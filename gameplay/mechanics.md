# Mechanics
## Teleportation
## Remote Control Robots
You control the robot first person. It can fit through places the player can't and it can be used to step on to reach high places.
## Circuits
## Double Jump
## Wall Running
## Wall Jump

Other design-related things
---------------------------

-   Show connection between elements by lines on the wall
    -   Show logical operations using their respective MIL/ANSI symbol,
        plus its short name (AND, OR, NAND, NOR, XOR, XNOR, NOT) inside
        the symbol (because not everyone knows the symbol)
    -   Has a to-be-chosen color when disabled, another one when enabled
    -   Can have delay and timer gates
        -   Must choose symbols
        -   Delay/timer written in symbol (e.g. 2s)

Test series
-----------

Some of them are named after scientists/artists

### Newton series

-   Differently weighed boxes
    -   Buttons accepting a certain threshold of mass
    -   Lever mechanism, to lift things
    -   Fun Fact™: Portal 2’s cube entity name is
        `portal_weighted_cube`, which *isn’t* actually weighted
-   Gravity fields
    -   Changes gravity for a given zone
    -   Low/zero gravity
        -   Zero-gravity shall not be accessed by the player since it
            can’t really swim in air…
-   Projected gravity fields
    -   Same as above
    -   Projected
    -   Gravity goes in the projection direction
        -   Can be reversed/stop or even faster/slower
    -   Can go through portals
    -   Has velocity cap
-   Zero-G boxes
    -   May be activated/deactivated by areas and/or special lasers
        (including slowed down ones)

### (Nikola) Tesla series

-   Magnetic boxes
    -   Positively charged: red aspect, white “+” on it
    -   Negatively charged: blue/cyan aspect, white “-” on it
    -   Can be more or less polarized, indicated by color intensity or a
        “gauge” on it
    -   Of course, they repel themselves
-   Magnetic surfaces?
-   Magnetic buttons
### Elemental series

-   Water/other liquid - !! Requires specific test chamber design to
    avoid too much sandboxing if the flow simulation is costly !!
    -   Could be poured by portals from a container/dispenser to fill
        some areas requiring fill-up as part of the test
    -   Use drains to limit liquid quantity
    -   Physical simulation shouldn’t be an actual particle simulation
        but rather a volume box simulation using a simple pathfinding
        algorithm to determine where to go
    -   Maybe use Bullet-FLUIDS?
        <https://github.com/rtrius/Bullet-FLUIDS>
-   Fire & hot Air
    -   Can make wooden objects catch fire to clean a path
    -   Its hot air effect (non-physically simulated, but still visually
        displayed using particles) could lift things (c.f. hot
        air balloons)
-   Air ducts
    -   Blow air or suck air, can be used to attract/repel objects
-   Earth? Give ideas.
-   Heat/cold beams (maybe?)
    -   Could lead to funny mechanics like triggering fire, making water
        boil/freeze it
        -   Making water boil to evaporate it, as testing element
        -   Freezing electrified, albeit deadly, water to be able to
            walk on it

### Wavelength series

-   Colored Boxes for use with ↓
-   Colored Box Button

-   White/colored lasers
    -   Has a limited set of colors: \[Color\] \[RGB\]
        -   Red 100
        -   Yellow 110
        -   Green 010
        -   Cyan 011
        -   Blue 001
        -   Purple 101
        -   White 111
-   Colored Laser redirection boxes
    -   Acts as light filter; e.g. red laser doesn’t pass through green
        box which only lets green pass
-   Laser redirection boxes, colored or not:
    -   When combining multiple laser colors, they RGB-ically
        combine (e.g. Red+Cyan=White)
    -   Already-imposed restrictions still applies for colored
        redirection boxes
-   Prism?
    -   Splits out laser into its R, G, B components
-   Colored laser receiver
    -   Can be activated by a combination of wavelengths/RGB components,
        though multiple activators are to be used only in most advanced
        tests
-   !!! On lasers: keep lethality or not? Rule(s) which defines it? !!!

### Multiplicity series

-   Multiple portal pairs (isn’t good for colorblind people)
    -   Linked portals have almost the same color:
        -   Red/Orange
        -   Yellow/Lime
        -   Green/Blue-Green or Cyan
        -   Blue/Violet

### Escher series

-   Noneucliean space: have (invisible) world-portals
    -   Might, by far, be the hardest thing to implement because of
        implications (LOD, portal rendering, …)
-   Space bending corridors
-   Big combination with gravity fields
-   
### Tag series

-   Paint fluids
    -   If Elemental series’ water pouring mechanics gets implemented,
        can be used with paint as liquid, for storage only parts
        -   Could spice up gameplay by limiting amount of paint; but
            resetting involves tricky things, pick one:
            -   Level restart (through disintegrating you? Or through
                escape ways to cloned test chamber?)
            -   Reset button: go to the test’s start point, press reset
                button, water sprayers washes out paint, boxes fizzled,
                game mechanics’ states reset
    -   Speed
    -   Surface-convert (nonportallable → portallable)
    -   Laser-reflect

### Ultimate

-   Any of the above, combined
    -   “Any”, possibly “All”, but don’t go too far
    -   Not necessarily complicated, but complex (refer to the Python
        lore; run your Python interpreter and type “import this”)
        -   Actually, try to avoid complicated levels, keep the fun

Chronos series? (wibbly-wobbly timey-wimey stuff)

Other random ideas
------------------

-   “Matrix” mode: see some things through walls
-   Self-destructing box
    -   Countdown displayed on it
-   Spheres
    -   Essentially the same as boxes, but it’s a sphere
    -   Sphere button
-   Tetrahedrons
    -   Serves the same purpose as boxes/spheres
    -   Constructed in-place by folding and soldering its net
    -   Tetrahedron buttons
-   Jello boxes / spheres / tetrahedrons
    -   Constructed in-place by pouring liquid jello in a
        transparent (e.g. plastic or glass) mold and then quickly being
        cooled
    -   Bouncy!
    -   Available in different colors, for the cheap price of \$0.00 !
    -   Dissolved when it goes in water
