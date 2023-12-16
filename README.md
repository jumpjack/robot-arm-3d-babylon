# robot-babylon
3d interactive robot model created with babylon.js

Github pages demo: https://jumpjack.github.io/robot-arm-3d-babylon/

Original demo: https://pensive-shannon-0eee31.netlify.app/

![image](https://user-images.githubusercontent.com/22677130/154802011-0faf7d5b-f3c1-4470-b4d7-499fac75f93e.png)

------------

Note:

Circonferenza su piano XY:

$(x - x_0)^2 + (y - y_0)^2 + (z - z_0^2) = R^2$

- Rotazione intorno a X:
    - $y_0' = y_0 \cos(\theta) - z_0 \sin(\theta)$
    - $z_0' = y_0 \sin(\theta) + z_0 \cos(\theta)$
- Rotazione intorno a Y:
    - $x_0' = x_0 \cos(\theta) + z_0 \sin(\theta)$
    - $z_0' = -x_0 \sin(\theta) + z_0 \cos(\theta)$
- Rotazione intorno a Z:
    - $x_0' = x_0 \cos(\theta) - y_0 \sin(\theta)$
    - $y_0' = x_0 \sin(\theta) + y_0 \cos(\theta)$

Equazioni implicite:

- X: $(x - (x_0 \cos(\theta) + z_0 \sin(\theta)))^2 + \left(y - (y_0 \cos(\theta) - z_0 \sin(\theta))\right)^2 + \left(z - (y_0 \sin(\theta) + z_0 \cos(\theta))\right)^2 = R^2$
- Y: $(x - (x_0 \cos(\theta) + z_0 \sin(\theta)))^2 + (y - (y_0 \cos(\theta) - z_0 \sin(\theta)))^2 + (z - (-x_0 \sin(\theta) + z_0 \cos(\theta)))^2 = R^2$
- Z: $(x - (x_0 \cos(\theta) - y_0 \sin(\theta)))^2 + (y - (x_0 \sin(\theta) + y_0 \cos(\theta)))^2 + (z - z_0)^2 = R^2$

Equazioni esplicite in Z:
- X: $z = (y_0 \sin(\theta) + z_0 \cos(\theta)) \pm \sqrt{R^2 - (x - (x_0 \cos(\theta) + z_0 \sin(\theta)))^2 - (y - (y_0 \cos(\theta) - z_0 \sin(\theta)))^2}$
- Y: $z = (-x_0 \sin(\theta) + z_0 \cos(\theta)) \pm \sqrt{R^2 - (x - (x_0 \cos(\theta) + z_0 \sin(\theta)))^2 - (y - (y_0 \cos(\theta) - z_0 \sin(\theta)))^2}$
- Z: $z = z_0 \pm \sqrt{R^2 - (x - (x_0 \cos(\theta) - y_0 \sin(\theta)))^2 - (y - (x_0 \sin(\theta) + y_0 \cos(\theta)))^2}$

-----------

Sostituendo cos(theta) e sin(theta) con C ed S per leggibilità:

- Rotazione intorno a X:
    - $y_0' = y_0 C - z_0 S$
    - $z_0' = y_0 S + z_0 C$
- Rotazione intorno a Y:
    - $x_0' = x_0 C + z_0 S$
    - $z_0' = -x_0 S + z_0 C$
- Rotazione intorno a Z:
    - $x_0' = x_0 C - y_0 S$
    - $y_0' = x_0 S + y_0 C$

Equazioni implicite:

- X: $(x - (x_0 C + z_0 S))^2 + \left(y - (y_0 C - z_0 S)\right)^2 + \left(z - (y_0 S + z_0 C)\right)^2 = R^2$
- Y: $(x - (x_0 C + z_0 S))^2 + (y - (y_0 C - z_0 S))^2 + (z - (-x_0 S + z_0 C))^2 = R^2$
- Z: $(x - (x_0 C - y_0 S))^2 + (y - (x_0 S + y_0 C))^2 + (z - z_0)^2 = R^2$

Equazioni esplicite in Z:
- X: $z = (y_0 S + z_0 C) \pm \sqrt{R^2 - (x - (x_0 C + z_0 S))^2 - (y - (y_0 C - z_0 S))^2}$
- Y: $z = (-x_0 S + z_0 C) \pm \sqrt{R^2 - (x - (x_0 C + z_0 S))^2 - (y - (y_0 C - z_0 S))^2}$
- Z: $z = z_0 \pm \sqrt{R^2 - (x - (x_0 C - y_0 S))^2 - (y - (x_0 S + y_0 C))^2}$
