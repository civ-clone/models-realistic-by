# models-realistic-by

Realistic units for [civ.one](https://civ.one)'s 3D map, adapted from models on Sketchfab by their authors, under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Wherever they're used, credit the authors as
[CREDITS.md](CREDITS.md) does.

The set draws 21 unit types, mostly the later ones: Diplomat, Paratroopers, Fanatics, Mech. Inf., Cannon, Artillery,
Howitzer, Armor, Freight, Nuclear, Cruise Missile, Fighter, Helicopter, Stealth Fighter, Galleon, Destroyer, Cruiser,
AEGIS Cruiser, Battleship, Submarine and Carrier.

[models-realistic-cc0](https://github.com/civ-clone/models-realistic-cc0) draws the rest of the realistic units, under
CC0. Some of these types are drawn by [models-cimpletoon](https://github.com/civ-clone/models-cimpletoon) too.
civ.one's 3D map draws each type from one set.

## What's here

- **`models/*.glb`:** one glTF binary for each model, facing `+z`, with one baked colour texture (JPEG, 512 px for
  people and 1024 px for the rest), a second for a prop, and a PNG at half the size of the one it goes with for its
  owner's colour. Each was cut down to its budget where it was over (2,000 triangles for a
  person, 2,500 for the Paratroopers with their parachute, 3,000 for a vehicle or gun, 2,500 for an aircraft or
  missile, 3,500 for a ship), and its colour baked into the texture. Each carries its credits in `asset.copyright`,
  and its credits, licence and what was done to it in `asset.extras`.
- **Put together:** the Diplomat wears a top hat, the Paratroopers hang under a parachute and the Fanatics carry a
  torch, each from a model of its own. The Paratroopers' soldier I generated in Meshy (CC0, made with AI: an image
  from a text prompt with Google's Nano Banana, then a model from the image); the file is CC BY because of its
  parachute. The Paratroopers are one soldier under a canopy 3.2 m wide: draw them once, not as a squad, or the
  canopies cut through each other. With the canopy they're 5.9 m tall, so they have a scale of their own, 0.045, which
  draws them 0.26 squares tall, about as tall as a rider; their soldier is drawn smaller than other people.
- **Animated:** the Fighter keeps its propeller's animation and the Helicopter its rotors' and wheels', each with its
  parts as their nodes place them. The rest are one mesh each, standing still (but for the rigged figures below).
- **Standing and floating:** a model stands on its origin, centred across and along, at its real size in metres. A
  ship floats with its origin at the waterline, its draught under it (`extent.draught`). Aircraft rest on the ground;
  the 3D map lifts them.
- **`models/rigged/diplomat.glb`:** not in the manifest. The Diplomat with its own 72-bone skeleton and its author's 25
  animations (idle, walking, running, talking, sitting, turning, a jump, blinks and mouth shapes), the hat on its head
  bone. Play an animation: at rest it lies flat.
- **The owner's colour:** each model takes its owner's colour on one part, as models-0ad and models-cimpletoon do:
  - **people:** their jacket or robe (and the Diplomat's tie), and the Paratroopers' parachute;
  - **guns:** the Cannon's carriage and wheels, and the Artillery's and Howitzer's paint;
  - **vehicles:** the Armor's upper hull and turret, the Mech. Inf.'s hull and the Freight's canvas cover;
  - **missiles:** the Nuclear's green bands and the Cruise Missile's wings;
  - **aircraft:** their wingtips, and the Helicopter's tail boom;
  - **ships:** a band along the hull, the Galleon's below its rail, the Carrier's island too, and the Submarine's
    conning tower.

  Those faces are a primitive of their own, drawn with a material that says `extras.playerColour` and a PNG at half
  the texture's size. Where the owner's colour goes, the PNG is grey, shaded as the texture is there but lifted to a
  light grey, with its alpha 0, and civ.one draws it as `rgb × mix(owner, white, alpha)`. Where a rule goes texel by
  texel (`cut`), as for bands and wingtips, and the colour ends partway across a face, the rest of that face is the
  texture's colour, solid, at that half size. The rest of each model is drawn from its JPEG as before. Where the
  colour goes is each model's `owner` rule in `roster.json`. The rigged Diplomat has none yet.
- **Poses:** the Fanatics, made standing with their arms held out and their hands open, hold their torch upright at
  their side in a fist, the other arm down, its hand curled and its fingers together. The Diplomat stands as in the
  first frame of his idle, and the Paratroopers' soldier hangs under his parachute as he was made.

  A figure is posed by `tools/blender/stance.py`, as its `stance` in `roster.json` says: a skeleton fitted to it where
  it stands in the file, the way each bone should point, any pieces that move whole (the torch), and how a hand's
  fingers curl (`fingers`: the Fanatics' right hand a fist, which holds the torch across its palm, and their left
  curled, its fingers drawn together). Blender weights each point to the bones near it, and the file's points and
  normals are moved; nothing else in it changes but a mark on the mesh (`extras.posed`).
- **Rigged and animated:** the Fanatics, besides the Diplomat's own skeleton and clips above. `tools/blender/rig.py`
  rigs a posed figure with its clips, as models-realistic-cc0's Partisans and riflemen are (a held weapon can be
  brought to the shoulder in both hands, and fire from its muzzle): as its `rig` in `roster.json` says, into
  `models/rigged/<model>.glb`, which the manifest then names (`rigged`). That's where the Diplomat's extra is, so it
  would move before the Diplomat were rigged; `build.py` and `check.py` refuse the two in one place.

  The Fanatics have models-realistic-cc0's Partisans' `idle` (3 s) and `move` (1 s), which loop, and `die` (1.5 s),
  their torch held up as they stand, and a `fight` of their own (1.5 s, played once): the torch drawn back by the
  shoulder and thrust out at arm's length, upright, its burning head at an enemy's face, landing at 0.5 s (its
  `strike`). It's a thrust, so nothing flies. Fallen, they lie along the ground from their hood's thick cowl to their heels, their back a few
  centimetres up, the torch on the ground beside them.
- **Not yet:** the Fighter's markings are taken off, but some ships still carry painted names and numbers.
- **`manifest.json`:** the set, as civ.one's library describes a set of models:
  - its licence, with the credit to show wherever it's used (`licence.attribution`), and its credits;
  - the scale it's drawn at, and any model's own where it isn't the set's;
  - each model's file and its SHA-256, its triangles, how far it reaches (`extent`, in metres), its animations, where
    it's from and what was done to it;
  - a rigged model's rigged file, its SHA-256, its clips by role, where its shots leave from, by clip, and when a
    blow lands, for a fight with no shots, such as the Fanatics' (`strikes`, by clip) (`rigged`);
  - which unit types each model draws (`names.unit`, by the engine's names for them).
- **`roster.json`:** what's built, and how:
  - each source: its page, author and licence, where its file came from and that file's SHA-256;
  - each model: the unit types it draws, its source, any parts left out, a piece its original fuses to the figure and
    how it's split off (`split`; none here yet), how it's cut (part by part, or wrapped in one new surface, which can
    be closed over a split piece's slits), how it's turned and sized, how deep a ship floats, the prop put in and how
    (a piece split off can be turned to stand as the figure is posed), where its owner's colour goes, how a figure is
    posed, how it's rigged and its clips, its budget, and its scale where it isn't the set's.

  The set's scale draws a 1.8 m person as tall as the other sets' people, 0.168 squares. The 3D map draws units
  bigger than life, so the rest have scales of their own, close to models-cimpletoon's sizes: vehicles and guns
  0.20 to 0.27 squares long, aircraft and missiles 0.16 to 0.22 across their longest side, ships 0.30 to 0.45 long.
- **`tools/`:** the build (`build.py`, with the Blender scripts it runs in `tools/blender/`) and the check CI runs
  (`check.py`).

## Building them again

`check.py` needs only Python 3.10 or later:

```bash
python3 -I tools/check.py
```

Building the models again needs [Blender](https://www.blender.org) (4.5 was used) and the original files, which
`roster.json` names by SHA-256. Put them in one folder, then:

```bash
python3 -I tools/build.py --blender /path/to/blender --originals /path/to/originals
```

Name models to build only those. Blender runs with its factory settings and with scripts in files turned off, and
reads the originals only as data. Without `--originals`, `build.py` only writes each model's `asset.copyright` and
`asset.extras`, the manifest and the credits.

The owner's colour goes on next to last, and the pose last. `owner.py` won't colour a file that has it already, and
`stance.py` poses a figure from where it stands, so a changed `owner` rule or `stance` takes effect only when its
model is built again from its original. `check.py` checks each rule's form, not that the file follows it.

The originals:
- **Most:** the copies in [Objaverse](https://huggingface.co/datasets/allenai/objaverse), whose links the roster
  gives.
- **The rest:** each model's GLB download on Sketchfab (1K textures), which needs a Sketchfab account.
- **The Paratroopers' soldier:** generated in my Meshy account, and too big to keep here. I've kept it.

With Blender 4.5 on the Mac they were made on, a model built again comes out the same file. Another version of
Blender, or another platform, may cut or bake it a little differently.

## Licence

- **The models** (`models/`) are adapted from their authors' models, under
  [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), and my changes are under it too, as are the manifest and
  `CREDITS.md`, which describe them. Credit the authors
  wherever they're used, as CREDITS.md does.
- **The tools, the roster and the files about the repository** (`tools/`, `roster.json`, this README and the rest)
  are mine, under the MIT licence.

See [LICENSE.md](LICENSE.md).
