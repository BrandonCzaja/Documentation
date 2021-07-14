# Express Documentation

## express()

-   Creates an Express application
-   The `express()` function is a top-level function exported by the express module

```
    const express = require('express')
    const app = express()
```

-   My notes: All express apps must have the above two lines, or the equivalent with import

## Middleware a.k.a. Methods

### express.json([options])

-   Parses incoming requests with JSON payloads
