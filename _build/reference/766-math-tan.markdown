# TAN

> f = TAN (x)

Tangent of `x`. `x` is in radian.

See also COS, SIN, TAN and ATAN.

### Example 1

```
a = tan(0.5)
print a             ' Output: 0.54630248984379

b = atan(a)
print b             ' Output: 0.5
```

### Example 2

```
' Short TAN use.bas   SmallBASIC 0.12.2 [B+=MGA] 2016-03-14
' in the following example it is important to keep in mind
' x,y when used in TAN are relative positions to x1,y1 and not
' absolute screen coordinates
' you can move x1,y1 anywhere on screen!!!!

x1 = 250
y1 = 150
angle = 60  ' degree

' highlight start point with a circle in yellow with radius 2
circle x1, y1, 2, 1, 14                             

' circle x,y,r,aspect,c   'aspect 1 is circle, !1=ellipse
' say you want to make a line 60 degrees from x1,y1  and
' you need the x2 100 greater than x1 or x2 = x1+100
' since we know TAN=y/x (though you need a diagram to see it)
' then TAN(RAD(60)) = y/100
' then 100*TAN(rad(60) = y   by algebraic mult 100 both sides
' so  y2=y1+100*TAN(rad(60)

line x1, y1, x1 + 100, y1 + 100*TAN(RAD(angle))     ' <== HERE IS TAN

' so here we used TAN to calculate the y change in height
' from y1 to create a 60 angle from point x1,y1 and x2,y2 AND
' AND make it so x2=100 more than x1
' check draw arc at x1,y1 with 100 radius
' for 0 degrees start to 60=2*pi/6 radians end arc, 1=aspect

arc x1, y1, 100, 0, RAD(angle), 1, 14               ' 14 = color yellow
```



### Trigonometry lesson

Review:

Trigonometry is the study of right triangles,
those that have one 90 degree angle AKA Pi/2 in radians.
These right triangles are infinite in a rectilinear coordinate system
with x,y referring to screen position in relation to an origin point (0,0).

In SmallBASIC the y axis increases from top to bottom
and in SmallBASIC the angle measures used for arguments to SIN
and COS and the other Trig Angles are expected to be in radian
measure as opposed to degree measure.

This is a standard conflict and source of confusion from what you might
learn in math class and doing stuff on a computer.
For all triangles that have all 3 angles the same,
their legs will have exactly the same ratios between themselves.

Feed a trig function an angle and it will return the special ratio
between the sides of the triangle that is universal to all triangles
that have the same equal angle measures.
Feed the COS function an angle and it will return
the universal ratio for the leg adjacent divided by the hypotenuse.
( Adjacent means next to or attached in the case of angles.)

Some more information gained from study or right angles:
The COS for one acute angle in a right triangle is
the SIN for the other acute angle.
For 45 degree angle (Pi/4 radians) the two legs are the same therefore
SIN(RAD(45 degrees)) = COS(RAD(45 degrees)) = .7071...
notice if that is squared =.5 exactly 1-COS(angle)^2=SIN(angle)^2
As the angle size approaches 0, COS(angle) > 1 and SIN(angle) >0
At angle = 0 you have more a line segment than a triangle.

Similarly as angle approaches 90 degrees = Pi/2 radians,
the COS(angle) ratio approaches> 0 and SIN(angle) >1
Trig functions are Unary Operators, they take one argument,
an angle expressed in Radians,
and return to you the ratio of the triangle sides involved.

The COS returns the ratio of the leg adjacent the angle
divided by the hypotenuse. adj/hyp
The SIN function returns the leg opposite the angle fed the function
divided by the hypotenuse. opp/hyp
The third main trig function is TAN, tangent. opp/adj
The TAN(angle in radians) returns
the ratio of the opp side divided by the adjacent side.

In SmallBASIC this is very handy because side opposite/ side adjacent
is the same as y/x the same two items that define a point location!
Can you see what this means?
Does a chill of revelation run up and down your spine?
Oh! that means for any point x,y on the screen,
I can find the angle it is from the origin!

It is the ATAN(y/x)
We are almost ready now to play pin the tail on the donkey! Hang in there...
The A before the TAN, the A before the SIN, COS... means ARC
ATAN is pronounced ARC TANGENT; ACOS is pronounced ARC COSINE; ASIN is pronounced ARC SIN.

In each the ARC means The Angle whose Trig Ratio is: (ratio of two sides)
so ATAN is the Angle whose TAN ratio is (opp leg lentgh/adj leg length)
We feed ATAN a leg ratio argument and it tells what angle that ratio came from.
ARC in the Language reference is referred to as "the inverse"
If TAN( an angle) = ratio then
ATAN( ratio=opp/adj ) = an angle (in radians)
DEG(ATAN(opp/adj) = an angle in degrees
You can think or the A in front of TAN or COS or SIN as give me "An Angle"
without the A you get side ratios.
