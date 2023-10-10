# Salt-peanut
Let's dance

![buh](https://github.com/nicolasbaez/Salt-peanut/blob/main/xp015.gif)
```javascript
w = k = 500;
setup = (_) => createCanvas(w, w, WEBGL);
draw = (_) => {
  colorMode(HSB, 3);
  rotateX(k);
  rotateY(k / 2);
  clear();
  for (i = 0; i <= PI; i += 0.1)
    for (j = 0; j < 2 * PI; j += 0.1) {
      stroke(i, j, 3);
      noFill();
      r = 99;
      push();
      translate(
        r * sin(i + k) * cos(j + k),
        r * sin(i + k) * sin(j + k),
        r * cos(i + k)
      );
      box(9);
      pop();
    }
  k += 0.02;
};
keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp015.gif", 314, { delay: 0, units: "frames" });
  }
};
