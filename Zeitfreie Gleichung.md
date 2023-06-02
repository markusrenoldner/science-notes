"time-free integration"


In [[Classical mechanics]], there holds for position, velocity, acceleration of a point mass:
$$\int ads = \int vdv$$
which is an identity that is sometimes useful, as it doesnt depend on $t$ explicitely.


## Example why this is useful
If the tangential acceleration of a mechanical body is available as a function of the position:
$$a=a(s)$$
then, one can find the velocity as a function of the position $v=v(s)$ by applying the above identity:
$$\int_{s_0}^{s_1} ads = \int_{v_0}^{v_1} vdv = \frac{1}{2}(v_0^2-v_1^2)$$
which gives
$$v_1^2=v_0^2 + 2 \int_{s_0}^{s_1} ads$$


## Derivation
For a coordinate $q$ one can informally write down the following "differentials":
$$ dq=\dot q dt ,\quad d\dot q =\ddot q dt$$
We derive now a relationship between $q$ and its time-derivatives without using $dt$ explicitely:
$$\ddot q= \frac{\dot q}{dt} = \frac{d}{dt}\dot q(q)=\frac{d\dot q}{dq}\frac{dq}{dt} = \frac{d \dot q}{dq}\dot q$$
which implies
$$\ddot q dq= \dot q dq$$
In integral form this reads
$$\int \ddot q dq=\int \dot q dq$$


## Source:
Prof. Heinz-Bodo Schmiedmayer - Mechanik 2 lecture notes