## Platonic-Solid-Circumsphere-Calculator
Calculate Latitude/Longitude coordinates of the vertices of any Platonic Solid, rotated to any 3D orientation within its encapsulating circumsphere.

## Why would I want to do that?
No idea why you'd want to, but I did it for Dyson Sphere Program (DSP), an absolutely gorgeous single-player interstellar factory simulation game.  Highly recommended if you enjoy factory simulation games.  (https://store.steampowered.com/app/1366540/Dyson_Sphere_Program/).  

If you're not here for DSP, the rest of this section is irrelevant!

In a December 2023 update, Youthcat Studio add the Dark Fog (DF) combat upgrade to the game.  DF is a self-replicating AI-enabled robotic mining hive that's propogating out-of-control throughout the star-cluster surrounding your home world. Players who choose to enable Dark Fog enjoy the ability to loot valuable resources when destroying the enemy units, but at the cost of expending valuable resources to build and maintain offensive/defensive equipment for controlling and exploiting the DF bases.

I wanted to place a network of planetary shields over large areas of a planet where current/future mining/manufacturing were planned, in a geometry that ensured the existing DF Base would continue to attack my harvesting arsenal rather than one of the shields.  I also wanted to omit one or two shield generators from the 'optimal' pattern, leaving an area open for additional DF bases to deploy [more bases, more assaults, more loot!].

Reddit offered great ideas and discussion about planetary shield effectiveness and optimal shield deployments (search "reddit dsp shield geometry" for a selection). I wanted to apply the cube pattern discussed in  https://www.reddit.com/r/Dyson_Sphere_Program/comments/190vx2p/shield_coverage_for_those_who_absolutely_want_to/, but found the location of exploitable resources and harvestable DF bases made that pattern impractical for me.  I noticed that if I rotate the cube in 3 dimensions it could work perfectly.  I could have simply eye-balled it to get 'close', and wait for the shields to full charge then see whether anything important was left exposed, but what fun is that?  Instead, I ventured down into a rabbit hole of Platonic Solids, Haversine Formulas, and Hamiltonian Cycles... then tied the bits together as a tool for quickly picking shield generator locations when I visit new unexplored systems.

Frankly, I don't really care for this level of accuracy.  I also don't typically optimize DSP factories or resource management, and enjoy slow, relaxed exploration rather than speed runs.  But, the curiousity of how to do it drove me towards coding the solution, and then generalizing it to rotate any Platonic Solids rather than just the Cube.

## Yeah, yeah, enough rambling... How do I use it?
Download the Excel workbook and launch it.  All logic is embedded in formulas rather than VBA, so it DOES NOT require allow VBA from an untrusted source. IF YOU'RE PROMPTED TO ALLOW MACROS, DO NOT ACCEPT!

Launch the spreadsheeet, choose one of the 5 Platonic Solids, enter the Latitude and Longitude where you want one of the vertices to be placed, and enter the Lat/Long of a reference point to establish a 'Line of Bearing' from the Starting point to one of its adjacent vertices.  The spreadsheet will then calculate all remaining vertices for you.

## What about other Polyhedrons?
My initial goal was to figure out how to find the vertices of a cube rotated on 3 axes within its circumsphere.  Once I realized that only 4 other shapes (Tetrahedron, Octahedron, Decahedron, Icosahedron) are comprised entirely of regular polygons, I decided to abstract the Excel formulas to include those as well.

Other isotropic and anisotropic polyhedrons could be added with varying degrees of difficult.  Rhombic and truncated polyhedrons might be most easy to add as an abstracted group.  Once we move away from the Platonic Solids, though, the shapes and areas of some faces of the polyhedron will be distorted by the fact that some vertices will have to be 'projected' to the circumsphere rather than inscribed directly upon it.

## Can I see the formulas?
Most of the columns and tabs are 'locked' in Excel, but you're welcome to see them.  They weren't locked to keep anything secret, just to prevent the formulas from being accidentally 'broken' by casual users. If you're inclined to see the innards (especially if you care to add other polyhedrons to the lookup tables!), unlock the hidden columns and tabs using the password 'Quagmire'.  If you have questions, please contact @dfs59xy on Discord.

