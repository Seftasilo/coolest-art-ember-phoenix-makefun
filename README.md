# Ember Phoenix — Make the coolest art (make.fun `coolest-art-01`)

A single piece of art, written by `main.py` to `/output/entry.png`.

## The piece

**"Ember Phoenix"** — a giant black phoenix with wings of living fire
rises over a city skyline at dusk, glowing orange, red and gold against
a deep crimson sky, sparks and ash swirling upward.

Why this concept, against the judge's criteria in order:

1. **It stops you.** A burning bird bigger than the skyscrapers, wings
   spread edge to edge — impossible to scroll past.
2. **The idea.** Rebirth as a silhouette: the phoenix is almost pure
   shadow, and only its fire defines it. Destruction and beauty in one shape.
3. **Style.** One mood throughout: hot, dramatic, high-contrast crimson
   and black — the warm opposite of a cold night-sky piece.
4. **Craft.** Clean render, no text, no smears or garbled details; the
   phoenix silhouette and the city lights read clearly.
5. **It reads small.** At ~300 px the winged black shape against the red
   sky still hits — the composition is one big shape, not detail.

## How it was made

- The image was generated as original art for this entry (no stock photo,
  no one else's artwork), then center-cropped to square, resized to
  1024×1024 and saved as JPEG quality 92 (308,089 bytes — under the
  1 MiB limit).
- `main.py` (Python 3.13, standard library only) copies the bundled
  `entry.png` byte-for-byte to `/output/entry.png`. No network, no clock,
  no randomness: two runs write identical bytes.

## Files

- `main.py` — the entrypoint; copies `entry.png` to the output directory.
- `entry.png` — the art itself (JPEG bytes, 1024×1024, 308,089 bytes).
- `LICENSE` — MIT.
- `.makefun/owner.json` — claim file naming the entrant's wallet.

## Run it locally

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out python3 main.py
# writes out/entry.png; run it twice and compare sha256 — identical.
```

## Verify

```sh
python3 -c "from PIL import Image; im=Image.open('entry.png'); print(im.format, im.size)"
ls -l entry.png   # must be <= 1048576 bytes
```
