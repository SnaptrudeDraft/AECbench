# Four-storey community school

Case `school4` · Doors and windows v1.0

## 1. The building

- **Type:** Four-storey community school
- **Floors:** 4
- **Rooms:** 73
- **Start:** Whole-building recorded BIM layout; zero starting openings; reserved vertical cores.
- **Data:** [`building.json`](building.json) has every room, core and access link, in metres. [`case.json`](case.json) lists the known limits of this building.

## 2. The request

> Add doors and windows to this Four-storey community school.

This is all the agent gets. There is no answer key: no hidden door count, door type or swing.

## 3. What the agent made

- **138 doors** and **167 windows** on 4 floors.

![Ground floor plan of the finished model](plan.jpg)

*Ground floor plan of the finished model, in Snaptrude.*

<details>
<summary><b>The agent's final message to the user</b></summary>

I've added 138 doors and 167 windows across the four floors. No furniture was added, since you asked for openings only.

**Doors**
- **Room doors:** each room opens off the main corridor through a 1.0 m door with a vision panel, swinging into the room. Larger rooms get 1.5–1.8 m double doors: reception, dining room, drama studio, ensemble rehearsal and the student common room.
- **Cores at each end:**
  - The stair doors open off the south core lobbies. They are fire-rated (60 min) and open into the stair.
  - Each lift gets a 1.2 m sliding landing door onto its lobby.
  - The core toilets and services stores open off their lobby.
  - Each lobby has 1.5 m double doors from the corridor; the two south ones are fire-rated.
- **Connecting doors:**
  - Servery ↔ dining room, and kitchen ↔ servery.
  - Each science prep room ↔ its lab.
  - Art materials store ↔ art studio, and costume store ↔ drama studio.
  - Equipment store ↔ hall.
- **Ground-floor exits (8):**
  - A main entrance pair of doors with glazed sidelights on the south front, into reception.
  - A fire-rated exit straight outside from each stair.
  - Double doors at both ends of the corridor.
  - Two hall exits to the north.
  - A kitchen service door.

**Windows**
- **Teaching rooms and offices:** two 2.1 × 1.8 m casements each, 0.9 m sill, about 1/8 of the floor area. The quiet sensory room has one smaller, higher window.
- **Hall:** five 2.4 m casements set high (1.2 m sill).
- **Toilets:** small top-hung windows at 1.8 m.
- **Lobbies and upper corridor ends:** fixed glazing.
- Every opening window opens outward.

**What I fixed:** every door was read back and swings the right way. I flipped the hinge to the wall side on 31 single doors.

**Checks**
- **Openings, met:**
  - 138 doors and 167 windows, each placed in one batch per floor.
  - Every room has a door: 125 of 125.
  - Every room people use for long periods has a window in an outside wall: 63 of 63.
  - Which way each door opens was read back for all 138; 0 needed reversing.
  - Window sashes opening into the room: 0.
- **Door swings into the corridor, not met — intentional, 3 doors:**
  - The accessible changing room door opens outward, which is the standard rule for accessible toilets.
  - The two hall doors open into the corridor because the hall is a large assembly space (about 240 m²).
- **Access, partly verified:**
  - Ground floor: 30 of 30 rooms reachable from the entrances.
  - Upper floors: every room is reached from its own corridor (29 of 29, 33 of 33, 33 of 33).
  - The check can't link the floors to each other. Each floor's stair room has a different name (S1…, S2…), so it doesn't see them as the same stair.
- **Overlaps between elements, not met:** on each floor the overlap check ran but did not finish, leaving 251 pairs it couldn't decide.
  - **Doors vs floor finishes, 260 overlaps:** every door's frame dips slightly into the floor finish on each side (at most about 1.7 litres).
  - **Windows vs their own wall, 167 overlaps:** each window's sill trim tucks into its wall (at most 0.06 litres).
  - These come from how the door and window designs are built, not from misplaced openings. I left them as they are.
  - There were no door–door or door–window clashes and no duplicates. The model has no columns, so door–column and window–column don't apply.
- **Element types and leftover sketches, met:** stand-in blocks used in place of real elements: 0. Leftover sketch rooms over finished rooms: 0.
- **Not part of this pass:** I changed no walls, slabs, roofs or structure, and added no furniture.
- **Stairs (VC):** the stair rooms are empty — there are no stairs in them yet. That's why the 3 "no stair between storeys" findings were already in the model before this pass.

My 3D picture of the result didn't capture, and the ground-floor plan view came out cropped, so I haven't seen the finished model as a whole.

**Next steps you could ask for:**
- Put stairs in the two stair rooms, with openings cut through the floors above.
- Furnish the classrooms, labs and toilets.
- Rename stacked rooms the same on every floor (e.g. "West stair"), so the access check can test the whole building.
- Apply façade and glazing materials.

</details>

## 4. The review

**Score: 9 / 10**

The opening task is comprehensively delivered across all four occupied storeys: the live model contains 138 doors and 167 windows, all 305 openings are hosted, all 125 rooms have doors, and no identified habitable room lacks an exterior window. The remaining concerns are minor quality issues—window-head heights vary within each storey, and moving-leaf clearance was not assessable—rather than functional defects.

**Problems left that the automatic checks found:** 1

### What was right

- Complete whole-building coverage on every occupied storey, not merely the ground floor.
- All 305 doors and windows return a wall host; no unhosted opening was found.
- Every one of the 125 rooms has at least one door, with no doorless room on any floor.
- No identified classroom, office, learning room, library, laboratory, studio, hall or similar habitable room lacks an exterior window.
- No internal room-to-room windows were found; all 167 windows face outside.
- Opening functions are suitable: room doors are generally swinging, lift landing doors are sliding and 1.20 m nominal, and exterior casement/awning windows open outward.
- Door widths are generous: measured nominal widths are approximately 1.11, 1.20, 1.61 and 1.91 m depending on function.
- The accessible changing-room door opens into the corridor, but this is a coherent outward-opening exception for an accessible changing use rather than a general swing error.
- Agent-reported totals—“138 doors and 167 windows”—match the live model exactly.

### What was wrong

- Window heads are not aligned to one consistent height per storey; two or three head levels occur on each occupied floor.
- Moving leaf and sash sweeps against nearby fixtures or opposing leaves were not assessable from the opening measurements.
- The prose describes ordinary doors as “1.0 m,” while the measurements show about 1.115 m nominal including the authored frame/trim convention; this is imprecise but not treated as fabrication.
- The agent acknowledged that it had not visually reviewed the whole finished model: “I haven't seen the finished model as a whole.”

### Measured evidence

Measured opening coverage: storeys 1–4 contain respectively 41/40, 28/37, 35/46 and 34/44 doors/windows. The access check found 125 rooms with 0 rooms lacking doors; habitable-window checks found 0 missing across 12, 13, 12 and 9 habitable rooms by floor. Window heads vary by storey (S1: 2.39/2.69/2.99 m; S2: 2.39/2.59/2.69 m; S3–S4: 2.39/2.69 m).

The full review is in [`results/2026-11-15_v1.0/reviews/school4.json`](../../results/2026-11-15_v1.0/reviews/school4.json).

## 5. Self-fixes

The agent's checks found no door problems to fix while it worked.

---

Disagree with this score? [Open a score dispute](../../../../../../issues/new?template=dispute-score.yml).
