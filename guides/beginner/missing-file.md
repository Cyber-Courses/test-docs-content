---
title: "Missing File Test"
description: "This file references non-existent content"
author: "Documentation Team"
date: "2024-01-29"
tags: ["error-test", "missing-file"]
---

# Missing File Test

This file contains links to non-existent files to test 404 handling.

## Broken Internal Links

- [Non-existent Guide](../non-existent-guide)
- [Missing API Reference](../../api/non-existent-endpoint)
- [Broken Example](../../examples/non-existent-example)

## Broken External Links

- [Broken External Link](https://example.com/non-existent-page)
- [Invalid Protocol](ftp://invalid-protocol.com)

## Expected Behavior

The system should:
1. Detect broken internal links
2. Show appropriate 404 pages for internal links
3. Handle external link failures gracefully
4. Log broken link errors
5. Provide helpful error messages

## Testing 404 Handling

This helps test:
- 404 page generation
- Broken link detection
- Error boundary handling
- User-friendly error messages 