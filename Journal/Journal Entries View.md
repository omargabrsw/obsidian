---
cssclasses:
  - wide
---

# Journal Pages

```dataviewjs
const journals = dv.pages('"Journal"')
  .where(j => j.file.name !== "Journal Entries View")
  .sort(j => j.file.ctime, 'desc')
  .limit(20);

const container = dv.container;

// === CONTAINER STYLE (background separation) ===
container.style.display = "grid";
container.style.gridTemplateColumns = "repeat(auto-fill, minmax(280px, 1fr))";
container.style.gap = "16px";
container.style.padding = "12px";
container.style.background = "#1a1a1a";
container.style.borderRadius = "12px";

// === BADGE HELPER ===
function createBadge(text, color) {
  const badge = document.createElement("span");
  badge.textContent = text;
  badge.style.fontSize = "0.75em";
  badge.style.padding = "4px 10px";
  badge.style.borderRadius = "999px";
  badge.style.background = color;
  badge.style.color = "#fff";
  return badge;
}

// === MAIN LOOP (ASYNC FOR FILE CONTENT) ===
(async () => {
  for (const journal of journals) {

    const card = document.createElement("div");

    // === CARD BASE ===
    card.style.background = "#242424";
    card.style.borderRadius = "14px";
    card.style.padding = "16px";
    card.style.cursor = "pointer";

    card.style.display = "flex";
    card.style.flexDirection = "column";
    card.style.justifyContent = "space-between";
    card.style.minHeight = "180px";

    // === DEPTH ===
    card.style.boxShadow = `
      0 1px 2px rgba(0,0,0,0.4),
      0 4px 12px rgba(0,0,0,0.5)
    `;
    card.style.border = "1px solid rgba(255,255,255,0.05)";

    card.style.transition = "all 0.25s ease";

    // === HOVER ===
    card.onmouseover = () => {
      card.style.transform = "translateY(-6px) scale(1.01)";
      card.style.boxShadow = `
        0 6px 18px rgba(0,0,0,0.6),
        0 12px 32px rgba(0,0,0,0.7)
      `;
      card.style.border = "1px solid rgba(255,255,255,0.12)";
    };

    card.onmouseout = () => {
      card.style.transform = "translateY(0) scale(1)";
      card.style.boxShadow = `
        0 1px 2px rgba(0,0,0,0.4),
        0 4px 12px rgba(0,0,0,0.5)
      `;
      card.style.border = "1px solid rgba(255,255,255,0.05)";
    };

    // === ACCENT BAR (optional polish) ===
    const accent = document.createElement("div");
    accent.style.height = "4px";
    accent.style.background = "linear-gradient(90deg, #6c5ce7, #00b894)";
    accent.style.borderTopLeftRadius = "14px";
    accent.style.borderTopRightRadius = "14px";
    accent.style.margin = "-16px -16px 12px -16px";

    card.appendChild(accent);

    // === TITLE ===
    const title = document.createElement("div");
    title.textContent = journal.file.name;
    title.style.fontWeight = "bold";
    title.style.color = "#ffffff";
    title.style.marginBottom = "6px";

    // === DATE ===
    const date = document.createElement("div");
    date.textContent = journal.file.ctime.toFormat("yyyy-MM-dd");
    date.style.fontSize = "0.8em";
    date.style.color = "#888";
    date.style.marginBottom = "8px";

    // === CONTENT PREVIEW ===
    let previewText = "";

    try {
      const file = app.vault.getAbstractFileByPath(journal.file.path);
      const content = await app.vault.read(file);

      previewText = content
        .replace(/---[\s\S]*?---/, "") // remove frontmatter
        .trim()
        .split("\n")
        .filter(line => line.trim() !== "" && !line.startsWith("#")) // remove empty + headings
        .join(" ")
        .slice(0, 140);

    } catch (e) {
      previewText = "...";
    }

    const preview = document.createElement("div");
    preview.textContent = previewText + "...";
    preview.style.fontSize = "0.9em";
    preview.style.color = "#999"; // reduced contrast
    preview.style.lineHeight = "1.4";

    // === TAGS ===
    const tagsContainer = document.createElement("div");
    tagsContainer.style.display = "flex";
    tagsContainer.style.flexWrap = "wrap";
    tagsContainer.style.gap = "6px";
    tagsContainer.style.marginTop = "10px";

    const tags = Array.isArray(journal.tags)
      ? journal.tags
      : typeof journal.tags === "string"
        ? journal.tags.split(",").map(t => t.trim())
        : [];

    tags.forEach(tag => {
      tagsContainer.appendChild(createBadge(tag, "#00b894"));
    });

    // === BUILD CARD ===
    card.appendChild(title);
    card.appendChild(date);
    card.appendChild(preview);
    card.appendChild(tagsContainer);

    // === CLICK ===
    card.onclick = () => app.workspace.openLinkText(journal.file.path, "", false);

    container.appendChild(card);
  }
})()
```