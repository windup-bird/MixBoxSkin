# MixBox: a Mixxx skin for all-in-one DJ units

- Mixxx **2.5.x**, minimum window **1024x600**
- No image assets — everything is drawn by Mixxx widgets plus QSS
- Palette: dark blue-grey base with a single `#3d8bfd` accent, one hue per deck

![overview](MixBox/skin_preview.png)

## Install

```sh
ln -s "$PWD/MixBox" ~/.mixxx/skins/MixBox    # or: cp -r MixBox ~/.mixxx/skins/
```

Restart Mixxx, then pick **Mixbox v2 Touchscreen** in Preferences → Interface.
`~/.mixxx/skins` may itself be a symlink to a working copy; Mixxx follows it.

## Skin settings

Persisted via the toolbar buttons, all under `[Skin]`: `aio_show_browser`,
`aio_show_hotcue`, `aio_show_loopjump`, `aio_show_deckfx`, `aio_show_colorfx`,
`aio_show_4decks` (2/4 deck), `show_waveforms`, `show_coverart`.

## Known limits

- 4-deck mode at 600px height leaves ~16px per waveform lane, since the deck
  cards are a fixed 100px. Collapsing them (and hiding the overview) whenever
  `aio_show_4decks` is on would be the fix.
- Knobs render as arcs only — there are no knob bitmap or SVG assets.
- Mixxx skin XML cannot open Preferences, quit, or toggle an effect's
  `enabled` state; those remain keyboard/hardware only.
- `overflow` and `row-height` in the QSS are not real Qt properties and are
  ignored, so the overview "half wave" trick does not actually clip.

## License

Creative Commons Attribution, Share-Alike 3.0 Unported — see the manifest.
