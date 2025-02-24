---
id: Daily Template
aliases: []
tags: []
Mood: 0
Sleep: 0
Week: <% moment(tp.file.title).format('gggg-[W]ww') %>
Weight: 0
---

[[Journal/Daily/<% fileDate = moment(tp.file.title, 'YYYY-MM-DD').subtract(1, 'd').format('YYYY-MM-DD') %>|Yesterday]] [[Journal/Daily/<% fileDate = moment(tp.file.title, 'YYYY-MM-DD').add(1, 'd').format('YYYY-MM-DD') %>|Tomorrow]]

Weekly Review: [[<% moment(tp.file.title).format('gggg-[W]ww') %>]]

<% tp.web.daily_quote() %>

## Today's mood?

## Gratitude Today? (3 Things)

## Reflect of yesterday

### Accomplishments

### Challenges

### Thoughts for Improvements

## What can i do for my [[<% moment(tp.file.title).format('gggg-[W]ww') %> |Weekly]] Goal?
