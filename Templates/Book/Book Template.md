---
title: "{{title}}"
subtitle: "{{subtitle}}"
author: 
  - "{{author}}"
rating: ":LiStar::LiStar::LiStar::LiStar::LiStar:"
category: 
  - "{{category}}"
publisher: "{{publisher}}"
publish: {{publishDate}}
total: {{totalPage}}
isbn: "{{isbn10}} {{isbn13}}"
cover: "{{coverUrl}}"
localCover: "{{localCoverImage}}"
status: unread
created: {{DATE:YYYY-MM-DD HH:mm:ss}}
updated: {{DATE:YYYY-MM-DD HH:mm:ss}}
---
# {{title}}

#Book 

<%* 
const cover = tp.frontmatter?.cover;

if (typeof cover === "string" && cover.trim() !== "") {
  tR += `![cover|150](${cover})\n`;
}
%>