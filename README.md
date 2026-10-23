# Battery

Omarchy widget `io.github.dexterhere.battery`: battery charge, state and time left. A **spec widget**: three JSON files, no code, no network, no files, no programs.

## Status

Pre-release (0.1.0). Spec only.

- There is no code in this repository, only `manifest.json`, `widget.json` and `layout.json`.
- The `battery.status` topic (`percent`, `state`, `timeLeft`) is in the website's provider catalog, but the daemon does **not** serve it yet. Status is **planned**: the widget cannot show real data until a battery provider ships.
- The desktop renderer does not exist yet either. The layout schema is DRAFT v0 and may change.

## Variants

All variants read the same three fields. Variant names are in `widget.json`, trees in `layout.json`.

| Variant    | Shows                                         | Size class        |
| ---------- | --------------------------------------------- | ----------------- |
| `ring`     | ring, big percent, state (the default)        | compact           |
| `bar`      | icon, percent, bar, state                     | compact           |
| `percent`  | big percent only                              | compact           |
| `chip`     | battery icon and percent, for the bar         | chip              |
| `timeleft` | bolt icon, percent, time left, state          | compact           |
| `detailed` | ring, percent, bar, state and time left       | wide              |

## Settings

None. A layout is plain data with no expressions, so it cannot honour a setting such as a low-battery threshold. `settings` is empty on purpose; add one when the format can act on it.

## Access

Reads `battery.status` (`percent`, `state`, `timeLeft`) only. Network, files, programs: none. No secrets.

## Install and removal

Not installable yet (no renderer, no battery provider). When the tooling exists, install from the Omarchy widget registry listing and remove it the same way. Nothing is written outside the widget's own entry, so removal leaves no files behind.

## Licence

MIT, see `LICENSE`.
