# Results: 2026-11-15, doors and windows v1.0

- **Agent model:** claude-opus-5-5, one run per case, 1 hour per case.
- **Reviewer:** reviewer v2 (gpt-5.6-sol), one review per case.
- **Mean score:** 7.4 / 10. 14 of 20 buildings scored 7 or more.

| Building | Score | Doors | Windows | Problems left |
| --- | --- | --- | --- | --- |
| [Office tower](../../cases/office-tower/) | 10 | 220 | 366 | 0 |
| [Apartment block](../../cases/apartment-block/) | 9 | 164 | 350 | 0 |
| [Laboratory](../../cases/laboratory-building/) | 9 | 214 | 194 | 0 |
| [Mixed-use residential](../../cases/mixed-use-residential/) | 9 | 173 | 246 | 0 |
| [Four-storey community school](../../cases/school4/) | 9 | 138 | 167 | 1 |
| [Serviced apartments](../../cases/serviced-apartments/) | 9 | 136 | 254 | 0 |
| [Student residence](../../cases/student-residence/) | 9 | 136 | 152 | 0 |
| [University building](../../cases/university-building/) | 9 | 182 | 494 | 0 |
| [Compact general hospital](../../cases/hospital6/) | 8 | 208 | 146 | 0 |
| [Hotel](../../cases/hotel/) | 8 | 189 | 210 | 0 |
| [Courthouse](../../cases/courthouse/) | 7 | 162 | 244 | 16 |
| [Resort lodge](../../cases/resort-lodge/) | 7 | 88 | 148 | 0 |
| [Restaurant-led boutique inn](../../cases/restaurant-inn3/) | 7 | 98 | 83 | 0 |
| [Senior living](../../cases/senior-living/) | 7 | 111 | 202 | 0 |
| [Civic library with central reading atrium](../../cases/library3/) | 6 | 100 | 98 | 12 |
| [Four-level retail and leisure centre](../../cases/mall4/) | 6 | 120 | 140 | 17 |
| [Sports centre](../../cases/sports-centre/) | 6 | 101 | 120 | 0 |
| [Municipal hall](../../cases/municipal-hall/) | 5 | 134 | 232 | 0 |
| [Transport terminal](../../cases/transport-terminal/) | 5 | 74 | 104 | 0 |
| [Performing arts venue](../../cases/theatre3/) | 3 | 111 | 75 | 10 |

"Problems left" counts what the six automatic checks still found when the reviewer opened the finished model.

This folder does not change after release. A new run, or a run on a new version, gets a new folder.

Files: [`scores.csv`](scores.csv), [`run.json`](run.json), and one review for each case in [`reviews/`](reviews/).
