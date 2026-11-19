# Laboratory

Case `laboratory-building` · Doors and windows v1.0

## 1. The building

- **Type:** Laboratory
- **Floors:** 4
- **Rooms:** 100
- **Start:** Whole-building recorded BIM layout; zero starting openings; reserved vertical cores.
- **Data:** [`building.json`](building.json) has every room, core and access link, in metres. [`case.json`](case.json) lists the known limits of this building.

## 2. The request

> Add doors and windows to this laboratory-building.

This is all the agent gets. There is no answer key: no hidden door count, door type or swing.

## 3. What the agent made

- **214 doors** and **194 windows** on 4 floors.

![Ground floor plan of the finished model](plan.jpg)

*Ground floor plan of the finished model, in Snaptrude.*

<details>
<summary><b>The agent's final message to the user</b></summary>

I added 214 doors and 194 windows across all four floors. Rooms are not furnished: you asked for openings only.

**Doors**
- **Every room has a door off a corridor:** a gallery, a lab access spine or the lift lobby. All 214 swing the way they should. I checked each one after placing it, and none needed flipping.
  - Labs, seminar rooms, the workshop, stores, waste and wash/prep rooms have 6′-0″ (1.83 m) pair doors.
  - Offices and support rooms have 3′-0″ (0.91 m) single doors.
  - Larger rooms with a second corridor wall or a long gallery wall get a second door.
- **Corridors connect to each other:** pair doors join the front gallery to the west, central and east spines and to the lift lobby. Each spine also joins the rear logistics gallery.
- **Stairs:** both stairs have 60-minute fire-rated pair doors off their spine on every floor, opening into the stair. On the ground floor each stair also has its own fire-rated door straight outside.
- **Lifts:** lifts A and B have centre-opening sliding landing doors, 1.2 m wide, facing the lift lobby on every floor.
- **Ground-floor entrances:** all of these open outward.
  - The main entrance is a pair door into the Public science reception, on the front facade.
  - There is a door at each end of the front arrival gallery.
  - There is a service door at each end of the rear logistics gallery.
  - There is a loading door into Receiving and consumables.

**Windows**
- Every room people work in that has an outside wall or a courtyard wall gets fixed two-panel windows. That covers labs, offices, meeting rooms, the library, lounges and so on.
- Each window is 6′-0″ × 6′-0″ (1.83 m square) with a 3′-0″ (0.91 m) sill. There is roughly one per 10′ (3 m) of wall.
- The reception has windows on either side of the entrance.
- No windows in the stairs, lifts, washrooms, waste holding, equipment stores, building support, receiving or the internal corridors.

**Check card**
- **Access (CA):** all 164 rooms have a door and none is cut off.
  - On the ground floor, all 41 rooms can be reached from the entrances, and both stairs lead straight outside.
  - The upper floors couldn't be tested. The stair and lift rooms are named per floor ("F02-…"), so the check can't tell they stack, and the stairs themselves aren't modelled yet. On the plan, every upper-floor room opens onto a corridor.
- **Openings (BA):** one batch of doors and one of windows per floor; nothing was refused. All 214 doors read back opening into the intended room or outside, with nothing flipped. Lift doors are sliding.
- **Model check:** no new findings. These were already in the model before I started:
  - 3 × "no stair between floors": the stair rooms are still empty.
  - 4 × unexplained slab holes.

I couldn't take a final picture: the canvas failed to capture twice. The openings are in the model, so check them on screen when you open it.

**Next steps you could ask for:**
- Place stairs in the two stair rooms so the upper floors have real escape routes.
- Rename the stair and lift rooms the same on every floor, so the access check can verify the whole building.
- Fit out the labs, offices and washrooms.
- Swap any window size or door type, e.g. full-height glazing on the front facade.

</details>

## 4. The review

**Score: 9 / 10**

The opening package is comprehensive and technically sound across all four occupied storeys: every one of the 164 rooms has a door, all 100 occupied rooms checked have exterior windows, all 408 openings are hosted, and the opening check reports no findings. The only material reservation is an overbroad verification claim about every door swinging/opening into a room or outside, although eight lift doors are sliding doors, which open into neither side; moving-leaf clearance and instance fire-rating values were not independently assessable.

**Problems left that the automatic checks found:** 0

### What was right

- Complete opening coverage on every occupied storey, not merely the ground floor.
- All 164 rooms have at least one door; the 41 ground-floor rooms are reachable from the exterior entrances.
- Every assessed occupied room has daylight from an exterior window: 25 of 25 on each of floors 1–4.
- All 408 openings are hosted; no unhosted opening was measured.
- Door operations and orientations are coherent: room doors open into their rooms, stair doors open toward the stair or exterior, and lift doors are sliding.
- Door sizes are generous: 92 single-swing doors at 1.029 m nominal, 114 double-swing doors at 1.943 m nominal, and eight 1.2 m lift doors.
- Window heads and sills are consistent by storey, with approximately 0.908 m sills and 2.749 m heads above each floor datum.
- Suitable families were present for pair flush doors, single flush doors, centre-opening lift doors, and fixed two-panel windows.

### What was wrong

- The final verification language incorrectly groups the eight non-swinging lift doors with doors opening into a room or outside; a sliding door opens into neither side.
- Moving-leaf and sash sweep against nearby fixtures or walls was not independently assessed.
- The claimed 60-minute ratings were not independently confirmed from the settings of the placed doors, although the opening check reported no fire-rating finding.

### Measured evidence

Live measurements found 214 doors and 194 windows: floor counts were F01 59/48, F02 52/50, F03 50/48, and F04 53/48. The access check found 164 rooms, none without a door; all 25 occupied rooms on each floor had at least one exterior window; every opening sits in a wall; windows had consistent 0.908 m sills and 1.842 m square geometry. The agent claimed, “All 214 doors read back opening into the intended room or outside,” while the eight verified lift doors are sliding doors, which do not open into either side.

The full review is in [`results/2026-11-15_v1.0/reviews/laboratory-building.json`](../../results/2026-11-15_v1.0/reviews/laboratory-building.json).

## 5. Self-fixes

The agent's checks found no door problems to fix while it worked.

---

Disagree with this score? [Open a score dispute](../../../../../../issues/new?template=dispute-score.yml).
