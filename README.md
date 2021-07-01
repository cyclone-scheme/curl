# curl

## Index 
- [Intro](#Intro)
- [Dependencies](#Dependencies)
- [Test dependencies](#Test-dependencies)
- [Foreign dependencies](#Foreign-dependencies)
- [API](#API)
- [Examples](#Examples)
- [Author(s)](#Author(s))
- [Maintainer(s)](#Maintainer(s))
- [Version](#Version) 
- [License](#License) 
- [Tags](#Tags) 

## Intro 
Cyclone Scheme bindings for the [cURL library](https://curl.haxx.se/).

## Dependencies 
None

## Test-dependencies 
None

## Foreign-dependencies 
None

## API 

### (cyclone curl)

#### [procedure]   `(curl-global-init flags)`

Initialize cURL with the given flags integer value.

This function is only required if `curl-easy-init` is not called.

#### [procedure]   `(curl-easy-init)`

Initialize cURL with default options and return a Cyclone Opaque object that maybe used for subsequent calls.

#### [procedure]   `(curl-easy-cleanup opq)`

Cleans up a cURL object initialized via easy init.

#### [procedure]   `(curl-easy-setopt opq option param)`

Set option, with given parameter `param`, on the cURL easy handle `opq`

#### [procedure]   `(curl-easy-perform opq)`

Perform cURL request using the given easy handle stored in `opq`.

#### [procedure]   `(curl-version)`

Returns the cURL version as a string.


## Examples
```scheme
(import (cyclone curl)
        (scheme base))

(define curl (curl-easy-init))
(curl-easy-setopt curl CURLOPT_URL "http://example.com")
(curl-easy-perform curl)
(curl-easy-cleanup curl)
```

## Author(s)
Justin Ethier

## Maintainer(s) 
Justin Ethier

## Version 
"0.2.0"

## License 
MIT

## Tags 
networking web http
