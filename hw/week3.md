### Homework 3 (due Wednesday February 11, 2015)

**This homework has two parts:** programming practice due **Sunday**, and a required tutorial to be completed **before Tuesday night**.

1. Programming practice:
  - Pick two additional sketches from [last week's list of 15](week2.md) and create them in Processing.
  
  - Beginning with the Ball class code below, modify it in the following ways:
    1. Modify the `Ball` constructor so that new Ball objects have a random velocity: `vx` and `vy`.
    2. Modify the `Ball` class so that every ball has its own color, which is set to a random color in the constructor.
    3. Add a [`mousePressed()`](https://processing.org/reference/mousePressed_.html) function to the code so that, when you click, the ball `b` is repositioned to the mouse position. (Hint: `b.x` and `b.y` will let you get and set the *x* and *y* coordinates of the ball.)
    4. Add a second `Ball` object and call its `draw` and `move` methods (functions) to animate it.
    
        ```Processing
        class Ball {
          float x, y;
          float vx, vy;
          float radius;
          color c;

          Ball() {
            x = random(width);
            y = random(height);
            radius = 10;
            vx = random(3);
            vy = random(2);
            c = color(random(360), 100, 100);
          }

          void draw() {
            fill(c);
            ellipse(x, y, radius*2, radius*2);
          }

          void move() {
            x = x + vx;
            y = y + vy;
            if (x < radius || x > width-radius) {
              vx = -vx;
            }
            if (y < radius || y > height-radius) {
              vy = -vy;
            }
          }
        }

        Ball b;

        void setup() {
          size(500, 500);
          colorMode(HSB, 360, 100, 100);

          b = new Ball();
        }

        void draw() {
          background(360);

          b.draw();
          b.move();
        }

        void mousePressed() {
          b.x = mouseX;
          b.y = mouseY;
        }
        ```

