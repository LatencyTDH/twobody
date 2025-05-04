# Enhanced Two-Body Gravitational Simulation

This is an interactive 3D simulation demonstrating the gravitational interaction between two bodies, built using three.js, with enhanced visuals and controls.

## Features

* **3D Visualization:** Shows two celestial bodies orbiting each other in 3D space against a dynamic starfield background.
* **Physics-Based:** Simulates gravitational attraction using Newton's law of universal gravitation ($F = G \frac{m_1 m_2}{r^2}$). Uses simple Euler integration for physics steps.
* **Enhanced Visuals:**
    * Uses `MeshStandardMaterial` for more realistic lighting effects on the bodies.
    * Includes ambient and point lighting, plus an emissive glow for the larger body.
    * Features a background starfield that slowly rotates.
    * Bodies visually scale based on their mass (relative to initial mass).
* **Interactive Controls:** Sliders allow real-time adjustment of:
    * **Gravity (G):** Affects the overall strength of the gravitational pull.
    * **Mass 1 / Mass 2:** Changes the mass of each body, influencing their orbits and visual size.
    * **Speed:** Controls the simulation's time progression (slow-motion or fast-forward).
* **Orbit Trails:** Visualizes the recent paths taken by the bodies with slightly transparent lines.
* **Automatic Camera Framing:**
    * The camera automatically pans to keep the center point between the two bodies in view.
    * The camera automatically zooms *out* if necessary to ensure both bodies remain visible.
    * **Manual Zoom Override:** If you manually zoom out further than the automatic zoom requires, the camera will respect your zoom level and not automatically zoom back in.
* **Manual Camera Controls:** Use your mouse to orbit (left-click drag), zoom (scroll wheel), and pan (right-click drag) the view via `OrbitControls`. Manual interaction temporarily overrides the automatic framing.
* **Basic Collision Avoidance:** The physics simulation pauses updates if the bodies get extremely close to prevent instability (based on their visual radii).

## How to Run

1.  **Save the Code:** Save the HTML code provided for the simulation as an HTML file (e.g., `two_body_simulation.html`).
2.  **Open in Browser:** Open the saved HTML file in a modern web browser that supports WebGL and JavaScript Modules (like Chrome, Firefox, Safari, Edge).
3.  **Interact:**
    * Observe the default orbit.
    * Use the sliders at the bottom to change `G`, `Mass 1`, `Mass 2`, and `Speed`. Notice how the orbits, body sizes, and simulation pace change.
    * Use your mouse (left-drag, right-drag, scroll) to manually control the camera view.
    * Observe how the camera automatically adjusts the pan and zooms out (if needed) when you are not manually controlling it.

## Technical Details

* **Library:** [three.js](https://threejs.org/) (r128)
* **Physics:** Simple Euler integration method.
* **Styling:** [Tailwind CSS](https://tailwindcss.com/) for UI elements.
* **Controls:** `OrbitControls` from three.js examples for camera interaction, augmented with custom auto-framing logic.
* **Error Handling:** Basic error messages may appear in the UI if issues occur during initialization or runtime. Check the browser's developer console for more details.

## Notes

* The Euler integration method can accumulate errors over long simulation times or with very high speeds/forces.
* Changing parameters drastically (especially mass or G) while the simulation is running can lead to unstable or chaotic orbits. You might need to let the camera readjust or manually reposition it.
* The initial conditions are set for a relatively stable orbit at default parameters.
