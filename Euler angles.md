
- are used to describe the orientation of a reference frame with respect to a fixed reference frame. The rotated frame is often fixed with a body (or orbit).
- measure the rotation of the new frame around its axes
- "reference frame"=coordinate system


## The 3-2-1- Euler angles
are the rotation angle along the z-, y-, and x-axis of the new frame (in this order)

Applications: usually spacecraft attitude control (controlling orientation of spacecraft)


## The 3-1-3 Euler angles
are rotation angles around z-, x-, and z-axis of the new frame

Application to orbit in perifocal frame (orbital x-axis towards periapsis, orbital z-axis towards angular momentum vector):
In case of describing the orientation of an orbit in the perifokal frame towards the inertial frame, the 3-1-3 Euler angles are 3 of the 6 so-called [[Keplerian orbital elements]]:
- Rotation around orbital z-axis: angle between x-axis of fixed (!!!) frame and ascending node, which is the "Right ascension"
- Rotation around orbital x-axis: angle between equatorial and orbital plane, which is the "inclination". The orbital x-axis points towards periapsis, but in this intermediate step, periapsis is also the ascending node! Also,  the orbital z-axis is not the fixed z-axis anymore.
- Rotation around orbital z-axis: angle between ascending node and periapsis, which is the "argument of periapsis". After this, the periapsis is not anymore the ascending node.
This can be visualized using [4] by pluggin in non-zero values for right ascension, inclination and periapsis argument one by one.


## Source
1. Basics on Euler angles: https://www.youtube.com/watch?v=2Cwa6hfn2K0&list=PLOIRBaljOV8iFyHu_PQ9OqYNzpDJKCt-d&index=2&ab_channel=AlfonsoGonzalez-Astrodynamics%26SEPodcast
2. Kepler elements are Euler angles: https://www.youtube.com/watch?v=bgFaDDt0Rn4&ab_channel=AlfonsoGonzalez-Astrodynamics%26SEPodcast
3. Perifocal frame: https://en.wikipedia.org/wiki/Perifocal_coordinate_system
4. Astrodynamics Interactive Demo https://alfonsogonzalez.github.io/AWP/