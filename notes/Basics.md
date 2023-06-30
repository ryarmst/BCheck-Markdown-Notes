---
title: Basics
created: 2023-06-30T01:30:36.851Z
modified: 2023-06-30T01:30:45.364Z
---

# Basics

## Important Notes
- Burp replaces line endings in multi-line strings with `\r\n` and trims trailing and leading whitespace except for spacing immediately following or proceeding the opening `"`
- Characters can be escaped with `\`
- Burp supports Java-style regex
- `#` is used for comments

### Special chars
- `\n` - new line
- `\r` - carriage return
- `\s` - space
- `\t` - tab
- `\b` - backspace
- `\f` - form feed


## Strings
- Double quotes denote literals: `"this is a test"`
- Backticks can be used for interpolatable string: `` `https://{random_str(10)}.example.com` ``**


