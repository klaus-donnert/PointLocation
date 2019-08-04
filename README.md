# PointLocation
Determine if a point is inside of a polygon 

```php
$pointLocation = new PointLocation();

// each point has a x and y
$points = [  "50 70"
             ,"70 40"
             ,"-20 30"
             ,"100 10"
             ,"-10 -10"
             ,"40 -20"
             ,"110 -20" 
           ];

// a polygon is a set of lines that form a closed loop
// The last point's coordinates must be the same as the first one's, to "close the loop"
$polygon = [  "-50 30"
              ,"50 70"
              ,"100 50"
              ,"80 10"
              ,"110 -10"
              ,"110 -30"
              ,"-20 -50"
              ,"-30 -40"
              ,"10 -10"
              ,"-10 10"
              ,"-30 -20"
              ,"-50 30"
           ];

foreach($points as $key => $point) {
    echo "point " . ($key+1) . " ($point): " . $pointLocation->pointInPolygon($point, $polygon) . "<br>";
}
```

This will output:

```
point 1 (50 70): vertex
point 2 (70 40): inside
point 3 (-20 30): inside
point 4 (100 10): outside
point 5 (-10 -10): outside
point 6 (40 -20): inside
point 7 (110 -20): boundary
```
