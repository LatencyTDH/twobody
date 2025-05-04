# Two-Body Gravitational Simulation

This is an interactive 3D simulation demonstrating the gravitational interaction between two bodies, built using three.js.

The visualization can be viewed at https://latencytdh.github.io/twobody.

## Features

* **3D Visualization:** Shows two celestial bodies orbiting each other in 3D space.
* **Physics-Based:** Simulates gravitational attraction using Newton's law of universal gravitation ($F = G \frac{m_1 m_2}{r^2}$).
* **Interactive Control:** Allows adjusting the gravitational constant (G) via a slider, affecting the orbital speed and dynamics.
* **Orbit Trails:** Visualizes the paths taken by the bodies.
* **Camera Controls:** Use your mouse to orbit (left-click drag), zoom (scroll wheel), and pan (right-click drag) the view.

## How to Run

1.  **Save the Code:** Save the HTML code provided above as an HTML file (e.g., `two_body_simulation.html`).
2.  **Open in Browser:** Open the saved HTML file in a modern web browser that supports WebGL (like Chrome, Firefox, Safari, Edge).
3.  **Interact:**
    * Observe the default orbit.
    * Use the slider at the bottom to change the value of the gravitational constant `G`. Notice how the orbits change speed and shape.
    * Use your mouse to change the camera angle and zoom level.

## Technical Details

* **Library:** [three.js](https://threejs.org/) (r128)
* **Physics:** Simple Euler integration method for updating positions and velocities based on calculated gravitational forces.
* **Styling:** [Tailwind CSS](https://tailwindcss.com/) for UI elements.
* **Controls:** `OrbitControls` from three.js examples for camera interaction.

## Notes

* The simulation uses simplified physics (Euler integration), which can accumulate errors over long periods. More advanced integrators (like Verlet or Runge-Kutta) could provide better accuracy but add complexity.
* The initial conditions (masses, positions, velocities) are set to create a relatively stable, interesting orbit for the default `G` value. Changing `G` significantly might lead to unstable orbits (e.g., bodies flying apart or colliding).
* Collision detection is not implemented. If the bodies get too close, the simulation might become unstable due to extremely large forces.
