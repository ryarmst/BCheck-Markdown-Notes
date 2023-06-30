---
title: Control Flow
created: 2023-06-30T00:44:56.702Z
modified: 2023-06-30T00:49:01.462Z
---

# Control Flow
Every bCheck needs a `given / then` statement to determine the scope of its actions.

## Template
```
given [response|request|host] | [ [any|query|header|body|cookie]* + insertion point] then
```

## Examples
### Insertion Points
For any insertion point
```
given any insertion point then
```

Query string insertion point
```
given query insertion point then
```

HTTP header insertion point
```
given header insertion point then
```

HTTP body parameter insertion point
```
given body insertion point then
```

HTTP Cookie insertion point
```
given cookie insertion point then
```

Combined query and body params using `or`
```
given query or body insertion point
```

### Responses
```
given response then
```

### Requests
```
given request then
```

### hosts
```
given host then
```
