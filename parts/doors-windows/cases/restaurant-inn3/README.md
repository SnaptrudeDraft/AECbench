# Restaurant-led boutique inn

Case `restaurant-inn3` · Doors and windows v1.0

## 1. The building

- **Type:** Restaurant-led boutique inn
- **Floors:** 3
- **Rooms:** 48
- **Start:** Whole-building recorded BIM layout; zero starting openings; reserved vertical cores.
- **Data:** [`building.json`](building.json) has every room, core and access link, in metres. [`case.json`](case.json) lists the known limits of this building.

## 2. The request

> Add doors and windows to this Restaurant-led boutique inn.

This is all the agent gets. There is no answer key: no hidden door count, door type or swing.

## 3. What the agent made

- **98 doors** and **83 windows** on 3 floors.

![Ground floor plan of the finished model](plan.jpg)

*Ground floor plan of the finished model, in Snaptrude.*

<details>
<summary><b>The agent's final message to the user</b></summary>

I've added **98 doors and 83 windows** across the three floors. The model check now has no new findings. I added no furniture, since you only asked for openings.

**Ground (restaurant):** 38 doors, 21 windows
- **Main entrance:** a 15'-9" (4.8 m) glazed automatic sliding door across the reception's south front. It's the smallest size that family comes in, so it takes the whole frontage and the reception has no separate windows.
- **Linked rooms:** pair doors join reception → bar → main dining → hot kitchen → cold prep. Every room also has its own door off the main corridor.
- **Service side (north):** an outward pair door into Receiving and a door straight out of Waste holding. Dry and cold storage opens into Receiving as well as the corridor.
- **Windows:** tall fixed glazing in the bar, main dining and private dining rooms (2'-0" sill, 8'-10" head). Casements above worktop height in the kitchens, high casements in staff changing, and high awnings in the toilets.

**First floor (events):** 32 doors, 25 windows
- Event reception → celebration dining → finishing kitchen → pantry → business dining are linked with interior doors.
- The lounge and dining rooms get tall fixed glazing; the office, staff room and wash-up get casements.

**Second floor (guest suites):** 28 doors, 37 windows
- Each of the 16 suites has an entry door off the corridor and two full-height casements on its outside wall.
- Housekeeping gets a casement.

**Cores (both ends, every floor):**
- 60-minute fire doors between the corridor and the core lobby, and between the lobby and the stair.
- Centre-opening lift landing doors face the lobbies: 3'-11" (1.2 m) for the passenger lift and 4'-7" (1.4 m) for the service lift, which is that family's maximum width.
- WC and store doors open off the lobbies, and the corridor ends get windows.
- On the ground floor each stair lobby has a 1.2 m exit door to the outside.

| Check | Result |
|---|---|
| CA: Access | All 87 rooms have a door; 29 of 29 ground-floor rooms are reachable from the street doors. The first and second floors aren't linked to the ground floor yet, because the stairs are still reservation rooms with no stair object, so the check can't follow them. |
| CA: Doors | 98 doors placed; every swing was read back and opens where intended first time. 20 single doors were re-hinged so they open against the wall beside them. |
| CA: Doors that open outward | The two accessible toilets open into the corridor. The two lobby exits, Receiving and Waste open outside. Upper-floor stair doors open into the stair, in the escape direction. |
| CA: Daylight | Every dining room, bar, lounge, office, staff room, kitchen and suite has an outside window. Stores, the lift shafts and Receiving have none, by intent. |
| CA: Egress | The two stairs are about 56 m apart (well over half the building's diagonal). On the ground floor each stair leads through its lobby straight outside. |
| BA: Openings | 83 window sills and heads checked against the target heights; every casement and awning opens outward. A clash check was not run. |
| Model check | No new findings. Two stair findings were already in the model and remain until the stairs are modelled. |

**One plan point:** the kitchens, stores and Receiving share the main corridor with guests. There is no separate service route, so you may want a back-of-house corridor along the north side.

**Next steps:**
- Place stair families in the four stair reservations so the upper floors connect and can be checked.
- Furnish the dining rooms, kitchens, toilets and suites.
- Apply facade and glazing finishes.

</details>

## 4. The review

**Score: 7 / 10**

The opening task is comprehensively delivered across all three occupied storeys: the live model contains 98 doors and 83 windows, every one is hosted, all 87 rooms have a door, and the opening check reports no swing, width, or operation findings. However, the guest-floor window design needs systemic safety rework: 32 operable suite casements have sills at approximately 0.594 m, materially below the 0.9–1.0 m bedroom guidance, with no verified guarding.

**Problems left that the automatic checks found:** 0

### What was right

- Complete occupied-storey coverage: 38/21, 32/25, and 28/37 doors/windows across storeys 1–3.
- All 98 doors and 83 windows returned valid wall hosts; no unhosted openings were measured.
- Every one of the 87 rooms has at least one door; all 29 ground-floor rooms are reachable from the main entrance.
- Habitable uses receive exterior glazing throughout: restaurant and event rooms, offices, staff rooms, kitchens, and all 16 suites.
- Opening measurements found no undersized doors, unread swinging doors, inward-opening exterior casements/awnings, or other shared-rule findings.
- Lift doors are sliding and measured 1.20 m passenger and 1.40 m service nominal width, opening onto core lobbies.
- Sampled stair and exit doors use the Single Flush Door family with a 60-minute fire rating; the ground exits open outside.
- Window families and sill heights are use-sensitive on the lower floors: toilet awnings at about 1.518 m and office casements at about 0.894 m.

### What was wrong

- All 32 operable suite casements measured approximately 0.594 m above the guest-room floors, below the standard’s 0.9–1.0 m bedroom range and potentially unsafe without guarding.
- Moving-leaf and sash sweep clearance against fixtures or adjacent walls was not independently assessable; the opening measurements verify operation and jamb returns but not full motion sweeps.
- The 4.8 m automatic sliding main entrance is functional and adequately wide but is an oversized catalogue-driven solution rather than a deliberately proportioned entrance assembly.

### Where it breaks the standard

| Rule | What happened | Evidence |
| --- | --- | --- |
| Bedroom windows should have suitable, safe sills, about 0.9–1.0 m. | The two operable casements in each of the 16 guest suites have approximately 0.594 m sills, with no verified guard or restricted-opening provision. | Live bounding-box measurements relative to each suite floor found 32 suite casements at 0.59365 m sill height. |

### Measured evidence

Live measurements found Ground 38 doors/21 windows, First 32/25, and Second 28/37; the access check measured 87/87 rooms with doors and 29/29 ground-floor rooms reachable. On storey 3, 32 casements serving the 16 named guest suites measured about 0.594 m sill height, despite the agent stating: “Each of the 16 suites has an entry door off the corridor and two full-height casements on its outside wall.”

The full review is in [`results/2026-11-15_v1.0/reviews/restaurant-inn3.json`](../../results/2026-11-15_v1.0/reviews/restaurant-inn3.json).

## 5. Self-fixes

The agent ran the automatic checks while it worked, and fixed what they found.

| Check | Found at first check | Left at last check |
| --- | --- | --- |
| Door opens against a wall | 20 | 0 |

---

Disagree with this score? [Open a score dispute](../../../../../../issues/new?template=dispute-score.yml).
