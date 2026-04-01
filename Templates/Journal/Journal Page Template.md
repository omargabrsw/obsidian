<%* 
// 1️⃣ Prompt for journal title
const journalTitle = await tp.system.prompt("Enter journal entry title");

// 2️⃣ Prompt Mood
const moods = ["Happy", "Sad", "Neutral", "Excited"];
const selectedMood = (await tp.system.multi_suggester(
  moods, moods, false, "Select your mood"
))[0];

// 3️⃣ Prompt Reflection (tags)
const reflections = ["Work", "Personal Growth", "Relationships", "Gratitude"];
const selectedReflection = (await tp.system.multi_suggester(
  reflections, reflections, false, "Select the type of reflection"
))[0];

// 4️⃣ Rename the file to match title
await tp.file.rename(tp.date.now("YYYY-MM-DD") + " - " + journalTitle);

// 5️⃣ Generate frontmatter dynamically so YAML parses correctly
tR += `---
date: ${tp.date.now("YYYY-MM-DD")}
mood: "${selectedMood}"
tags: ["Journal", "${selectedReflection}"]
---
`

%>