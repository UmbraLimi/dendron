---
id: 9106aff9-94e1-44b6-bba9-34f73642af91
title: Gotchas
desc: 'uuuu'
updated: 1618841709588
created: 1618841297340
---

# Dendron Gotchas

## Frontmatter

- beware of apostrophe's - be sure to escape them
  - today's // will stop dendron from parsing pn load
  - today\'s // works
- there is no need to surround strings in apostrophes UNLESS the string is EMPTY.
  - desc: '' **// is ok**
  - desc: 'Howdy' **// is ok, but not necessary**
  - desc: Howdy **// is ok**
