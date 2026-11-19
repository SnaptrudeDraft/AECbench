# Resort lodge

Case `resort-lodge` · Doors and windows v1.0

## 1. The building

- **Type:** Resort lodge
- **Floors:** 3
- **Rooms:** 51
- **Start:** Whole-building recorded BIM layout; zero starting openings; reserved vertical cores.
- **Data:** [`building.json`](building.json) has every room, core and access link, in metres. [`case.json`](case.json) lists the known limits of this building.

## 2. The request

> Add doors and windows to this resort-lodge.

This is all the agent gets. There is no answer key: no hidden door count, door type or swing.

## 3. What the agent made

- **88 doors** and **148 windows** on 3 floors.

![Ground floor plan of the finished model](plan.jpg)

*Ground floor plan of the finished model, in Snaptrude.*

<details>
<summary><b>The agent's final message to the user</b></summary>

I've added the doors and windows to the lodge: **88 doors and 148 windows** across the three floors, with none refused. Not furnished: all rooms. They were empty before, and this pass covered openings only.

**Doors**
- **Main entrance:** a 6′-0″ (1.83 m) double door in the south wall of Lodge reception, opening outward. There's no site drawn, so I treated the south side as the front. Tell me if the approach is from somewhere else and I'll move it.
- **Ground-floor outside doors:** a garden door at each end of the main corridor. Delivery doors in the outside walls of Food receiving (south) and Waste sorting (north). Both stairs have an outside exit door.
- **Rooms:** every room opens off the main corridor with a door that swings into the room. Dining rooms, the briefing room, the meditation and wellness studios and reception get double doors; all others get 3′-0″ (0.91 m) single doors. The kitchen also opens into both dining rooms.
- **Behind the lift lobbies:** the lifts, plus Food receiving, Waste sorting and the linen rooms, are entered from their lift lobby. The lifts have 1.2 m sliding landing doors.
- **Stairs:** corridor doors into both stairs are rated 60 min and open into the stair.

**Windows**
- Every room people use has 4′-9″ × 6′-0″ (1.45 × 1.83 m) casements on a 2′-0″ (0.6 m) sill: two or three per room, about 1/8 of the floor area as glass.
- Corner rooms get two more on the end wall. The upper corridors have a window at each end.

**Fixed while checking:** 10 single doors had the latch side tight against a wall. They're now flipped to hinge the other way: the south lift lobbies, the food receiving, waste and linen rooms, and the roof maintenance room.

**CA — circulation and access (BIM stage)**
- **Spine:** met. A double-loaded corridor runs the full length of each floor, 5′-11″ (1.80 m) clear, against the 1.1 m minimum for hotels (IBC). Nothing stands in it. The lift lobbies are on it.
- **Entrance:** partly met. It's on the south edge I assumed as the front. It opens into Lodge reception, which leads straight to the corridor, but reception isn't labelled as a lobby.
- **Access:** ground floor 28 of 28 rooms reachable, 0 rooms without a door on any floor. Upper floors: not verified (see Egress).
  - Rooms entered through a lift lobby rather than the corridor: Food receiving, Waste sorting, Clean and Soiled linen rooms (floor 2), Clean and Soiled linen stores (floor 3), and all 6 lifts.
- **Daylight:** met, 51 of 51 rooms people use have an outside window. No room is meant to be dark.
- **Dead ends:** met. The longest is about 1.5 m, past the stair doors.
- **Toilets:** the Public WC is entered from the corridor. It isn't divided inside yet, so separate men's, women's and accessible WCs are not verified.
- **Service routes:** partly met. Food receiving and Waste sorting each have their own outside door, and the kitchen opens directly into both dining rooms. But deliveries share the guest corridor; the existing plan has no separate back-of-house corridor.
- **Egress:** two stairs, about 59 m apart, against about 32 m (half the plan diagonal). Both open straight outside at ground level.
  - Whether each upper floor connects down to the ground is not verified. The stairs aren't modelled yet, and the stair rooms are named differently on each floor ("F01:…", "F02:…"), so the check can't match them up. This is also why the model check reports "no stair between storeys" twice; both findings were there before this turn.
- **Doors:** all 88 read for which way they open; 0 needed their swing flipped and 10 needed their hand flipped.
  - These open outward or slide on purpose: the electrical intake room (plant), 6 stair doors (into the stair, the way people escape), 6 outside doors (exits) and 6 sliding lift doors.
- **Findings left open:** 0, apart from the stair link above.

**BA — BIM authoring**
- **Openings:** every door and window is a real door or window element, none built as a mass. Doors and windows went in as one batch each per floor.
- **Clashes:** door/door, door/window and window/window: pass, 0 clashes and 0 duplicates.
- **Model check:** no new findings. No leftover sketch rooms remain.
- **Not touched this turn:** wall conversion, construction types, partitions, slab openings, structure and roof.

**Suggested next steps**
1. Place stair families in the West and East stair rooms, cut the openings through the floors, and give the stair rooms one name on every floor. That lets the check confirm every upper floor connects down to an exit.
2. Divide the suite "envelopes" and the Public WC into rooms, and add their inner doors.
3. Furnish the rooms: dining seating, a kitchen line, suite beds, the reception desk and WC fittings.
4. Add an entrance canopy, then apply exterior finishes and show the lodge in Realistic view.

</details>

## 4. The review

**Score: 7 / 10**

The opening task is substantially complete across all occupied storeys: I measured 36/26/26 doors and 46/53/49 windows on storeys 1–3, with every room having a door and every identified habitable room having an exterior window. The systemic defect is window suitability: nearly all windows have a 0.604 m sill, including guest-suite and office-like uses where the standard expects about 0.9–1.0 m, so significant repeated adjustment is needed despite otherwise strong hosting, sizing, and operation checks.

**Problems left that the automatic checks found:** 0

### What was right

- Complete whole-building coverage: storey 1 has 36 doors/46 windows, storey 2 has 26/53, and storey 3 has 26/49.
- All 82 recorded rooms have at least one door; no floor or room-use group is missing door coverage.
- Habitable-window coverage is complete by floor: 15/15 occupied rooms on floor 1, 15/15 on floor 2, and 17/17 on floor 3.
- All 236 openings have wall hosts and lie within their host bounding boxes.
- Opening measurements report no swing, hand, sash-direction, width, lift-door, or fire-rating findings. Lift doors are sliding and measure 1.20 m nominal; the main entrance is a wide double-swing door.
- The final counts of 88 doors and 148 windows exactly match the live model, and the agent openly disclosed the 0.6 m sill choice.

### What was wrong

- A single 0.604 m sill strategy was applied to nearly all windows, including the 19 guest/suite-envelope rooms and office-like uses; this is below the standard’s approximately 0.9–1.0 m expectation for bedrooms and offices.
- Moving-leaf and sash sweep clearance against walls, fixtures, and adjacent leaves was not independently established; this remains not assessed rather than a failure.
- Building-wide access status is unverified because 54 upper-floor rooms are reported as not linked to other floors, but this results from the disclosed reserved stair/lift starting-model condition and is not penalized in this opening-only review.

### Where it breaks the standard

| Rule | What happened | Evidence |
| --- | --- | --- |
| Window sill heights must suit the room use, approximately 0.9–1.0 m in bedrooms and offices. | Almost all habitable-room windows use a uniform low sill of approximately 0.604 m, including guest-suite and office-like rooms. | Measured window bottoms were 0.604 m above the floor on all floor-1 windows and nearly all floor-2 and floor-3 windows; only four upper-corridor windows measured about 0.908 m. |

### Measured evidence

Live measurements found 88 doors and 148 windows, all 236 hosted and bounding-box-contained in their host walls; the access check found 0 doorless rooms and habitable-window coverage of 15/15 on storey 1, 15/15 on storey 2, and 17/17 on storey 3. Window bounding boxes measured 0.604 m sills throughout almost all rooms, matching the agent’s statement: “Every room people use has … casements on a 2′-0″ (0.6 m) sill.”

The full review is in [`results/2026-11-15_v1.0/reviews/resort-lodge.json`](../../results/2026-11-15_v1.0/reviews/resort-lodge.json).

## 5. Self-fixes

The agent's checks found no door problems to fix while it worked.

---

Disagree with this score? [Open a score dispute](../../../../../../issues/new?template=dispute-score.yml).
