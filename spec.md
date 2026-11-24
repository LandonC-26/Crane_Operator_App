# Project Specification

# Your App's Name
Crane_Operator_1

## Purpose
This app will operate a tower crane with the keyboard. The player picks up loads from a staging area and places them on a building under construction before time expires, without reaching 100% crane capacity.

## Inputs
- L = Load weight in pounds.
- R = Radius from the crane in feet.
- LB = Rated crane capacity at the current radius in pounds.
- P = Percent capacity used.

The app uses only predefined game values. The player does not enter a load weight or crane capacity manually.

### Crane layout
- The crane pivot is a fixed point at the center of the work area.
- X is horizontal position to the left or right of the crane pivot.
- Y is position on the overhead map.
- Z is hook height above the ground.
- Hook radius is limited to 50 to 150 feet.
- Hook height is limited to 0 to 300 feet.
- Radius guides are marked at 50, 75, 100, 125, and 150 feet.
- The hook starts centered over the staging area at a safe height.

### Keyboard controls
- A / D: move the trolley left or right, changing R and X.
- W / S: raise or lower the hook, changing Z.
- Q / E: rotate the crane in the overhead plane, changing Y.
- F or Space: pick up or set down a load.
- P: pause or resume.
- R: restart after confirmation.
- Left / Right arrows: trolley.
- Up / Down arrows: hook height.

The controls use held-key movement at a fixed speed. The interface shows every control.

## Calculations
Calculate the percentage of crane capacity used by the attached load:

```text
P = (L / LB) * 100
```

LB is looked up from the crane load chart using the hook's current radius R. If R falls between chart radii, use the rating from the lower radius band.

Example:

```text
L = 350 lb
R = 50 ft
LB = 400 lb
P = (350 / 400) * 100 = 87.5%
```

### Capacity bands
- 0 to 89.9%: normal.
- 90 to 99.9%: warning.
- 100% or more: crane tips and the run ends.

The warning state is amber and includes text. The tip state is red and plays a dramatic tip-over animation.

There is no swinging-load physics. The crane hook and load move directly to the same position. Weather and dynamic-load multipliers are ignored.

### Crane limits
- Trolley movement speed: 20 feet per second.
- Hook lift/lower speed: 15 feet per second.
- Rotation speed: 30 degrees per second.
- Movement stops at the 50-foot and 150-foot radius limits.
- Hook height stops at 0 feet and 300 feet.
- Pickup or drop actions work only in a clearly marked close-range zone.

## Outputs
- Side view matching the hook, trolley, and attached load position.
- Overhead or map view showing the crane, staging area, building, hook, and loads.
- Load chart for 50, 75, 100, 125, and 150 feet.
- Timer and cumulative score.
- Live percentage showing capacity in use.
- Faint radius guides at 50, 75, 100, 125, and 150 feet.
- Crane tip-over effect at 100% capacity or more.
- Normal, warning, success, and failure states that use text as well as color.

## Look and feel
On desktop, the crane and map are centered. Controls are on the bottom. Timer and score are on the right. The load chart is beside the side view on the left.

On a phone, timer and score appear at the top. The load chart appears below them. The crane map appears in the center. The side view appears below the map, and controls appear below or beside it.

The layout remains usable on narrow portrait screens and short landscape screens.

The app includes touch controls for mobile while retaining all keyboard controls. Touch controls do not require simultaneous presses.

## Simplified game loop
- The round starts with a 3-minute timer and three loads in the staging area.
- Load weights are fixed at 300 to 400 pounds.
- The player moves the hook over a load, lowers it, and presses F or Space.
- The player carries the load to a marked building position and lowers the hook.
- Pressing F or Space again places the load.
- A successful placement adds 100 points plus 10 points per full remaining second.
- A failed drop adds no points and leaves the load attached.
- The round is won after all three loads are placed before time expires.
- The round is lost if the crane reaches 100% capacity or time reaches zero.

## Simplified score and timer
- Starting timer: 180 seconds.
- Successful placement: 100 points.
- Time bonus: 10 points per full remaining second.
- Incorrect drop: no points.
- Tipping or timer expiration: round ends immediately.
- The end panel shows the final score and win/loss state.
- The best score is stored in local storage when available.
- Without local storage, the best score lasts only for the current page session.

## Validation
The app is validated with hand calculations for capacity and simple boundary cases.

Example calculations:

```text
350 / 400 * 100 = 87.5%
360 / 400 * 100 = 90.0%
400 / 400 * 100 = 100.0%
350 / 300 * 100 = 116.7%
```

Required test cases:
- Hook movement stops at each radius and height limit.
- A load can be picked up only while the hook is in the staging zone.
- A load can be set down only at a marked building position.
- An empty hook reports 0% capacity.
- A radius change updates capacity immediately.
- 89.9% remains normal, 90% warns, and 100% tips.
- Warning and tip states include visible text.
- Timer expiration ends the round.
- A successful delivery adds score and removes the load from staging.
- Restart clears score, timer, placements, and crane position.
- Pause stops crane movement and the timer.
- All primary actions work with keyboard and touch controls.
- Desktop and phone layouts remain usable after resizing.
- Rapid pickup/drop presses cannot duplicate an action or load.
- Invalid load data is ignored and does not score or tip.

## Simplified responsive behavior
- Desktop: map and side view in the main area with a right-side status panel.
- Phone portrait: status at the top, map in the main area, side view below, and controls below or beside it.
- Phone landscape: compact status and controls around a larger map.
- The app uses a viewport-aware, scalable layout with readable text.
- Touch buttons are large enough for reliable tapping.

## Simplified accessibility
- Status values include visible text, not only a meter or color.
- Warning and tip states include plain-language text.
- Capacity changes are announced through a live region.
- Success and failure dialogs use plain, visible text.
- Controls have visible keyboard focus.
- Reduced-motion preference disables or reduces crane and tip animation.
- Every primary action is available with keyboard and touch.

## Out of scope
This app does not account for weather, wind, dynamic forces, crane internal forces, load swing, cable stretch, boom deflection, or multi-crane operations.
