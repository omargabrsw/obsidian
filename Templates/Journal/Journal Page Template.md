<%* 
const journalTitle = await tp.system.prompt("Enter journal entry title");

const moods = ["Happy", "Sad", "Neutral", "Excited"];
const selectedMood = (await tp.system.multi_suggester(
  moods, moods, false, "Select your mood"
))[0];

const reflections = ["Work", "Personal Growth", "Relationships", "Gratitude"];
const selectedReflection = (await tp.system.multi_suggester(
  reflections, reflections, false, "Select the type of reflection"
))[0];

await tp.file.rename(tp.date.now("YYYY-MM-DD") + " - " + journalTitle);

tR += `---
date: ${tp.date.now("YYYY-MM-DD")}
mood: "${selectedMood}"
---
`
tR += `#Journal #${selectedReflection.replace(/\s+/g,"_")}\n\n`
%>
