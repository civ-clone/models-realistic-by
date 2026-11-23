# Licence

This repository holds two kinds of work under two licences.

## The models: CC BY 4.0

`models/` are adapted from models by the authors listed in [CREDITS.md](CREDITS.md) and in each file's `asset.extras`,
each licensed by its author under the Creative Commons Attribution 4.0 International licence:
https://creativecommons.org/licenses/by/4.0/ (but for the Paratroopers' soldier, CC0, below). `manifest.json` and `CREDITS.md`, which describe them, are under the
same licence.

I made these changes, which are under the same licence:
- **Fewer triangles:** each is cut down, part by part or wrapped in one new surface, to no more than `roster.json`
  says, and its colour baked into one texture. Parts the roster names are left out first (the Fighter's markings, the
  Artillery's second gun).
- **Placing:** each is turned to face `+z`, sized in metres, and stood on the ground or floated at its waterline. The
  Diplomat stands as his idle animation's first frame has him.
- **Assembly:** the Diplomat's top hat, the Paratroopers' parachute and the Fanatics' torch are each put with the
  model they go with.
- **The owner's colour:** on each model in the manifest, the faces that take their owner's colour, as `roster.json`
  says, are a primitive of their own, with a PNG of their own whose alpha is 0 where the colour goes.
- **Poses:** the Fanatics are posed holding their torch upright, out of the T-pose they were made in.
- **Format:** each is a glTF binary with JPEG textures (and that PNG), carrying its credits in `asset.copyright` and
  `asset.extras`.

The Paratroopers' soldier I generated for civ.one in [Meshy](https://www.meshy.ai) on a paid plan: from a text prompt,
Meshy made an image with Google's Nano Banana, then a model from the image (made with AI). Meshy's terms make it mine,
and I dedicate it to the public domain under CC0 1.0 (https://creativecommons.org/publicdomain/zero/1.0/); the file
is CC BY because of its parachute.

You may use, change and share them, for any purpose, if you credit each author as CREDITS.md does, with a link to the
licence, and say that they were changed. A credit you can copy for the whole set:

> Models by the authors listed at https://github.com/civ-clone/models-realistic-by/blob/main/CREDITS.md, CC BY 4.0
> (https://creativecommons.org/licenses/by/4.0/): reduced, rebaked, assembled, given their owner's colour and
> converted by dom111.

CC BY 4.0 licenses each author's own rights in their model. It grants nothing in anyone else's designs or trademarks,
such as those of the real vehicles, aircraft and ships these depict.

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
