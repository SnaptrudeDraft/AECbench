# University building

Case `university-building` · Doors and windows v1.0

## 1. The building

- **Type:** University building
- **Floors:** 5
- **Rooms:** 120
- **Start:** Whole-building recorded BIM layout; zero starting openings; reserved vertical cores.
- **Data:** [`building.json`](building.json) has every room, core and access link, in metres. [`case.json`](case.json) lists the known limits of this building.

## 2. The request

> Add doors and windows to this university-building.

This is all the agent gets. There is no answer key: no hidden door count, door type or swing.

## 3. What the agent made

- **182 doors** and **494 windows** on 5 floors.

![Ground floor plan of the finished model](plan.jpg)

*Ground floor plan of the finished model, in Snaptrude.*

<details>
<summary><b>The agent's final message to the user</b></summary>

I've added **182 doors and 494 windows** to the university building. None of the rooms have furniture yet: the 120 teaching rooms, offices and study rooms, and the 5 washrooms and 5 pantries.

**Doors**
- **Rooms:** every room's door is in the wall it shares with a cloister and swings into the room. Rooms over about 750 sq ft get a 6'-0" pair door; the rest get a 3'-0" × 7'-0" single door.
- **Between spaces:** the four cloisters on each floor are walled off from each other, so there's a pair door at each corner where they meet. The lift lobby has a pair door onto the south cloister, and each lift has a centre-opening sliding door about 3'-11" wide.
- **Stairs:** both stairs (south-west and north-east corners) have a 60-minute fire-rated door from the cloister that opens into the stair.
- **Ground floor:** the main public entrance is at the east end of the south cloister, with two more entrances at each end of the north cloister. There are two pair doors into the courtyard, and each stair has an exit door straight outside.

**Windows**
- All 120 teaching rooms, offices and study rooms have windows in their outside wall: two-panel casements, 4'-9" × 6'-0", with a 3'-0" sill. They open outward, one to three per wall, giving roughly 1/10 to 1/8 of the floor area as glass.
- The cloister walls facing the courtyard and the outer ends of the cloisters also have windows.

**What I fixed:** two stair doors (floors 2 and 5) were hinged on the wrong side, so I flipped them. The model check now finds nothing new.

**Self-check against the model as it stands**

| Item | Result |
|---|---|
| Circulation | **met**: four cloisters in a loop around the courtyard, plus a lift lobby; stairs and lifts open off the cloisters |
| Entrance | **not verified**: the three entrances open into cloisters, not an entrance lobby. With no site in the project I can't tell which edge is the front. I treated the south cloister as the public front |
| Access | **met per floor**: 35 of 35 rooms reachable from both stairs on every floor; 175 of 175 rooms have a door. **Not met across the building**: the overall access check fails because nothing links one floor to the next |
| Daylight | **met**: 120 of 120 teaching rooms, offices and study rooms have an outside window. No room in them is meant to be dark, and none is internal |
| Corridor widths | **met**: cloisters about 9'-2" clear (2.8 m), against 1.8 m for a school (assumed). Routes measured: 4 cloisters per floor. Columns or furniture in corridors: 0 |
| Dead ends | **met**: the cloisters form a loop. The lift lobby is a 29 ft × 9'-10" dead-end pocket off the south cloister, ending at the lift doors |
| Toilets | **not verified**: each floor's washroom is one room entered from the west cloister. It has no separate men's, women's or accessible rooms inside |
| Routes | **not met (already in the plan)**: there is no separate service corridor. The pantry and cleaning store opens off the east cloister, the same route visitors use |
| Exits | **met**: 2 stair rooms on every floor, but no stairs are built in them yet. Stair centres are about 187 ft (57 m) apart, more than half the plan diagonal (137 ft / 42 m). Both stairs exit straight outside at ground level |
| Door swings | **met**: 182 doors placed; checked which way all 182 open; 0 needed flipping. 7 open outward by design: 3 entrances, 2 courtyard doors and 2 stair exits, all exits |
| Open findings | **met**: 0 new findings. The 4 "no stair between floors" findings were already in the model, because the stair rooms are still empty |
| Rooms equipped | **not met**: 0 of 130 rooms furnished, since furniture wasn't asked for |
| Openings | **met**: 182 doors and 494 windows, all real door and window elements. One batch of doors and one of windows per floor (42/97, 35/100, 35/99, 35/99, 35/99). 0 masses created. 0 windows open inward |
| Clashes and access | **met**: no overlaps between doors and windows on floors 1–5 (0 clashes, 0 duplicates, check complete). The building-wide access result is in the Access row |
| Rest | **not applicable**: no room conversion, partitions, slab openings, structure or roof this turn |
| Furniture | **not applicable**: none placed; 0 open findings |

The final picture of the model failed twice because of a display error, so I can't show it here. Reloading the tab should fix that.

**Possible next steps:**
1. Put actual stairs in the two stair rooms and lifts in the lift rooms, so the floors are properly connected and the building-wide access check can pass.
2. Divide each washroom into men's, women's and accessible toilets, each entered from a small lobby, and fit them with WCs and basins.
3. Furnish the 120 teaching rooms, offices and study rooms.
4. Add an entrance lobby or canopy at the main south-cloister entrance once the approach side is confirmed, and apply exterior and glazing finishes.

</details>

## 4. The review

**Score: 9 / 10**

The opening task is comprehensively delivered across all five occupied storeys: every one of the 182 doors and 494 windows is hosted, all 175 rooms have a door, habitable-room window coverage is present, and the shared opening rules report no findings. The result falls just short of 10 because moving-leaf/sash collision clearance could not be independently established, while 172 openings carry the limitation that leaf position is estimated; this is not a defect, but leaves a final sign-off item not assessed.

**Problems left that the automatic checks found:** 0

### What was right

- Complete opening coverage on occupied storeys 1–5: 42/35/35/35/35 doors and 97/100/99/99/99 windows.
- The access check reports 175 rooms, zero rooms without a door, and suitable direct room-to-cloister connections throughout every floor.
- All room doors checked in the live opening measurements open into their served rooms; stair doors open into the stair reservations and final exits open outside.
- All 494 windows are casements opening toward “outside”; every identified teaching, office, study and similar occupied room has exterior-window coverage.
- All openings are hosted, doors stand exactly at floor level, and window sill/head heights are consistent across every occupied storey.
- Door sizes are suitable: regular doors are approximately 1.029 m nominal, stair/exit doors approximately 1.029 m, pair doors approximately 1.943 m, and lift landing doors exactly 1.200 m nominal.
- Family definitions are appropriate and versioned: Single Flush Door v4, Pair Flush Door v5, centre-opening Lift Landing Door v1, and two-panel Casement Window v6.
- The automatic opening check of the whole model reports 182 doors, 494 windows and zero rule findings, including no inward-opening casements, undersized openings or unfire-rated stair doors.

### What was wrong

- Moving-leaf and sash collision sweeps were not independently assessable; 172 opening measurements note that leaf position is estimated from the family hand.
- The agent could not provide the requested final representative capture because the screenshot failed, although the same failure happened during the review and does not undermine the measured model.

### Measured evidence

Live measurements found 182 doors and 494 windows, with 182/182 doors and 494/494 windows hosted. Door bottoms exactly match each storey floor; every window has a 0.908 m sill, 1.841 m height and 2.749 m head, while the measurements show all casements open toward “outside,” stair doors open into stair reservations, exterior exits open outside, and all ten lift doors are sliding with 1.200 m nominal width. The agent’s claim, “I've added **182 doors and 494 windows**,” matches the live recount.

The full review is in [`results/2026-11-15_v1.0/reviews/university-building.json`](../../results/2026-11-15_v1.0/reviews/university-building.json).

## 5. Self-fixes

The agent ran the automatic checks while it worked, and fixed what they found.

| Check | Found at first check | Left at last check |
| --- | --- | --- |
| Door opens against a wall | 2 | 0 |

---

Disagree with this score? [Open a score dispute](../../../../../../issues/new?template=dispute-score.yml).
