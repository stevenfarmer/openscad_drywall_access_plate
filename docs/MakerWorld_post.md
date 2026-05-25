# Parametric Drywall Access Panel

## Hidden Clamp System | No Screws | OpenSCAD | Flush Mount

---

# IMAGE PLACEHOLDERS TO ADD BEFORE POSTING

Replace these with real renders/photos/screenshots before posting unless you want your listing to look like an abandoned repo maintained by raccoons.

## Required Images

1. Hero image of assembled panel installed in drywall
2. Exploded view showing all parts
3. Layout view showing individual parts separated
4. Rear-side install view showing clamp ring
5. Wedge key close-up showing correct orientation
6. Cable notch version installed with HDMI/network cable
7. Print orientation diagram
8. OpenSCAD customizer screenshot
9. Dimensional diagram showing what to measure
10. Optional install GIF/video
11. Close-up of wall insert flange support in slicer
12. Installed rear view showing wedges locked against clamp ring

---

# DESCRIPTION

Finally.

A drywall access panel that does **not** look like it belongs in a sad apartment maintenance closet.

This is a fully parametric OpenSCAD drywall access panel with a hidden clamp system, removable flush cover, wedge locking keys, and zero visible screws. It is designed for FDM printing and configurable directly inside OpenSCAD.

The panel installs using a rear clamp ring and wedge-lock system that compresses against the backside of the drywall. Once installed, the removable cover plate sits cleanly in the front recess with hidden pry/service access.

It actually looks intentional.

Wild concept.

---

# TESTED PRINT SETUP

Tested successfully with:

* Bambu P1P
* 0.4 mm nozzle
* PLA
* 0.20 mm layer height
* 3–4 walls
* 7–15% gyroid infill
* Bambu Studio `Tree (Auto)` supports with `Snug` style for the wall insert flange

Approximate print time and filament usage will vary by configured panel size, because this is parametric and your drywall hole may be either reasonable or evidence of crimes.

Suggested common starter sizes to generate/export:

* 120 x 120 mm opening
* 180 x 180 mm opening
* 215 x 215 mm opening, if your printer bed and exclusion zones allow it

If you are printing near your machine's max build area, check the actual slicer build plate limits and exclusion zones before assuming the advertised bed size is real. Printer marketing departments are chaos goblins with nicer fonts.

---

# WHAT MAKES THIS DIFFERENT

Most printable access panels are either:

* ugly as hell
* screw-mounted
* friction-fit sadness
* designed around brittle snap tabs
* weirdly overcomplicated
* somehow all of the above

This one uses a **wall insert**, **rear clamp ring**, and **wedge keys** so the panel can clamp into a drywall opening without visible hardware.

The cover is separate, removable, and cleaner-looking than the usual “I made this in CAD at 2 AM and gave up” wall plate.

---

# QUICK START GUIDE

This is the “I just want the damn thing to print” section.

## Step 1 — Measure Your Opening

Measure the drywall hole you want the panel to fit into.

You need:

* opening width
* opening height
* drywall thickness

Use millimeters if possible. OpenSCAD wants millimeters, because apparently civilization requires suffering.

Common drywall thicknesses:

* 1/2 inch drywall = about **12.7 mm**
* 5/8 inch drywall = about **15.9 mm**

## Step 2 — Enter These Values

In OpenSCAD, set:

```scad
opening_width = 180;
opening_height = 180;
drywall_thickness = 12.7;
```

Replace those example values with your measured values.

## Step 3 — Pick Your Fit Mode

```scad
fit_mode = "normal";
```

Use:

* `loose` if your printer runs tight or you want easier assembly
* `normal` for the recommended starting point
* `tight` only if your printer is dialed in and you enjoy tempting fate

Start with `normal` unless you have a good reason not to.

If you are unsure, print a smaller test size first. It is cheaper to waste a little plastic than to discover your printer is dimensionally spicy after a full-size wall part.

## Step 4 — Pick Your Cover

```scad
cover_variant = "blank";
```

Options:

* `blank` = clean solid removable cover
* `cable_notch` = removable cover with a tombstone-style cable pass-through notch

If using the cable version, set:

```scad
cable_notch_position = "bottom_center";
cable_slot_width = 20;
```

Cable notch position options:

* `bottom_left`
* `bottom_center`
* `bottom_right`

## Step 5 — Preview the Parts

Set:

```scad
part_selector = "all";
preview_mode = "layout";
```

Use `layout` mode to see all parts separated. This is the best preview mode for sanity-checking because OpenSCAD render mode is not always great at showing colors/transparency. Shocking, I know.

Preview modes:

* `assembled` = shows the parts in assembled position
* `exploded` = separates cover/clamp ring for inspection
* `layout` = spreads parts apart for easier visual checking and exporting sanity

## Step 6 — Export Each Part

Set `part_selector` to each part and export individually:

```scad
part_selector = "wall_insert";
part_selector = "cover_plate";
part_selector = "clamp_ring";
part_selector = "wedge_key";
```

Print the wedge key multiple times. The design uses four wedge keys in the preview/install layout.

Do not export `all` unless you intentionally want one assembled STL blob. That is useful for looking at the model, not for printing separate parts.

## Step 7 — Print

Recommended print setup:

* 0.20 mm layer height
* 3–4 walls
* 7–15% gyroid infill
* supports are generally not needed for the cover plate, clamp ring, or wedge keys
* wall insert flange support is recommended; Bambu Studio `Tree (Auto)` supports with `Snug` style worked well in testing

## Step 8 — Install

1. Insert the wall insert into the drywall opening.
2. Place the clamp ring behind the drywall.
3. Slide the wedge keys through the sleeve slots from inside the opening.
4. Tighten until snug.
5. Press the cover into place.

You are clamping drywall, not torquing the head bolts on a tractor.

Snug is enough.

---

# INCLUDED PARTS

The OpenSCAD file can generate:

* wall insert
* removable cover plate
* rear clamp ring
* wedge key
* full assembly preview
* exploded preview
* separated layout preview

---

# FEATURES

## Fully Parametric

Customize:

* opening width
* opening height
* drywall thickness
* fit tolerance
* cover style
* cable notch position
* cable notch width
* cover lip depth
* cover lip clearance
* optional cover detents
* corner radius
* visible border size
* clamp ring overlap
* wedge retention strength
* cover top roundover

If your wall opening is weird because your measuring tape skills failed you emotionally, this can probably compensate.

## Hidden Wedge-Lock Clamp System

Instead of visible screws or garbage spring clips, this uses:

* rear clamp ring
* tapered wedge keys
* enclosed wedge slots in the sleeve
* compression locking against the backside of the drywall

No exposed hardware.
No rattling nonsense.
No tiny screws falling into another dimension.

## Enclosed Wedge Slots

The wedge key slots are enclosed through the wall insert sleeve instead of being open rear notches.

That means:

* cleaner slicing
* stronger sleeve geometry
* more predictable wedge placement
* less “why is this slot a weird broken trench?” nonsense

## Correct Wedge Preview Orientation

The preview shows the wedge keys flipped into their intended installed orientation so users can see how the thick/thin wedge faces apply pressure against the clamp ring.

This matters because wedges are simple right up until they are upside down and pissing you off.

Recommended image for this section: show one correct wedge orientation and one wrong orientation. Label them clearly. People will absolutely install them upside down if you let the universe make decisions.

## Two Cover Variants

### Blank Cover

Clean flush panel with hidden service pry slots on all four sides.

### Cable Notch Cover

Integrated tombstone-style cable notch for:

* HDMI
* USB
* speaker wire
* network cable
* low-voltage wiring
* random future nonsense you swear you'll label later

The cable notch exists only on the removable cover, so the wall insert stays structurally cleaner.

## Hidden Service Pry Slots

The cover can be removed using side-entry underside pry slots.

This avoids:

* screwdriver gouges
* broken fingernails
* drywall damage
* rage

For cable-notch covers, the cable notch acts as the bottom access point, and the other three sides keep pry slots.

## Softer Cover Plate Edge

The cover plate includes a configurable top roundover/chamfer so it does not look like a tiny plastic paving stone slapped on your wall.

Set this with:

```scad
cover_plate_top_roundover = 1.2;
```

Set it to `0` if you want a square/blocky edge because you hate joy.

## Optional Cover Detents

The cover includes optional small friction-fit detent ribs on the rear alignment plug.

Use these if the cover needs a little more grab:

```scad
cover_detents_enabled = true;
cover_detent_size = 0.35;
```

Keep detents small. These intentionally increase local friction, and too much detent will turn “snug cover” into “why did I print a wall plug from hell.”

---

# PRINT SETTINGS

## Recommended Material

### PLA

Works perfectly for normal indoor use.

### PETG

Recommended for:

* hotter environments
* utility rooms
* attic spaces
* long-term durability
* people who enjoy overbuilding things

## Recommended Settings

### Layer Height

0.20 mm

### Walls

3–4 walls

### Infill

7–15% gyroid infill

### Supports

Supports are generally not needed for the cover plate, clamp ring, or wedge keys.

For the wall insert, support under the front flange is recommended. I used Bambu Studio `Tree (Auto)` supports with `Snug` style, and that worked well.

Do not go support-happy inside the sleeve/key geometry unless your slicer specifically needs it. Support removal inside internal geometry is how people become villains.

---

# PRINT ORIENTATION

## Wall Insert

Print with the sleeve pointing upward and the front flange on the build plate.

Add support under the front flange overhangs if your slicer flags them. Bambu Studio `Tree (Auto)` supports with `Snug` style worked well in testing.

## Cover Plate

Print visible face upward for best surface finish.

## Clamp Ring

Print flat.

## Wedge Keys

Print flat on the large wedge surface.

Print at least four wedge keys.

---

# COMMON PRINT FAILURES

## Stringing or ugly underside under the wall insert flange

Use support under the front flange.

Bambu Studio `Tree (Auto)` with `Snug` style worked well in testing.

## Cover is too tight after printing

Increase:

```scad
cover_lip_clearance = 0.35;
```

Or use:

```scad
fit_mode = "loose";
```

## Cover is too loose after printing

Enable detents:

```scad
cover_detents_enabled = true;
cover_detent_size = 0.35;
```

Or slightly reduce:

```scad
cover_lip_clearance = 0.20;
```

## Wedge keys are hard to insert

Increase:

```scad
key_slot_clearance = 0.35;
```

Or use:

```scad
retention_strength = "light";
```

## Clamp ring is hard to fit through the opening

Reduce:

```scad
clamp_ring_overlap = 10;
```

Or generate a slightly larger opening size if you are still in planning mode.

---

# PACKAGED STL SUGGESTIONS

If you are publishing this as a MakerWorld model, consider uploading a few ready-to-print STL/3MF sets in addition to the OpenSCAD source.

Recommended sets:

* 120 x 120 mm blank cover set
* 180 x 180 mm blank cover set
* 180 x 180 mm cable notch set
* 215 x 215 mm blank cover set, if it fits your printer profile cleanly

Each set should include:

* wall insert
* cover plate
* clamp ring
* four wedge keys

The OpenSCAD file is the real magic, but MakerWorld users also like when the printer can just go brrrr without a side quest.

---

# INSTALLATION GUIDE

## Step 1 — Cut the Drywall Opening

Cut the drywall opening to match your configured `opening_width` and `opening_height`.

Try not to freehand this like a caffeinated raccoon.

## Step 2 — Insert the Wall Sleeve

Insert the wall insert into the opening from the front.

The front flange should sit against the visible wall surface.

## Step 3 — Position the Clamp Ring

Insert the clamp ring through the opening and position it behind the drywall.

The clamp ring sits on the backside of the drywall and gives the wedge keys something to compress against.

## Step 4 — Install Wedge Keys

Slide the wedge keys through the side slots from inside the opening.

The wedges tighten the clamp ring against the backside of the drywall.

Tighten until snug.

Again: drywall, not submarine hatch.

## Step 5 — Install Cover Plate

Press the cover plate into the front recess.

If it is too tight, increase `cover_lip_clearance` slightly.

If it is too loose, enable detents or reduce clearance.

Done.

You now have a clean access panel instead of contractor sadness.

---

# ADVANCED GUIDE / TUNING

This is the “fine, let’s tune the bastard” section.

## Main Parameters

### Part Selection

```scad
part_selector = "all";
```

Options:

* `all`
* `cover_plate`
* `wall_insert`
* `clamp_ring`
* `wedge_key`

Use `all` for previewing only. Export individual parts one at a time for printing.

### Preview Mode

```scad
preview_mode = "assembled";
```

Options:

* `assembled`
* `exploded`
* `layout`

Use `layout` if OpenSCAD color/transparency behavior is being useless in render mode, which it often is.

### Preview Transparency

```scad
preview_transparency = 0.65;
```

Transparency is mostly useful in OpenSCAD F5 preview mode.

F6 render mode may not visually honor it in a useful way, because OpenSCAD occasionally behaves like it was built by a committee of haunted geometry goblins.

For reliable visual separation in F6/render mode, use:

```scad
preview_mode = "layout";
```

## Fit Tuning

### Fit Mode

```scad
fit_mode = "normal";
```

Options:

* `loose`
* `normal`
* `tight`

Use `loose` if:

* the wall insert is too tight in the opening
* the clamp ring fights installation
* your printer tends to over-extrude
* you want easier field assembly

Use `tight` only if:

* your printer is accurate
* you want snugger alignment
* you enjoy living dangerously

### Cover Lip Clearance

```scad
cover_lip_clearance = 0.25;
```

Increase this if the cover is hard to seat or remove.

Decrease slightly if the cover feels sloppy.

### Cover Lip Depth

```scad
cover_lip_depth = 1.5;
```

This controls the deeper rear alignment plug on the cover plate.

The plug fits into the sleeve bore and helps keep the cover aligned.

## Cover Retention

### Optional Detents

```scad
cover_detents_enabled = false;
cover_detent_size = 0.35;
```

Enable detents if the cover needs more friction.

Start small. Big detents are a great way to create an access panel that technically works but requires a blood oath to remove.

## Clamp Strength

### Retention Strength

```scad
retention_strength = "normal";
```

Options:

* `light`
* `normal`
* `strong`

Use `light` for easier wedge insertion/removal.

Use `normal` for most cases.

Use `strong` if the panel needs a firmer clamp or the drywall opening is slightly imperfect.

### Key Slot Clearance

```scad
key_slot_clearance = 0.25;
```

Increase this if the wedge keys are too tight in the slots.

Decrease only if the keys feel loose and your printer is accurate enough to justify the arrogance.

## Visual Design

### Plate Border

```scad
plate_border = 10;
```

Larger values make the front flange/cover more forgiving of rough drywall cuts.

Smaller values look sleeker but give you less margin for drywall sins.

### Corner Radius

```scad
corner_radius = 8;
```

Controls rounded corners on the visible cover/frame and related parts.

### Cover Plate Top Roundover

```scad
cover_plate_top_roundover = 1.2;
```

Controls the softened top edge of the cover plate.

Set to `0` for a square edge.

## Cable Notch Tuning

### Cover Variant

```scad
cover_variant = "cable_notch";
```

Options:

* `blank`
* `cable_notch`

### Cable Notch Position

```scad
cable_notch_position = "bottom_center";
```

Options:

* `bottom_left`
* `bottom_center`
* `bottom_right`

### Cable Slot Width

```scad
cable_slot_width = 20;
```

The cable notch height is derived automatically from the width so the tombstone shape stays proportional.

Increase the width for larger cable bundles.

Do not make the notch huge unless you want the cover to look like it lost a bar fight.

## Clamp Ring Sizing

### Clamp Ring Overlap

```scad
clamp_ring_overlap = 14;
```

This controls how much the rear clamp ring overlaps around the drywall opening.

Larger overlap gives more clamping surface.

Smaller overlap may be easier to insert through tight openings, but gives less bite behind the drywall.

---

# TROUBLESHOOTING

## Cover Is Too Tight

Try:

```scad
cover_lip_clearance = 0.35;
```

Or use:

```scad
fit_mode = "loose";
```

## Cover Is Too Loose

Try:

```scad
cover_detents_enabled = true;
cover_detent_size = 0.35;
```

Or slightly reduce:

```scad
cover_lip_clearance = 0.20;
```

## Wedge Keys Are Too Tight

Increase:

```scad
key_slot_clearance = 0.35;
```

Or use:

```scad
retention_strength = "light";
```

## Wedge Keys Feel Too Loose

Use:

```scad
retention_strength = "strong";
```

Or reduce:

```scad
key_slot_clearance = 0.20;
```

## Clamp Ring Is Hard To Insert

Reduce:

```scad
clamp_ring_overlap = 10;
```

Or make the opening slightly larger if you are still in planning mode.

## OpenSCAD Preview Looks Like Yellow-on-Yellow Blob Hell

Use:

```scad
preview_mode = "layout";
```

Colors and transparency are useful in F5 preview, but F6 render may not show them the way you expect.

Layout mode spreads the parts apart so the model is easier to inspect even when OpenSCAD decides visual clarity is optional.

## Exported STL Contains All Parts Together

That means `part_selector` was probably set to:

```scad
part_selector = "all";
```

Set it to one part at a time before exporting:

```scad
part_selector = "wall_insert";
```

Then export.

Repeat for each part.

---

# USE CASES

Perfect for:

* behind TVs
* projector wiring
* smart home hubs
* low-voltage access
* hidden charging stations
* network access
* cable passthroughs
* plumbing shutoffs
* workshop wiring
* retrofit access
* future cable pulls
* “future me will thank me” planning

---

# NOTES

* Designed primarily for standard drywall thicknesses.
* Tight printers may require minor clearance adjustment.
* Wedge slots are enclosed for improved strength and cleaner printing.
* The preview wedges are intentionally flipped/oriented to demonstrate correct installation direction.
* The wall insert no longer has the cable notch; cable notch lives on the removable cover only.
* OpenSCAD F6 render may ignore useful transparency/color behavior, so layout mode is included for easier visual checking.
* If you need the largest possible panel for your printer, check your printer’s actual usable bed area and exclusion zones before assuming the full advertised build volume is real. Printer marketing departments are chaos goblins with nicer fonts.

---

# REMIX / LICENSE

Remix it.
Improve it.
Make it weird.

If you somehow evolve this into a NASA-certified pressure hatch, I absolutely want pictures.

---

# TAGS

drywall
access panel
wall plate
flush mount
hidden fastener
cable management
smart home
openscad
parametric
3d printing
low voltage
networking
home improvement
makerworld
remixable
no screws
hidden clamp
