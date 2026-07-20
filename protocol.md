# Light-Sheet Microscopy Protocol

Related pages: [Relevant Fish Lines](relevant_fish_lines.md) · [Microscopy Components](microscopy_components.md)

## Overview

1. Fish embedding in agarose
2. Aligning the laser and objective
3. Aligning the sample to the laser and objective
4. Imaging the prepared zebrafish nervous system

---

## Preparing Agarose

### Materials
- low-melting point agarose powder
- dish
- distilled water
- glass screw top bottle
- water bath (37–42 °C) or hot plate
- microwave
- test tubes
- pipette

In order to attain clear images, while still maintaining a high enough density to entrap the fish that you are trying to image, it is important to select a percentage of agarose that strikes a happy medium. The concentration that this lab has settled on is a 1.5% weight vs. volume ratio of agarose to distilled water. This equates to **1.5 g of agarose per 100 mL of water** and scales proportionately.

1. Combine agarose and system H₂O according to the 1.5% proportion (**1.5 g of agarose per 100 mL of water**) in a screw top bottle.
2. Heat the agarose mixture in the microwave until the agarose is completely dissolved and the solution becomes clear. This should be accomplished in the following manner to avoid damaging the mixture: heat the glass bottle in the microwave for ~30 seconds at a time, swirling the mixture around between heating sessions. **Watch carefully while microwaving so it does not bubble over.**
3. Once dissolved and clear, distribute the melted agarose into individual test tubes (fill ¾ of the tube). Cover individual test tubes with parafilm to avoid contaminants.
4. Place all test tubes in the temperature-controlled fridge by the incubator.

---

## Embedding the Zebrafish Larvae (Part 1)

### Materials
- water bath (37–42 °C) or hot plate
- microwave
- one test tube with agarose solution

Here, we will reheat the agarose solution which will be used to embed the larval zebrafish later in the protocol. Doing this step early allows time for the solution to cool down after reheating in the microwave, so you do not cook your fish.

1. Select a single agarose test tube from the fridge. Place this tube in the microwave for 5 seconds at a time until the center of the agarose solution melts, i.e. turns clear. Once this happens, only heat the tube 2 to 3 seconds at a time, inspecting the tube between heating sessions. If this process is done too quickly, the top portion of the agarose will pop off in the microwave and you will lose half of your solution.
2. Once the agarose has melted all the way through, maintain the agarose's temperature by placing the test tube in a 37–42 °C water bath, or onto a heating block. Leave the tube in this heat bath for a few minutes to allow the agarose to cool off.

---

## Aligning the Objective to the Laser

### Principle Rules
1. Do not hit the objective against any other object — it is expensive, and scratches on the objective will negatively affect image quality.
2. After using any solution which comes in contact with the objective, clean the objective. This can be done by either creating a small bath of distilled water and dipping the objective in, or by using a lens cleaner with a lens cleaning solution.

### Materials
From the prep room, you will need the following items:
- sample housing — Hein drawer
- fluorescein — fridge
- pipette — top shelf above Hein drawer
- distilled water — sink

### Light-Sheet Room
1. **Turn on both power adapters.**
   Devices connected to power adapters:
   - cooler fan for laser
   - 2 mysterious cables that also lead to the back of the cooler fan housing
   - camera cooler
   - camera power cable
   - piezo controller — controls the z-axis for the objective
   - X-axis controller for the sample stage (Thorlabs LTS Long Travel Stage)
   - power cable for laser box
2. **Turn the laser on.** Flip the laser switch at the back of the laser's housing into the "on" position. You should see the "Power" light turn on.
3. **Turn the camera on.** Flip the switch on the camera at the top of the scope.
4. **Turn on the computer and associated large monitor.**
   - Click the desktop app called "HHMI ZebraScope". A drop-down menu will appear.
   - Click "Project VIs" in the drop-down menu.
   - Right-click "ZebraScope GUI & major module launcher.vi"
   - Click "Run"
   - The program should start.

   *Make sure to turn on the camera prior to opening the program. If you do not, there will be an error once you click "Start Acquisition (F1)".*
5. **Turn on the laptop.**
   - This laptop controls the laser box. The laser housing contains 4 different wavelength lasers, and this laptop lets you select which laser to use as well as modulate its power.
   - The password to the laptop is '12zfish34'.
   - On the laptop, select the "Omicron Control Center" app.
   - Once the app opens, select the 488nm laser in the upper section.
   - Under optical output power, select a "set-point" between 5 and 15%. The goal is to get good image resolution while not hurting the fish.
6. **Prepare the sample housing.**
   - Place the sample housing securely in the sample housing stage beneath the objective. If nudged, the sample housing should not move.
   - Pipette the fluorescein into the sample housing until there is a meniscus of fluorescein above the objective.
   - Raise the stage on which the sample is resting to the objective using the coarse step setting on the stage controller. Press the "UP" key to raise the stage until the objective just pierces the fluorescein meniscus. As always, be careful not to hit the objective against any object.
7. **Turn off the lights in the room.**
8. **Enable the laser & camera.**
   - Go to the main computer screen.
   - Select "Scan Mode: Scanning Off." This ensures that the galvanometers are off — in other words, the laser will simply be directed to a single point in the sample. **It will be our goal in this section to align the objective to this lasing point.**
   - Click the "OFF" button near the 488nm laser in the "Lasers" box to "Enable," or open the shutter for the 488nm laser to be emitted. You should not see the laser beam being emitted, hopefully, through some protective goggles.
   - Check that the laser line is unobstructed — make sure the laser is able to reach the beam block on the other side of the sample housing.
   - Now, click "Start Aquisition (F1)" at the upper left of the GUI. This will enable the camera to start capturing.
9. **Align the objective to the laser.**
   - You made it!! This is the main purpose of this section. You want to align the focus point of the laser to the center of the camera. Let me talk you through this.
   - At this point, you should see a glowy green gaussian distribution line across the screen of the camera GUI. In actuality, the laser is shaped like a bowtie where the center is the point of focus. If you do not see the laser on the camera screen, make sure that the camera is fully zoomed out and that there are no scroll bars to the sides of the camera screen.
   - On the microscope, you will see two manual adjustment knobs, one for X positioning and the other for Y positioning. Adjust them until the laser line is roughly centered on the camera GUI. Follow the descending slope of the gaussian line to get to the center focus.
   - Now, to adjust the focus depth of the system, i.e. vary the distance between the objective and the sample, adjust the objective position using the main computer GUI. Turn to the "Target tilt 1" square and adjust the Z position back and forth. A good starting point is adjusting ±10 either way.
   - Once the focus is roughly in the center of the screen, adjust the camera zoom to -3 in both the X and Y directions. Adjust the Z position until the vertical width of the focus of the laser beam is ~15 pixels wide.
   - Place your cursor at the center of the image being captured (1024, 1024). The cursor's location will be displayed beneath the image being captured. In total, the image dimensions are 2048 by 2048 pixels.
   - Using the X and Y knobs, bring the focus precisely to the center of the image being captured, i.e. where you placed your cursor.
   - You have now aligned the laser beam to the objective!!
10. **Clean the objective from the fluorescein.**
    - This can be done by either creating a small bath of distilled water and dipping the objective in, or by using a lens cleaner with a lens cleaning solution.

---

## Embedding the Zebrafish Larvae (Part 2)

### Materials
- water bath (37–42 °C) or hot plate
- one test tube with agarose solution
- pipette
- zebrafish larvae (6 to 7 days post-fertilization)
- sample housing for microscope
- fine probe or forceps for positioning larvae

Here, we will embed the zebrafish larvae. This step comes after the objective-to-laser alignment because we want to prepare the sample as close to the imaging step as possible, since the larvae are still alive in the agarose and therefore capable of movement.

At this point (from Part 1), a test tube with melted agarose solution should be ready.

1. Before use, briefly touch the outside of the test tube to your upper lip to test the temperature. If you can withstand the heat of the tube for 5 seconds, the agarose is ready to use. This is critical to avoid cooking the fish.
2. Place a 35mm petri dish under the embedding scope.
3. Place the ice-cream nail decal mold on top of the petri dish. The middle ice-cream decal is a good shape to fit into the sample housing that you will mount in the microscope.
4. Pipette a larval zebrafish. Release as much water as possible back into the larvae petri dish — the goal is to have as little water in the pipette as possible.
5. Deposit the pipetted zebrafish in the tube containing the agarose. If the agarose mixture is well made and properly heated, the fish will be able to swim in the tube, meaning the solution is not too thick and the fish isn't cooked.
6. Now, pipette the larval zebrafish back up from the tube and release it into a **rectangular** ice-cream mold.
7. **Position the larval zebrafish in the agarose.** Using the probe, finesse the larva so that it is positioned as parallel to the sides of the mold as possible while minimizing the pitch and yaw angle. This is critical — when imaging, you will want the fish's brain to be as orthogonal as possible to the objective above. Keep moving the fish while the agarose has yet to solidify, without touching the fish; this will require practice. It is also important to avoid moving the fish once the agarose has solidified, as this will cause the agarose to form cracks and bubbles.
8. **Remove the agarose block from the mold with the embedded fish.** Wait until the agarose has solidified. Use the probe to outline the perimeter of the mold. Once outlined, bend the rubber mold back to completely separate the agarose block from the mold. Take a large blade and slide it under the block to move it onto the petri dish.
9. Cut the sides of the agarose block around the fish, being careful not to hurt the fish.
10. **Mount the prepared agarose-larva block into the sample housing.** First, pipette a thin layer of agarose onto the beam in the sample housing as an adhesion layer. Wait a few seconds for this layer to solidify. Pick up the prepared agarose-larva block and deposit it on top of the thin layer of agarose. The fish should face the direction of the mount that is not connected to the wall. Once placed, deposit a thin layer of agarose over the agarose-larva block to make the sample sturdier.

---

## Aligning the Sample to the Objective & Laser

### Materials
- mounted zebrafish larvae in sample housing
- bottle of facility water

1. **Position the sample.** Bring the mounted zebrafish sample housing into the light-sheet room. Mount the sample housing beneath the microscope. Pour the system water into the sample housing until there is once more a meniscus formed over the housing.
2. **Switch the laser to a scanning mode.** At the top of the GUI, set "Scan Mode: Current Ch & Pos." This will now allow the focused laser to start scanning.
3. **Start acquiring images.** Click "Start Acquisition (F1)."
4. **Use the controller to raise the stage and align the zebrafish larvae to the objective.**
   - Walk over to the microscope and sample, and roughly center the sample to the objective using the medium step on the controller.
   - Then, look at the camera GUI and

*(Note: this section is still a work in progress — the final alignment step and confirmation criteria below still need to be connected.)*

You know the sample has been aligned when you can see the ears of the zebrafish in focus.

---

## Taking Z-Stack Images

1. Switch the "Scan Mode:" to "Experiment"
...

### Checking Produced Images on ImageJ

*(This section is still a work in progress.)*
