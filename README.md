This Asset generates an ivy, by having only a collision mesh and starting points or surface as input.
It automatically generates a VDB SDF and normal vector field from the input, or it can alternatively use the second input to provide a collision SDF and a vector Field, representing the normals of the collision object.
There are various parameters to control the growth, including direction, branching, curviness/straitness of the branches, maximum number of branching, as well as control for the leaf distribution. 
The core is a sop solver, where a vex wrangle generates new points each frame, based on various criteria. 
The grow direction vector is projected first projected onto the surface, and a position for the next point is calculated based on this projection and the adjustable step. The current point is displaced along that projection vector by the step amount.
The new position is projected back onto the surface, to ensure perfect adhesion to the surface.
Each point becomes part of the branch, growing towards the direction of growth.
