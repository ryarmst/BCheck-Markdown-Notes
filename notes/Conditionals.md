---
title: Conditionals
created: 2023-06-30T00:52:41.751Z
modified: 2023-06-30T01:01:49.202Z
---

# Conditionals

## References
- [PortSwigger: BCheck Definition Reference](https://portswigger.net/burp/documentation/scanner/bchecks/bcheck-definition-reference)

## Template
Simple condition
```
if [condition] then
  [action]
end if
```

else if then
```
if [condition 1] then
  [action 1]
  else if [condition 2] then
   [action 2]
end if
```

else then
```
if [condition] then
  [action]
  else then
    [action 2]
end if
```       

## Examples
Check the latest response against a regular expression version and report an informational issue
```
if {latest.response} matches "Apache Tomcat [\d\s\.]+" then
  report issue:
    severity: info
    confidence: certain
    detail: "Disclosed Apache Tomcat Server"
    remediation: "Do not return detailed component information"
end if
```


## Conditions
```
{X} matches "[regex]" - True if X matches the regex provided.
{X} differs from {Y} - True if response X differs from response Y.
{X} in {Y} - True if Y contains X (for example, Y could be a responseand X could be a header to search for within that response).
{X} is {Y} - True if the provided parameters are identical.
any interactions - True if Burp Collaborator has received anyinteractions.
dns interactions - True if Burp Collaborator has received any DNSinteractions.
http interactions - True if Burp Collaborator has received any HTTPinteractions.
smtp interactions - True if Burp Collaborator has received any SMTPinteractions.
```

### Logic
Conditions can be combined and modified with:
- and
- or
- not
Brackets can also be used to refine the flow of logic.
