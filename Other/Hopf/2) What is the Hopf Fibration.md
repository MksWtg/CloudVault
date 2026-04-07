
Prerequisites: [[1) Hopf 101]]
Consider the space of all lines through the origin in $\mathbb{C}^2$, we call this CP1 or the complex projective line or the Riemann sphere.

This visualization should help with the fact that this space is topologically a 2-sphere.

Think of it as wrapping the plane into a ball and joining it at a point.

![[Pasted image 20260403114100.png]]


Every point in C2 belongs to a line through the origin. This is a map C2 -> CP1

replace C2 with S3 (considering only the unit vectors) and replace CP1 with S2 (the stereographic projection). We get a map S3 -> S2.

It maps each point on S2 to a circle on S3.

Consider (x = 1, y = 0, z = 0)

In the sphere above, 1 is x, i is y and infinity is z.

What is the circle this maps to?

Well this maps to all points on the line with gradient 1.


| R3  |                                                                                                                                                                                                                     |                                                     |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------- |
| S3  | The norm \|\|(z0, z1))\|\| = sqrt(norm(z0)^2 + norm(z1)^2). so the norm squared is just norm(z0)^2 + norm(z1)^2. = 2 abs(lambda)^2 = 1, so lambda has magnitude 1/sqrt(2). So lambda itself is 1/sqrt(2)(e^i theta) | Take only the unit vectors from above               |
| C2  | The diagonal line in C- $\lambda(1, 1)$ where lambda is in C                                                                                                                                                        | Each point is z0, z1 are complex numbers            |
| CP1 | All points where z0 : z1 is 1                                                                                                                                                                                       | Complex projective line- C plus a point at infinity |
| S2  | (1, 0, 0) or lat = 0, long = 0                                                                                                                                                                                      | Sphere                                              |
|     |                                                                                                                                                                                                                     |                                                     |
Start with two complex points z0, z1 and assume the norm of (z0, z1) is 1.
Now z0/z1 is a complex number. Take the equivalence class of all such points with the same ration. these form a circle. This ratio, a complex number w, is a point on the complex plane. use stereo projection to make it a point on S2.