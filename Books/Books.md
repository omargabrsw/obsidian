---
cssclasses:
  - wide
---

# Books

```dataviewjs
// Fetch all book pages
const books = dv.pages('"Books"')
  .where(b => b.file.name !== "Books read list" && b.file.name !== "Books");

// Use the DataviewJS container for the grid
const container = dv.container;
container.style.display = "grid";
container.style.gridTemplateColumns = "repeat(auto-fit, minmax(160px, 1fr))";
container.style.gap = "16px";
container.style.padding = "8px";

// Optional: container background (lightly contrast with Obsidian dark theme)
container.style.backgroundColor = "#1e1e1e";

// Create each book card
books.forEach(book => {
  const card = document.createElement("div");
  card.style.border = "1px solid transparent"; // default border
  card.style.borderRadius = "8px";
  card.style.overflow = "hidden";
  card.style.cursor = "pointer";
  card.style.display = "flex";
  card.style.flexDirection = "column";
  card.style.alignItems = "center";
  card.style.background = "#2a2a2a";
  card.style.transition = "transform 0.2s, border 0.2s, box-shadow 0.2s";
  card.style.boxShadow = "0 2px 6px rgba(0,0,0,0.3)";

  // Hover effect: lift and border color
  card.onmouseover = () => {
    card.style.transform = "translateY(-4px)";
    card.style.border = "1px solid #8888ff";
    card.style.boxShadow = "0 6px 12px rgba(0,0,0,0.5)";
  };
  card.onmouseout = () => {
    card.style.transform = "translateY(0)";
    card.style.border = "1px solid transparent";
    card.style.boxShadow = "0 2px 6px rgba(0,0,0,0.3)";
  };

if (book.cover) {
  const img = document.createElement("img");
  img.src = book.cover;
  img.style.width = "100%";
  img.style.height = "auto";      
  img.style.display = "block";    
  img.style.objectFit = "contain";
  card.appendChild(img);
}

  // Book title
  const title = document.createElement("div");
  title.textContent = book.file.name;
  title.style.fontWeight = "bold";
  title.style.marginTop = "8px";
  title.style.textAlign = "center";
  title.style.color = "#f0f0f0";
  title.style.padding = "0 4px";
  card.appendChild(title);

  // Author
  const author = document.createElement("div");
  author.textContent = book.author ?? "Unknown";
  author.style.fontSize = "0.9em";
  author.style.color = "#bbbbbb";
  author.style.textAlign = "center";
  author.style.paddingBottom = "8px";
  card.appendChild(author);

  // Click to open
  card.onclick = () => app.workspace.openLinkText(book.file.path, "", false);

  // Append card to container
  container.appendChild(card);
})
```

