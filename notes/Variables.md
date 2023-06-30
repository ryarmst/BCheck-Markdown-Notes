---
title: Variables
created: 2023-06-30T00:49:19.830Z
modified: 2023-06-30T01:30:36.031Z
---

# Variables

## References
- [PortSwigger: BCheck Definition Reference](https://portswigger.net/burp/documentation/scanner/bchecks/bcheck-definition-reference)

## Examples
Define a variable with a global scope
```
define:
	variable_name = "some value"
```

Assign a collaborator address to a variable
```
define:
	collaborator_address = {generate_collaborator_address()}
```

Array variables can be created that are run once for each value when later called
```
run for each:
  variable_name = "value 1", "value 2", and so on
```

An array of URLs
```
run for each:
  url_array =
    null,
    "http://example.com",
    `https://{random_str(5)}{base.response.url}`
                    
```

## Reserved Variables
Specific request/response properties.

- `base` - the request/response received initially by Burp
- `latest` - the most resent request/response pair from the scan
- `{request_name}` - a specific request and response pair that has been named

### Request/Response Template
```
base|latest|{request_name} {
  response {
    status_code
    headers
    body
    http_version
  }
  request {
    method
    url {
      protocol
      host
      port
      path
      file
      query
    }
    http_version
    headers
    body
  }
}
```

Example: `request.url.protocol` returns the protocol
