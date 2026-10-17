# Images

Every image here is exactly what the models were shown: one camera view of one scene, rendered in Isaac Sim. These are a few examples of what changes between scenes, which cameras can show the answer, and the scenes right on the line.

## What changes between scenes

Each scene changes the step being checked. For the cart, the same overhead camera shows:

| Seated | Off the shelf | Tilted on the edge |
|---|---|---|
| <img src="cart_seated_overhead.png" width="280" alt="Cart from the overhead camera, with the plate flat on the top shelf"> | <img src="cart_off_shelf_overhead.png" width="280" alt="Cart from the overhead camera, with the top shelf empty"> | <img src="cart_tilted_overhead.png" width="280" alt="Cart from the overhead camera, with the plate resting on the shelf’s lip"> |
| The plate sits flat on the top shelf. | The plate fell off, so the shelf is empty. | The plate rests on the shelf’s lip. |

For the pipette, the close-up camera shows where the tip ends:

| In a well | Too high above the plate |
|---|---|
| <img src="pipette_in_well_closeup.png" width="360" alt="Close-up of the pipette tip down in a well"> | <img src="pipette_too_high_closeup.png" width="360" alt="Close-up of the pipette tip above the plate"> |

## When the camera can show the answer, and when it can’t

Each row is one scene seen from two cameras. Only the first camera can show the answer, so the right answer depends on the camera.

| Scene | Camera that shows the answer | Camera that can’t |
|---|---|---|
| **Pipette:** tip too high above the plate | <img src="pipette_too_high_closeup.png" width="300" alt="Close-up of the tip above the plate"><br>Close-up camera. Right answer: “too high above the plate”. | <img src="pipette_too_high_overhead.png" width="300" alt="Overhead view of the bench, where the pipette hides its own tip"><br>Overhead camera: the pipette hides its own tip. Right answer: “can’t tell”. |
| **Grip:** only one arm gripping | <img src="grip_one_arm_end_cameras.png" width="300" alt="The two end cameras side by side, showing where each gripper meets the plate"><br>End cameras, shown side by side: you can see where each gripper meets the plate. Right answer: “only one arm gripping”. | <img src="grip_one_arm_wrist_cameras.png" width="300" alt="The two wrist cameras side by side, where each gripper hides its own contact"><br>Wrist cameras, shown side by side: each gripper hides its own contact. Right answer: “can’t tell”. |
| **Cart:** the plate fell off | <img src="cart_fell_off_overhead.png" width="300" alt="Cart from the overhead camera, with the top shelf empty"><br>Overhead camera: the shelf is empty. Right answer: “off the shelf”. | <img src="cart_fell_off_low.png" width="300" alt="Cart from the low camera, where the shelf’s lip hides the deck"><br>Low camera: the shelf’s lip hides the deck, so a seated plate looks the same. Right answer: “can’t tell”. |

## Scenes right on the line

We intentionally tested 15 scenes right on the line. They count in Figure 1 but are not graded right or wrong (see [How it was tested](../README.md#how-it-was-tested)).

| Tip 1 mm above the plate | Tip resting on a well’s edge | Plate just touching the shelf lip |
|---|---|---|
| <img src="pipette_near_call_hover_closeup.png" width="280" alt="Close-up of the tip hovering just above the plate"> | <img src="pipette_near_call_edge_closeup.png" width="280" alt="Close-up of the tip resting on the edge of a well"> | <img src="cart_near_call_lip_overhead.png" width="280" alt="Cart from the overhead camera, with the plate just touching the shelf lip"> |
