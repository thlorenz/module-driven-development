# Intro

## substack 
  module.exports = function () {}

## connect

### dependencies

`
"dependencies": {
  "qs": "0.5.1",                // tj
  "formidable": "1.0.11",
  "cookie-signature": "0.0.1",  // tj
  "buffer-crc32": "0.1.1",
  "cookie": "0.0.5",
  "bytes": "0.0.1",             // tj
  "send": "0.1.0",              // tj and below
  "bytes": "0.1.0",
  "fresh": "0.1.0",
  "pause": "0.0.1",
  "debug": "*"
},
`

## Raynos
  twitter

# We got it

## Easier said than done

### Examine challenges and patterns to get there

#### Challenges

- spotting potential standalone modules 
- coupling (can't pull it out because it directly depends on another part of my app/lib)

#### Patterns

1.  small modules (helps spotting and keeps work to publish small)
2.  decouple, decouple
    - later discuss inversion of control, events, etc.
3.  continuously refactor out modules
4.  continuously pull out modules that serve a non app/lib related purpose
5.  pull out/test/readme/publish -> use anywhere

somewhat more work, but pays off especially once you need one of them ;)

# Example replpad

## Demo

- piping
- vim-bindings
- vim-map
- source code
- core docs

