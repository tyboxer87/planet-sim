# Planet Lab

Open **index.html** in a modern browser. Everything is in one HTML file: no build, packages, network requests, or installation needed.

Drag an object from the bottom palette into space, or select a type and click to place it. Select a type before editing its spawn mass. Drag existing bodies to move them, drag empty space to pan, and scroll to zoom. Auto orbit estimates a circular launch velocity around the strongest local attractor; Aim velocity lets you draw a launch vector on the canvas. Space pauses; Escape cancels placement; Delete removes a selected body. The object selector, inspector buttons, and “Place selected type at view center” button in Science & help support keyboard use.

The two clocks are deliberately separate: orbital time advances Newtonian dynamics in years, while stellar time advances aging in millions of years. Set stellar aging to Frozen to study orbits. The inspector's **Advance 10%** button lets you explore an individual star's lifecycle without waiting. The Stellar nursery preset starts with a massive star near the end of its life. Collision course demonstrates two brown dwarfs merging into a red dwarf. Change the spawn mass to experiment with more massive stars. Mass readouts always use solar masses (M☉), temperatures use Kelvin (K).

Tap the **Your universe** or **Inspector** header to expand or collapse that module. The creation panel has three views: **Full** shows the palette and every control, **Objects** shows only the four draggable object choices, and **Hide** leaves just the panel header. Pause and Fit remain available above the panel in the compact views. Switching views preserves mass, launch mode, speed, and selection settings. On small screens, both top modules start collapsed and the palette starts in Objects view; opening one top module closes the other. Your choices remain in effect when rotating the device or resetting the simulation. Expanded panels scroll when space is tight.

## Science and game rules

- Gravity uses all-pairs Newtonian forces, G = 4π² in AU³/(M☉ yr²), softening of 0.008 AU, and an adaptive kick-drift-kick leapfrog integrator. Close encounters can slow the actual orbital clock to keep the integration stable. No boundaries or artificial edge bounces: use Fit to find distant bodies.
- Sticky mergers conserve mass and linear momentum, combine gas content, and mix remaining stellar fuel. Real collisions can also eject matter or fragment objects. Display sizes and collision radii are enlarged independently of camera zoom.
- Gas-rich objects cross a schematic brown-dwarf boundary at 0.0124 M☉ and hydrogen-fusion threshold at 0.075 M☉. Composition matters: merging rocks does not produce a hydrogen-burning star. These thresholds are approximate and depend on composition and formation.
- Hot blue main-sequence stars are distinct from blue giants. A short schematic giant phase is included near the end of stellar life. Sun-like stars leave **white dwarfs**, not red dwarfs. Red dwarfs are low-mass hydrogen-burning stars with extremely long lives.
- Core-collapse supernovae begin at 8 M☉ in this model. Initial masses of 8–20 M☉ leave a neutron star; above 20 M☉ they leave a black hole. These are broad educational shortcuts, not reliable remnant predictions. Real outcomes depend on core structure, metallicity, winds, and binary evolution. A neutron-star maximum mass of 2.3 M☉ and a white-dwarf thermonuclear threshold of 1.4 M☉ are schematic rules.
- Ejecta are represented by massive gas clouds, preserving mass. Gas clumps above 0.075 M☉ form protostars after a compressed 60 Myr, then ignite after another 5 Myr. Real supernova ejecta mix with surrounding gas and require cooling, fragmentation, and gravitational collapse; they do not immediately become stars. Radiated mass loss and winds are omitted.
- Rocky-world surface temperatures use a radiative equilibrium estimate from all luminous bodies, albedo 0.30, and a 33 K greenhouse offset that tapers to zero for very cold worlds. Unilluminated rocky worlds approach the 2.725 K background floor. Stellar readouts use effective surface temperatures. Black holes show Hawking temperature, not accretion-disk temperature. Gas giant temperatures include an intrinsic heat floor. This is not a climate model.
- Rocky worlds below 273 K are icy; 273–373 K is a simplified liquid-water band assuming ~1 bar; above 373 K they are hot; above 1,400 K they are molten. Rock melting depends on composition and pressure. **Simulated life** develops after 100 Myr continuously at 273–323 K. That rule is fictional: temperature alone cannot predict life. Green habitable rings are single-star estimates; other stars and atmospheric conditions can change the result.
- The optional **40 M☉ black-hole finale** spirals everything inward and restarts the solar neighborhood. This is an arcade mechanic. Real black holes do not vacuum up distant matter or reset the universe. Disable it for ordinary gravity and accretion.

The in-game **Science & help** panel contains controls, equations, model limits, and source links.

Sources checked against NASA:

- [Types of stars](https://science.nasa.gov/universe/stars/types/)
- [Stellar lifetimes and remnants](https://science.nasa.gov/exoplanets/stars/)
- [Star lifecycles](https://science.nasa.gov/mission/webb/star-lifecycle/)
- [The habitable zone](https://science.nasa.gov/exoplanets/habitable-zone/)
- [Black holes](https://science.nasa.gov/universe/black-holes/)

## Verification

Serve the folder locally with `python -m http.server 8000`, then visit `http://localhost:8000/tests.html` for deterministic browser checks covering gravity, orbit stability, conservation, mergers, stellar evolution, climate states, spawning, and reset behavior. The tests run in an isolated iframe and do not change a game open in another tab.
