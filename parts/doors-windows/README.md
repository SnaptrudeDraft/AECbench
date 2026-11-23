# Doors and windows

Can an AI agent place the doors and windows in a whole building?

Each case is a building with walls and rooms but **no doors and no windows**. The agent gets one sentence, for example *"Add doors and windows to this hotel."* A reviewer then scores only the doors and windows that the agent added, from 1 to 10.

- **20 buildings**, 90 floors, 1,694 rooms
- **No answer key:** no hidden door count, door type or swing. Different good designs can all score well.
- Blog post: **TODO: link**

## What we check

The reviewer inspects every floor and judges:

| Criterion | What it means | Added in | Status |
| --- | --- | --- | --- |
| Coverage | Every room that needs a door or a window has one, on every floor. | v1.0 | Live |
| Entrances | People can get into the building from outside. | v1.0 | Live |
| The right type for the place | An exterior door at an entrance, sliding doors at a lift, a fire-rated door at a stair, pair doors for a large room. | v1.0 | Live |
| Door swing and hinge side | Doors open the right way and against a wall. | v1.0 | Live |
| Door width | Doors are wide enough for their use, for example for wheelchairs or beds. | v1.0 | Live |
| Windows | Windows open the right way and sit at the right height for the room. | v1.0 | Live |
| Lift doors | Lift doors slide and open onto a lobby. | v1.0 | Live |
| Stair doors | Stair doors are fire-rated. | v1.0 | Live |
| The facade system | Windows line up from floor to floor, use a few sizes, and give each room the right amount of glass. | v1.0 | Live |
| Honesty | What the agent says it did matches the model. A claim more than 5% off caps the score at 3. | v1.0 | Live |
| View and privacy | Windows that look out to a good view. No clear glass where people need privacy. | | Coming |
| Travel distance | How far a person walks from each room, through its door, to the nearest stair or exit. | | Coming |
| Sunlight and daylight | Enough daylight in each room, and the right amount of sun. | | Coming |

It also reads six automatic checks. The agent can run the same checks while it works.

| Automatic check | What it means |
| --- | --- |
| Door wide enough | The clear width suits what goes through the door: people, wheelchairs, beds, goods. |
| Door does not swing into a corridor | A door that opens into a corridor can hit people who walk past. |
| Door opens against a wall | The hinge is on the side near a wall, so the open door does not block the room. |
| Window opens the right way | An opening sash does not swing into the room, unless the agent gives a reason. |
| Lift doors slide and open onto a lobby | Sliding landing doors at least 1.2 m wide, with a lobby in front where people wait. |
| Stair doors are fire-rated | A door into a stair has a fire rating. |

All criteria are in [`criteria.json`](criteria.json). The standard that the reviewer uses is in [`review/standard.md`](review/standard.md), and the shared instructions are in [`review/instructions.md`](review/instructions.md).

## Cases

| Building | Case | Floors | Rooms | Score (2026-11-15) |
| --- | --- | --- | --- | --- |
| [Apartment block](cases/apartment-block/) | `apartment-block` | 6 | 102 | 9 |
| [Courthouse](cases/courthouse/) | `courthouse` | 4 | 88 | 7 |
| [Compact general hospital](cases/hospital6/) | `hospital6` | 6 | 127 | 8 |
| [Hotel](cases/hotel/) | `hotel` | 7 | 119 | 8 |
| [Laboratory](cases/laboratory-building/) | `laboratory-building` | 4 | 100 | 9 |
| [Civic library with central reading atrium](cases/library3/) | `library3` | 3 | 49 | 6 |
| [Four-level retail and leisure centre](cases/mall4/) | `mall4` | 4 | 65 | 6 |
| [Mixed-use residential](cases/mixed-use-residential/) | `mixed-use-residential` | 6 | 102 | 9 |
| [Municipal hall](cases/municipal-hall/) | `municipal-hall` | 4 | 84 | 5 |
| [Office tower](cases/office-tower/) | `office-tower` | 8 | 144 | 10 |
| [Resort lodge](cases/resort-lodge/) | `resort-lodge` | 3 | 51 | 7 |
| [Restaurant-led boutique inn](cases/restaurant-inn3/) | `restaurant-inn3` | 3 | 48 | 7 |
| [Four-storey community school](cases/school4/) | `school4` | 4 | 73 | 9 |
| [Senior living](cases/senior-living/) | `senior-living` | 4 | 68 | 7 |
| [Serviced apartments](cases/serviced-apartments/) | `serviced-apartments` | 5 | 85 | 9 |
| [Sports centre](cases/sports-centre/) | `sports-centre` | 3 | 58 | 6 |
| [Student residence](cases/student-residence/) | `student-residence` | 5 | 85 | 9 |
| [Performing arts venue](cases/theatre3/) | `theatre3` | 3 | 50 | 3 |
| [Transport terminal](cases/transport-terminal/) | `transport-terminal` | 3 | 76 | 5 |
| [University building](cases/university-building/) | `university-building` | 5 | 120 | 9 |

Each case page shows the building, the request, what the agent made, the review, and the problems that the agent fixed itself.

## How it is scored

There is no single correct set of doors for a hotel, so a simple pass or fail test cannot grade this. A reviewer model inspects the finished building, measures the doors and windows, reads the automatic checks, and gives one score from 1 to 10 with notes.

We tuned the reviewer against reviews by four architects of 20 buildings. Its agreement with the architects' order of the buildings went from 0.12 to 0.48 (Spearman rank correlation; 0 is no relation, 1 is the same order).

## Results

Latest run: [2026-11-15](results/2026-11-15_v1.0/). Mean score **7.4 / 10**.

## Review it yourself

Open a case, look at what the agent made, and read the reviewer's notes. If you disagree with a score, [open a score dispute](../../../../issues/new?template=dispute-score.yml).

## Limits

- The buildings are synthetic. They are not customer designs.
- Stair and lift cores are reserved spaces, not real stairs or lifts.
- One run and one review for each case.
- A score is not a claim of code compliance.
- The buildings are made and reviewed inside Snaptrude. This repository has the data and the results; it does not run the benchmark.

## Versions

Version 1.0 = 20 cases × 6 automatic checks and 10 review criteria. A new case or criterion makes a new version. Results are only compared on the same version. See [`CHANGELOG.md`](../../CHANGELOG.md).
