---
title: "Core API"
description: "Main library functions and classes"
author: "API Team"
date: "2024-01-18"
tags: ["api", "core", "functions"]
---

# Core API

The core API provides the main functionality of our library.

## Main Class

### `Library`

The main class that provides all library functionality.

```typescript
import { Library } from 'our-library';

const lib = new Library(options);
```

#### Constructor Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `debug` | `boolean` | `false` | Enable debug mode |
| `timeout` | `number` | `5000` | Request timeout in ms |

#### Methods

##### `initialize()`

Initialize the library.

```typescript
await lib.initialize();
```

##### `process(data: any)`

Process data through the library.

```typescript
const result = await lib.process(data);
```

## Utility Functions

### `validate(data: any)`

Validate input data.

```typescript
import { validate } from 'our-library';

const isValid = validate(data);
```

### `transform(data: any, options: TransformOptions)`

Transform data according to options.

```typescript
import { transform } from 'our-library';

const transformed = transform(data, { format: 'json' });
``` 