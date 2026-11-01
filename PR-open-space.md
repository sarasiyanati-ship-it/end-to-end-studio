**Skill:** `plugins/design/skills/open-space/`

**What it makes, in one line:** Parks, squares, green corridors, playgrounds, trees and rainwater retention on the structure plan, sized against the brief and a design rain, as `open-space.geojson`, key numbers and three maps (open space, rainwater, climate fit).

**Reads:** structure-plan, climate, drawing-graphics. Reads (end): massing

**Writes:** (in `<proposal folder>/open-space/`) `open-space.geojson`, `catchments.geojson`, `key-numbers.json`, `key-numbers.csv`, `assumptions.md`, `open-space.svg/.png`, `rainwater.svg/.png`, `climate-fit.svg/.png` (only with climate output), `drawings.txt`, `summary.md`

**Tested on:** `competition/proposals/test/`: yes

- structure-plan has not been run yet, so the test used a **stand-in** traced after the brief's framework plan (p. 37), labelled STAND-IN in the data and on the maps.
- climate could not run in my environment (weather APIs unreachable), so the test used a **stand-in** in climate's output format: the corridor after the brief's text (pp. 24, 33) and shade from existing buildings and woods. It is labelled STAND-IN.
- Also tested with no structure plan, no climate and no targets (the built-in stand-in path), and with a fake massing (sealed area from roofs and streets).
- Test result: 28.7 % of the site is green, with 10.9 ha of public green against 6 ha in the brief and 7,500 m² of play area. 9,609 m³ of retention is needed and is held in swales and basins. The cold-air corridor overlaps about 12.6 ha of neighbourhoods, which is flagged for massing.

**What still isn't right:**

- **Design rain 30 mm in 60 min is an assumption.** The brief gives none. The local value goes in `targets.json`; in Germany it would come from KOSTRA-DWD.
- **No terrain data:** retention is placed along the green edges, not checked against the falls of the land.
- Without massing, roofs and streets are estimated as shares of each neighbourhood. Rerun after massing.
- No drawing-graphics yet, so the maps use the fallback: black on white with one accent, and water as a line hatch.

- [x] I changed only my own skill folder
- [x] No key, no personal path, no site, competition or layer name of my own in the skill
- [x] It works alone: in a fresh chat, and in an empty project with only a brief
- [x] Drawing skills: no colours, line weights or fonts of my own, and no fixed scale
- [ ] Tested once without the skill too
