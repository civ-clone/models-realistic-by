# Licence

This repository holds two kinds of work under two licences.

## The models: CC BY 4.0

`models/`, `manifest.json` and `CREDITS.md` are adapted from models by the authors listed in [CREDITS.md](CREDITS.md)
and in each file's `asset.extras`, each licensed by its author under the Creative Commons Attribution 4.0 International
licence: https://creativecommons.org/licenses/by/4.0/

I made these changes, which are under the same licence:
- **Fewer triangles:** each is cut down, part by part or wrapped in one new surface, to no more than `roster.json`
  says, and its colour baked into one texture. Parts the roster names are left out first (the Fighter's markings, the
  Artillery's second gun).
- **Placing:** each is turned to face `+z`, sized in metres, and stood on the ground or floated at its waterline. The
  Diplomat stands as his idle animation's first frame has him.
- **Assembly:** the Diplomat's top hat, the Paratroopers' parachute and the Fanatics' torch are each put with the
  model they go with.
- **Format:** each is a glTF binary with a JPEG texture, carrying its credits in `asset.extras`.

The Paratroopers' soldier I generated for civ.one with [Meshy](https://www.meshy.ai) from a text prompt (made with
AI), and dedicate to the public domain under CC0 1.0 (https://creativecommons.org/publicdomain/zero/1.0/); the file is
CC BY because of its parachute.

You may use, change and share them, for any purpose, if you credit each author as CREDITS.md does, with a link to the
licence, and say that they were changed. A credit you can copy for the whole set:

> Models by the authors credited in this set, CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/): reduced,
> rebaked, assembled and converted by dom111.

The Transport comes from a page that says it "may not be used in datasets for, in the development of, or as inputs to
generative AI programs".

## The tools: MIT

`tools/`, `roster.json` (what's built, and how), and the files about the repository (`README.md`, `LICENSE.md`,
`package.json`, `.github/`, `.gitignore`, `.gitattributes`) are mine:

MIT License

Copyright (c) 2026 dom111

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated
documentation files (the "Software"), to deal in the Software without restriction, including without limitation the
rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit
persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the
Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE
WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR
OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
