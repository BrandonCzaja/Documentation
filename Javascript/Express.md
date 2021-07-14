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

-   Based on the npm package body-parser
-   Parses incoming requests with JSON payloads
-   Creates a new body object, `req.body`, on the request object that contains the parsed data
    -   If there was an error, the Content-Type didn't match, or no body to parse, the `req.body` is an empty object `{}`
-   Returns middleware that only parses JSON and only looks at requests where the Content-Type header matches the type option
-   Supports all Unicode encoding
-   Can handle and decompress deflated encodings (compressed)

#### express.json options

-   inflate
    -   Description:
        -   Enables or disables handling of deflated (compressed) bodies; when disabled, deflated bodies are rejected
    -   Type:
        -   Boolean
    -   Default:
        -   true
-   limit
    -   Description:
        -   Controls the maximum request body size. If this is a number, then the value specifies the number of bytes. If it is a string, the value is passed to the bytes library for parsing
    -   Type:
        -   Mixed
    -   Default:
        -   " 100kb "
-   reviver
    -   Description:
        -   Passed directly to `JSON.parse` as the second argument. For more info see MDN docs on JSON.parse
    -   Type:
        -   Function
    -   Default:
        -   null
-   strict

    -   Description:
        -   Toggles accepting only arrays and objects; when disabled, will accept anything `JSON.parse` accepts
    -   Type:
        -   Boolean
    -   Default:
        -   true

-   type

    -   Description:
        -   Determines what media type the middleware will parse
        -   Can be a string, array of strings, or a function
        -   If not a function, type option is passed directly to the `type-is` library and this can be an extension name (like json), a mime type (like application/json), or a mime type with a wildcard like (_/_ or \*/json)
        -   If a function, the type option is called as fn (req) and the request is parsed if it returns a truthy value
    -   Type:
        -   Mixed
    -   Default:

        -   application/json

-   verify
    -   Description:
        -   Ths option, if supplied, is called as verify (`req, res, buf, encoding`), where `buf` is a Buffer of the raw request body and `encoding` is the encoding of the request. The parsing can be aborted by throwing an error
    -   Type:
        -   Function
    -   Default:
        -   undefined
