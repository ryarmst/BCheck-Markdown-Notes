---
title: Actions
created: 2023-06-30T01:00:57.419Z
modified: 2023-06-30T01:12:03.956Z
---

# Actions
These cause Burp Scanner to perform an action.

## References
- [PortSwigger: BCheck Definition Reference](https://portswigger.net/burp/documentation/scanner/bchecks/bcheck-definition-reference)

## Template


## Important Notes
- Request properties default to a replacement behavior without an action keyword

## Send Request
Sends a request with specified info.

### Template
```
send request [called request_name]: # "called request_name" gives the request a name for later reference
  [appending|replacing] headers:
    "name_of_header1": "value of header1",
    "name_of_header2": "value of header2"
  removing headers:
    "name_of_header1":,
    "name_of_header2":"
  [appending|replacing] queries:
    "name_of_query_1=http://portswigger.net",
    "name_of_query_2=https://portswigger.net"
  removing queries:
    "name_of_query_1",
    "name_of_query_2"
  [appending|replacing] path: "/test"
  removing path
  [appending|replacing] method: "GET" # how does appending a method work?
  removing method # how does removing a method work?
  [appending|replacing] body: "contents of body"
  removing body
```

## Send Request (raw)
Sends a raw request

Example
```
send request [called request_name]:
  "GET /catalog/product?productId=2 HTTP/2
  Host: ginandjuice.shop
  Cookie: session=qwertyuiop
  Content-Length: 2"
```

## Send Payload
Sends a request for each payload in each payload position for `given insertion point` Control Flows. 

### Template
```
send payload [called payload_name]:
  appending: "payload1", "payload2"
  replacing: "payload1", "payload2"
```

## Report Issues
Reports an issue. WARNING: reporting an issue will terminate the BCheck even if parts have not run. This behavior seems like a bad decision TBH.

### Template
```
report issue:
  severity: # `[info|low|medium|high]`
  confidence: # `[info|low|medium|high]`
  remediation:
  detail:
```
