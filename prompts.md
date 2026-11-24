# Prompts

Store project prompts here.

## 2026-11-23

### Request 1
- **Asked:** Set up the project folders for a single-file web app, keeping `AGENTS.md`, `spec.md`, `prompts.md`, and `index.html` at the top level. Create `00_planning`, `01_data`, `02_validation`, and `03_output` with short README files, describe the layout in `AGENTS.md`, and add the file-placement rule.
- **Changed:** Created the top-level files and all four numbered folders with README files. Added layout and file-placement instructions to `AGENTS.md`.
- **Worked:** Yes. The layout was created and verified.

### Request 2
- **Asked:** After each request, add an entry to `prompts.md` recording what was asked, what changed, and whether it worked.
- **Changed:** Added this prompt-log entry format to `prompts.md` and recorded the folder setup and current logging request.
- **Worked:** Yes.

### Request 3
- **Asked:** Review `spec.md` in plan mode and identify missing considerations or improvements for a keyboard-operated tower crane game.
- **Changed:** Reviewed the specification and repository guidance, with no app or specification files modified. Prepared a requirements and implementation plan covering gameplay, crane physics, controls, scoring, validation, accessibility, and responsive behavior.
- **Worked:** Yes.

### Request 4
- **Asked:** Implement the prior recommendations for coordinate layout, capacity calculations, simple percentage tipping, simplified gameplay, controls, scoring, crane limits, responsive behavior, validation, and accessibility.
- **Changed:** Replaced `spec.md` with a concrete simplified specification covering the crane coordinate system, controls, percentage capacity, 90% warning and 100% tipping, fixed loads and 3-minute game loop, scoring, test cases, responsive layouts, touch controls, and basic accessibility.
- **Worked:** Yes.

### Request 5
- **Asked:** After every significant code change, summarize the change in a local commit message and do not push it.
- **Changed:** Added the Git workflow rule to `AGENTS.md`, including commit-after-significant-change and no-push instructions.
- **Worked:** Yes.

### Request 6
- **Asked:** Read `spec.md` and provide a short overview of the app plus a 3-to-5-stage build plan beginning with a page-layout mockup.
- **Changed:** Reviewed the specification and prompt log. No app code or specification content was changed; prepared an implementation plan for the mockup and subsequent gameplay stages.
- **Worked:** Yes.

### Request 7
- **Asked:** Execute Phase 1 by building the static page-layout mockup.
- **Changed:** Replaced the placeholder `index.html` with a responsive desktop/mobile mockup containing the crane worksite, staging area, building, side view, load chart, timer, score, capacity panel, delivery status, and control bar.
- **Worked:** Yes; layout was added without implementing gameplay.

### Request 8
- **Asked:** Execute Phase 2 by adding crane movement and live visual feedback.
- **Changed:** Added held-key and touch controls for trolley, hook height, and crane rotation; enforced radius and height limits; synchronized the map and side-view hook positions; added live radius, height, and capacity status; and added normal, 90% warning, and 100% tip feedback. Added a temporary F/Space demo-load toggle for testing capacity states.
- **Worked:** Yes; the app served locally and the implementation was committed.

### Request 9
- **Asked:** Explain in simple terms what went wrong while implementing Phase 2.
- **Changed:** Reviewed the Phase 2 work and prompt history. No app code was changed; prepared an explanation of patch-context, browser-validation, and verification difficulties.
- **Worked:** Yes.

### Request 10
- **Asked:** Execute Phase 3 by adding real load pickup and drop behavior.
- **Changed:** Replaced the demo-load toggle with three fixed loads, staging and building zone checks, attached-load capacity updates, successful delivery counting, hidden staging loads after pickup, and a local tip-over end panel with restart. The implementation is in place pending verification and commit.
- **Worked:** Yes; the source changes and Git diff were checked before the local commit.

### Request 11
- **Asked:** Execute Phase 4 by completing the timer, scoring, end states, best-score storage, responsive behavior, and accessibility behavior.
- **Changed:** Added a three-minute countdown, 100-point delivery scores, remaining-time bonuses, time-expiration and win/loss dialogs, local best-score storage with a session fallback, and timer/score live status updates. Implementation is in place pending final source verification and commit.
- **Worked:** Yes; the final source markers and Git diff passed before the local commit.

### Request 12
- **Asked:** Make the crane controls faster and fix inability to rotate the crane.
- **Changed:** Increased trolley, hook, and rotation speeds; added Q/J and E/L keyboard rotation aliases; clarified rotate touch buttons; added a live angle readout; and visually rotated the crane jib and hook position. Verification and commit are pending.
- **Worked:** Yes; source checks passed before the local commit.

### Request 13
- **Asked:** Run the website and complete it, move the staging and building areas closer, label loads with weights, and make the timer count down live.
- **Changed:** Moved staging and building visually closer to the crane, mapped radius zones to staging and building positions, added visible 350 lb, 340 lb, and 360 lb load labels, and updated the timer display every frame. Browser testing completed all three deliveries and opened the win dialog.
- **Worked:** Yes; the timer counted down, all loads delivered successfully, and the final score was 1970 points.

### Request 14
- **Asked:** Make the crane, load, staging, and building displays accurately reflect the shared X/Y position instead of independent estimates.
- **Changed:** Added a shared crane X/Y/Z model based on radius and angle, synchronized the map hook and crane jib with X/Y, synchronized the side view with radius and height, moved staging and building to shared map coordinates, added X/Y/Z/angle readouts, and made attached loads follow the hook. Delivered loads now remain labeled on the building.
- **Worked:** Yes; browser testing delivered all three loads and showed the win dialog with accurate X/Y/Z and angle readouts.

### Request 15
- **Asked:** Review the specification for Phase 5 clarifications, and execute Phase 6 by correcting crane appearance and slowing controls.
- **Changed:** Added Phase 5 clarifications for construction workers, load sliders, crane alignment, and control behavior. Updated the crane base to meet the brown ground section, added a visible trolley and cable connection to the jib, and reduced trolley, hook, and rotation speeds by 15%. Browser verification and commit are pending.
- **Changed:** Browser testing confirmed the slower controls, crane trolley, cable, and brown ground alignment. A staged load attached successfully and the crane base measured at the brown section boundary.
- **Worked:** Yes; verified the crane appearance and slowed controls before the local commit.

### Request 16
- **Asked:** Make the wire visibly and physically connect from the top of the crane to the yellow trolley and crane.
- **Changed:** Moved the yellow trolley inside the jib, added a trolley hanging-point detail, and positioned the cable dynamically from the trolley's actual bounding position down to the hook. Browser verification and local commit are pending.
- **Changed:** Browser geometry verification confirmed the cable starts within 3 pixels of the trolley center and extends from its lower edge.
- **Worked:** Yes; the trolley-to-cable connection was verified before commit.

### Request 17
- **Asked:** Stop broad crane redesign and improve only the bucket, wire, trolley, and crane connections for seamless play.
- **Changed:** Added visible jib end hardware, trolley wheels and hanging block, a clearer hoist block and J hook, and aligned the cable and hook directly under the trolley while keeping the crane layout and gameplay unchanged. Verification and commit are pending.
- **Changed:** Browser screenshot and geometry verification confirmed the trolley, cable, hoist block, hook, and crane assembly remain visually connected.
- **Worked:** Yes; the focused connection improvements were verified before commit.

### Request 18
- **Asked:** Complete a full browser run-through and test every app function for proper use.
- **Changed:** Audited keyboard and touch controls, pause/resume, restart, movement limits, staging pickup, building drop, all three deliveries, scoring, timer, 90% warning, 100% tipping, and restart after tip. No app code was changed; prepared a malfunction report and implementation recommendations.
- **Worked:** Yes; the core delivery run and edge-state tests completed successfully.

### Request 19
- **Asked:** Fix the visual model so the crane hook can visibly reach the staging area and rotate 360 degrees.
- **Changed:** Updated jib, trolley, cable, hook, and attached-load visuals to use a shared 360-degree crane angle and radius. The hook now projects left for the staging side and right for the building side. Browser verification and commit are pending.
- **Changed:** Anchored low-height staging/building hook positions to the actual staging-load and building rectangles, while retaining continuous 360-degree radial movement elsewhere.
- **Changed:** Browser geometry confirmed the hook is inside the staging zone at X=-55 ft and inside the building zone after rotation; 360-degree angle changes moved the hook across left, rear, and right positions.
- **Worked:** Yes; staging reach and 360-degree visual rotation were verified before commit.

### Request 20
- **Asked:** Simplify the crane visuals, remove visual bugs, and keep the app smooth and functional.
- **Changed:** Removed conflicting angle/radius projection logic and reduced the crane to one direct radius-to-horizontal-hook model. Zone snapping now applies only when the hook is in staging or building range, and jib rotation is lightly damped.
- **Changed:** Browser verification confirmed the hook is inside the staging zone for pickup and inside the building zone for drop, with successful first-load delivery.
- **Worked:** Yes; simplified visual behavior was verified before commit.

### Request 21
- **Asked:** Fix the hook being visually far from the crane and disconnected from the wire.
- **Changed:** Switched the hook and cable to the trolley's actual screen position, constrained the trolley to the jib, and kept the jib fixed for a mechanically simple side view. Browser verification and commit are pending.
- **Changed:** Browser geometry confirmed trolley, cable, and hook share the same vertical axis with less than 5 pixels of offset at staging and building positions.
- **Worked:** Yes; the hook and wire connection were simplified and verified before commit.

### Request 22
- **Asked:** Execute Phase 5.
- **Changed:** Added two moving construction workers on the building, worker collision detection with a skull and restart dialog, and three 300–400 lb load sliders with 10 lb steps that update staging labels and attached capacity. Browser verification and commit are pending.
- **Changed:** Browser testing confirmed moving workers, slider updates at 300/390/400 lb values, live attached capacity, worker-hit dialog, skull visibility, and restart cleanup.
- **Worked:** Yes; Phase 5 was verified before the local commit.

### Request 23
- **Asked:** Decrease the construction workers to one.
- **Changed:** Removed the second worker and all second-worker state, movement, and collision references while retaining the first worker's movement, collision, skull, and restart behavior.
- **Changed:** Browser verification confirmed one construction worker remains and worker motion continues.
- **Worked:** Yes; the single-worker Phase 5 change was verified before commit.

### Request 23
- **Asked:** Decrease the construction workers to one.
- **Changed:** Removed the second worker element and all second-worker state, movement, and collision references while preserving one moving worker, collision detection, skull, and restart behavior.
- **Worked:** Pending browser verification and commit.
