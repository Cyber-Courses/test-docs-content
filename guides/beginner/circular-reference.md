---
title: "Circular Reference Test"
description: "This file tests circular reference handling"
author: "Documentation Team"
date: "2024-01-30"
tags: ["error-test", "circular-reference"]
---

# Circular Reference Test

This file tests how the system handles potential circular references in navigation.

## Self-Reference

This file links to itself: [Circular Reference Test](./circular-reference)

## Parent Reference

This file links to its parent: [Beginner Guides](../)

## Expected Behavior

The system should:
1. Detect circular references
2. Prevent infinite loops in navigation
3. Handle self-references gracefully
4. Log circular reference warnings
5. Continue functioning normally

## Testing Navigation Loops

This helps test:
- Circular reference detection
- Navigation loop prevention
- Breadcrumb generation with loops
- Sidebar rendering with circular links

## Best Practices

In real documentation:
- Avoid self-references
- Use clear navigation hierarchies
- Test navigation flows
- Monitor for circular references 