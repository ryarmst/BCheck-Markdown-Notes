---
title: Functions
created: 2023-06-30T01:16:58.147Z
modified: 2023-06-30T01:23:25.907Z
---

# Functions
All BCheck functions are denoted with curly braces `{function}`

## Function List

### Numbers
- `{random_str(int)}`

### Regular Expressions
- `regex_replace (String source, String regex, String replacement)`
  - Example: `regex_replace ({var}, "[a-z]*@", "abc@")`

### String Transformation
- `{to_upper(string)}`

### Encoding
- `{base64_encode(string)}`
- `{base64_decode(string)}`

### Hashing
- `sha1(String)`
- `sha256(String)`
- `md5(String)`

### Collaborator
- `{generate_collaborator_address}`
