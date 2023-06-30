---
title: 'Templates: Host Checks'
created: 2023-06-30T01:37:00.892Z
modified: 2023-06-30T01:49:48.560Z
---

# Templates: Host Checks


## Check for Git directory (/.git/config)
```
metadata:
    language: v1-beta
    name: "Host-level"
    description: "Checks for an exposed git directory"
    author: "Carlos Montoya"

run for each:
    potential_path =
        "/.git/config",
        "/.git/config~"

given host then
    send request called check:
        method: "GET"
        path: {potential_path}

    if "[core]" in {check.response.body} then
        report issue:
            severity: info
            confidence: certain
            detail: `Git directory found at {potential_path}.`
            remediation: "Ensure your git directories are not exposed."
    end if
```

## Check for robots.txt
```
metadata:
    language: v1-beta
    name: "robots.txt Check"
    description: "Checks for the presence of robots.txt"
    author: "Ryan Armstrong"

define:
    robots_path = "/robots.txt"

given host then
    send request called check:
        method: "GET"
        path: {robots_path}

    if "200" in {check.response.status_code} then
        report issue:
            severity: info
            confidence: certain
            detail: `robots.txt file identified`
            remediation: "Ensure sensitive paths are not exposed."
    end if
```

