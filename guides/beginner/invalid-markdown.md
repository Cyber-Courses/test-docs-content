---
title: "Invalid Markdown Test"
description: "This file has intentionally invalid markdown syntax"
author: "Documentation Team"
date: "2024-01-28"
tags: ["error-test", "invalid-markdown"]
---

# Invalid Markdown Test

This file has intentionally invalid markdown syntax to test error handling.

## Unclosed Code Block

```javascript
function test() {
  console.log("This code block is not closed properly
  return true;
}

## Unclosed List

- Item 1
- Item 2
  - Nested item without proper indentation
- Item 3

## Invalid Link

[Broken Link](broken-url-without-protocol)

## Invalid Image

![Broken Image](non-existent-image.jpg)

## Unclosed Bold Text

This text is **bold but not closed properly

## Invalid Table

| Column 1 | Column 2
| --- | ---
| Data 1 | Data 2
| Data 3

## Expected Behavior

The markdown renderer should:
1. Handle unclosed blocks gracefully
2. Show broken links/images with fallbacks
3. Continue rendering the rest of the content
4. Log parsing errors appropriately 