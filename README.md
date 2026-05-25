# Parametric Drywall Access Plate

A parametric OpenSCAD drywall access panel / wall plate system with a hidden rear clamp ring, removable flush cover, and wedge-lock keys.

This project is designed for FDM printing and easy customization inside OpenSCAD.

## What it generates

- Wall insert / sleeve
- Removable cover plate
- Rear clamp ring
- Wedge key
- Assembled preview
- Exploded preview
- Layout preview for easier inspection and export

## Quick start

Open `scad/DrywallAccessPanel.scad` in OpenSCAD and set the main parameters:

```scad
opening_width = 180;
opening_height = 180;
drywall_thickness = 12.7;
fit_mode = "normal";
cover_variant = "blank";
```

Preview all parts:

```scad
part_selector = "all";
preview_mode = "layout";
```

Export individual printable STLs by setting `part_selector` one part at a time:

```scad
part_selector = "wall_insert";
part_selector = "cover_plate";
part_selector = "clamp_ring";
part_selector = "wedge_key";
```

Do not export `all` unless you intentionally want one combined STL blob.

## Recommended print settings

- 0.20 mm layer height
- 3–4 walls
- 15–25% infill
- No supports in standard orientations
- Print at least four wedge keys

## Print orientation

- Wall insert: front flange face-down
- Cover plate: visible face upward
- Clamp ring: flat
- Wedge keys: flat on the large wedge surface

## Project docs

- `docs/MakerWorld_post.md` — MakerWorld listing/write-up draft
- `scad/DrywallAccessPanel.scad` — main parametric source file

## License

MIT License.
