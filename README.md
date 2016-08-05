# Rotating Cube

Spinning cube in wireframe, with a text-based viewport.
This is vanilla JS, and everything is done using homemade math functions. Move your mouse pointer to rotate the cube in the direction you want.

[See it here](https://rawgit.com/sea-reel/Pure-JS-rotating-cube/master/3d-cube.html)

![](http://image.noelshack.com/fichiers/2016/29/1469151084-cube.png "Screenshot")

I use some tricks to approximate the sinus/cosinus function:

```javascript
function sine(x) {
    x = x%6.28;
    if (x < -3.14159265)
        x += 6.28318531;
    else
    if (x >  3.14159265)
        x -= 6.28318531;

    if (x < 0)
        return 1.27323954 * x + 0.405284735 * x * x;

    return 1.27323954 * x - 0.405284735 * x * x;
}

function cosse(x) {
    return sine(x-1.57);
}

function skrt(x) {
    var a = 1, b = x;
    while(abse(a-b)>5) {
        a = (a+b)/2;
        b = x/a;
    }
    return a;
}

function abse(x) {
    return (x > 0) ? x : -x;
}
```
