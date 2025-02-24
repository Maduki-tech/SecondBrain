> When having issues with the 3D Printer finding the Z Offset

[Fix 3D printer Offset](https://www.webcarpenter.com/blog/162-3D-Print---How-to-calibrate-Z-offset-with-a-BLTouch-bed-leveling-probe-sensor)

The main Problem was, that the printer was not right level.
> Current Z position -2

To fix the problem, you can run

```
M851 Z -X.XX
```
- Will set new Z position.

Safe:
```
M500
```

Activate:
```
M501
```

Get:
```
M503
```
### If you want to check the current height 
```
G1 F60 z0
```

This moves the Nozzle to its `0`
