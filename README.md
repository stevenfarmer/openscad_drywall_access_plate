# Parametric Drywall Access Plate

A parametric OpenSCAD drywall access panel / wall plate system with a hidden rear clamp ring, removable flush cover, and wedge-lock keys.

This repo contains the source for a printable, customizable drywall access panel designed for FDM printing. The model is generated from a single OpenSCAD file and can export the wall insert, cover plate, rear clamp ring, and wedge key as separate printable parts.

No visible screws. No brittle snap-tab nonsense. No sad beige apartment maintenance closet energy.

## What this project generates

- Wall insert / sleeve
- Removable cover plate
- Rear clamp ring
- Wedge key
- Assembled preview
- Exploded preview
- Layout preview for easier inspection and export

## Repository layout

```text
.
├── scad/
│   └── DrywallAccessPanel.scad
├── docs/
│   ├── MakerWorld_post.md
│   └── README.md
├── README.md
└── .gitignore
```

## Requirements

- OpenSCAD
- FDM 3D printer
- Slicer of choice, such as Bambu Studio, OrcaSlicer, PrusaSlicer, Cura, etc.

The source is plain OpenSCAD. No build system, package manager, or dependency dumpster fire required.

## Quick start

Open:

```text
scad/DrywallAccessPanel.scad
```

Then set your core dimensions:

```scad
opening_width = 180;
opening_height = 180;
drywall_thickness = 12.7;
```

Common drywall thicknesses:

- 1/2 inch drywall: about `12.7 mm`
- 5/8 inch drywall: about `15.9 mm`

Choose your fit mode:

```scad
fit_mode = "normal";
```

Options:

- `loose` — easier install/removal, useful for printers that run tight
- `normal` — recommended starting point
- `tight` — snugger fit if your printer is dialed in

Choose your cover variant:

```scad
cover_variant = "blank";
```

Options:

- `blank` — clean solid removable cover
- `cable_notch` — cover with a tombstone-style cable pass-through notch

Cable notch options:

```scad
cover_variant = "cable_notch";
cable_notch_position = "bottom_center";
cable_slot_width = 20;
```

Supported notch positions:

- `bottom_left`
- `bottom_center`
- `bottom_right`

## Preview workflow

To inspect all generated parts:

```scad
part_selector = "all";
preview_mode = "layout";
```

Preview modes:

- `assembled` — shows how parts fit together
- `exploded` — separates cover/clamp ring for inspection
- `layout` — spreads parts apart for easier visual checking

`layout` mode is the most reliable sanity-check view, especially because OpenSCAD render mode is not always great about useful color/transparency display. Tiny haunted geometry goblin stuff.

## Export workflow

Export each printable part individually by changing `part_selector`:

```scad
part_selector = "wall_insert";
```

Then export STL.

Repeat for:

```scad
part_selector = "cover_plate";
part_selector = "clamp_ring";
part_selector = "wedge_key";
```

Print at least four wedge keys.

Do not export with:

```scad
part_selector = "all";
```

unless you intentionally want one combined preview STL blob. That is useful for inspection, not for printing separate parts.

## Recommended print settings

- 0.20 mm layer height
- 3–4 walls
- 7–15% gyroid infill
- Print at least four wedge keys
- Supports are generally not needed for the cover plate, clamp ring, or wedge keys
- For the wall insert, support under the front flange is recommended
- Bambu Studio `Tree (Auto)` supports with `Snug` style worked well in testing

## Print orientation

| Part | Orientation | Supports |
|---|---|---|
| Wall insert | Sleeve pointing upward, front flange on build plate | Recommended under flange overhangs |
| Cover plate | Visible face upward | Usually no |
| Clamp ring | Flat | No |
| Wedge keys | Flat on large wedge surface | No |

## Installation overview

1. Cut the drywall opening to match your configured `opening_width` and `opening_height`.
2. Insert the wall insert from the front.
3. Position the clamp ring behind the drywall.
4. Slide wedge keys through the sleeve slots from inside the opening.
5. Tighten until snug.
6. Press the cover plate into place.

Snug is enough. You are clamping drywall, not sealing a submarine hatch.

## Main tunable parameters

| Parameter | Purpose |
|---|---|
| `opening_width` | Drywall opening width in mm |
| `opening_height` | Drywall opening height in mm |
| `drywall_thickness` | Actual wall board thickness in mm |
| `fit_mode` | Global clearance preset |
| `cover_variant` | Blank or cable notch cover |
| `cable_notch_position` | Cable notch location |
| `cable_slot_width` | Cable notch width |
| `cover_lip_clearance` | Cover plug fit clearance |
| `cover_detents_enabled` | Optional friction ribs for cover retention |
| `plate_border` | Visible border around opening |
| `corner_radius` | Rounded corner radius |
| `clamp_ring_overlap` | Rear clamp ring overlap behind drywall |
| `retention_strength` | Wedge-lock tightness preset |
| `key_slot_clearance` | Wedge key slot clearance |

## Troubleshooting highlights

### Cover is too tight

Increase:

```scad
cover_lip_clearance = 0.35;
```

or use:

```scad
fit_mode = "loose";
```

### Cover is too loose

Enable detents:

```scad
cover_detents_enabled = true;
cover_detent_size = 0.35;
```

or slightly reduce:

```scad
cover_lip_clearance = 0.20;
```

### Wedge keys are too tight

Increase:

```scad
key_slot_clearance = 0.35;
```

or use:

```scad
retention_strength = "light";
```

### Clamp ring is hard to insert

Reduce:

```scad
clamp_ring_overlap = 10;
```

## MakerWorld listing copy

The MakerWorld-focused write-up lives here:

```text
docs/MakerWorld_post.md
```

That version is written for model listing pages and print users. This README is written for the GitHub/source crowd.

## Generated assets

Generated STL/3MF/export files are intentionally ignored by `.gitignore`.

Suggested workflow:

1. Generate/export locally from OpenSCAD.
2. Keep source changes in Git.
3. Publish final printable files through MakerWorld or GitHub releases if desired.

## Contributing / remixing

Remix it. Improve it. Make it weird.

Useful contributions could include:

- additional cover variants
- alternate clamp/wedge geometries
- test print notes for different printers/materials
- better diagrams or screenshots
- slicer profile recommendations
- generated STL release packages

## License

MIT License.

Use it, modify it, remix it, publish your changes, and do cool stuff with it. Just keep the license notice and do not blame the project when your drywall hole looks like it was cut by a caffeinated raccoon.
