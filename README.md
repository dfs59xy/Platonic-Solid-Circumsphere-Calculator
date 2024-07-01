# Polyhedron-Circumsphere-Inscriber
Calculates the intersections of each vertex of a polyhedron with its circumsphere when the polyhedron is rotated to any 3D orientation wrt the circumsphere's geographic coordinate system.

The initial version only supports Platonic Solids (Tetrahedron, Hexahedron, Octahedron, Dodecahedron, and Icosahedron). These were the simplest polyhedrons to model as a class because of the uniformity of their faces.

I have a plan for adding the Truncated-, Stubbed-, and Rhombic- variants of the Platonic Solids, but I don't personally have a need for them, so I might never get to it.  If you have need for them, though, I'll be happy to either add them or help you do it.

## Why would I inscribe a polyhedron's vertices onto its circumsphere at arbitrary 3D orientations?
I have no idea why you'd want to do it.

I did it for Dyson Sphere Program (DSP), an absolutely gorgeous single-player interstellar factory simulation game.  Highly recommended if you enjoy factory simulation games. (https://store.steampowered.com/app/1366540/Dyson_Sphere_Program/).  

If you're not here for DSP, the rest of this section is irrelevant... but I'd love to know why someone would use it for anything other than DSP.  Say 'Hi' to @dfs59xy on Discord and teach me something new!

In the December 2023 update to DSP, Youthcat Studio add the Dark Fog (DF) combat upgrade to the game.  DF is a self-replicating AI-enabled robotic mining hive that's propogating out-of-control throughout the star-cluster surrounding your home world. Players who choose to enable Dark Fog enjoy the ability to loot valuable resources when destroying the enemy units, but at the cost of expending valuable resources to build and maintain offensive/defensive equipment for controlling and exploiting the DF bases.

I wanted to place a network of planetary shields over large areas of a planet where current/future mining/manufacturing were planned, with a geometry and orientation that would ensure the existing DF Base would continue to attack my harvesting arsenal rather than one of the shields.  I also wanted to omit one or two shield generators from the 'optimal' pattern, leaving an area open for additional DF bases to deploy [more bases, more assaults, more loot!].

Reddit offered great ideas and discussion about planetary shield effectiveness and optimal shield deployments (search "reddit dsp shield geometry" for a selection). I wanted to apply the cube pattern discussed in https://www.reddit.com/r/Dyson_Sphere_Program/comments/190vx2p/shield_coverage_for_those_who_absolutely_want_to/.  I started placing planetary shields, but soon discovered that the location of some important resources (as well as the DF base I was harvesting) made that pattern impractical for me.  But I noticed that if I rotated the cube in 3 dimensions it could fit perfectly, and leave some space for up to 2 more DF bases.  I could have simply eye-balled it to get 'close', and wait for the shields to fully charge then see whether anything important was left exposed, but what fun would that have been?!?  Instead, I ventured down the rabbit hole of Platonic Solids, Haversine Formulas, and Hamiltonian Cycles... then tied the bits together as a tool for quickly picking shield generator locations when I visit new unexplored systems.

Frankly, I didn't need this level of accuracy for my DSP purposes.  I also don't typically optimize DSP factories or resource management, and I prefer casual, relaxed exploration vice speed runs.  But, the curiousity of 'how to do it' drove me towards coding the solution for a Cube, and then generalizing it to rotate any Platonic Solids rather than just the Cube.  So I figured, "why not share it."

## Yeah, yeah, enough rambling... How do I use it?
Download the Excel workbook and launch it.  

Note:  IF YOU'RE PROMPTED TO ALLOW MACROS, DO NOT ACCEPT!
Note:  All logic is embedded in formulas rather than VBA [never enable Macros/VBA from an untrusted source!].

Launch the spreadsheeet, choose a Platonic Solid from the dropdown, enter the Latitude and Longitude where you want one of the vertices to be placed, and enter the Lat/Long of a reference point to establish a 'Line of Bearing' from the Starting point to one of its adjacent vertices.  The spreadsheet will calculate all remaining vertices for you and display their Lat/Long in both floating point format and degrees/minutes/seconds. 

## What about other Polyhedrons?
My initial goal was to figure out how to find the vertices of a cube rotated on 3 axes within its circumsphere.  Once I realized that only 4 other shapes (Tetrahedron, Octahedron, Decahedron, Icosahedron) are also comprised entirely of regular polygons, I abstracted the Excel formulas to include those as well.

Other isotropic and anisotropic polyhedrons could be added with varying degrees of difficult.  Rhombic and truncated polyhedrons might be most easy to add as an abstracted group.  Once we move away from the Platonic Solids, though, the shapes and areas of some faces of the polyhedron will be distorted by the fact that some vertices will have to be 'projected' to the circumsphere rather than inscribed directly upon it.

## Can I see the formulas?
Most of the columns and tabs are 'protected' in Excel, but you're welcome to see them.  They're not protected to keep them secret, but instead just to hide the _Quagmire_. The password to unlock everything is yours for the asking, @dfs59xy on Discord.

