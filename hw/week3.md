### Homework 3 (due Sunday, September 20, 2015)

**This homework has two parts:** programming practice due **Sunday**, and a required tutorial to be completed **before Tuesday night**.

1. Programming practice:
  - Pick two additional sketches from [last week's list of 15](week2.md) and create them in Processing.
  
  - **Assignment**: Beginning with the Ball class code below, modify it in the following ways. Put your final code containing all the changes you've made into a new [GitHub repository](../github-guide.md#to-create-a-new-repository) and send me the link.

    1. Modify the `Ball` constructor so that new Ball objects have a random velocity: `vx` and `vy`.

    2. Modify the `Ball` class so that every ball has its own color, which is set to a random color in the constructor.

    3. Add a [`mousePressed()`](https://processing.org/reference/mousePressed_.html) function to the code so that, when you click, the ball `b` is repositioned to the mouse position. (Hint: `b.x` and `b.y` will let you get and set the *x* and *y* coordinates of the ball.)

    4. Add a second `Ball` object and call its `draw` and `move` methods (functions) to animate it.

    5. **Optional challenge**: Modify the `Ball` class constructor to take `x` and `y` parameters; after reading the Array tutorial, or, using [`ArrayList`](https://processing.org/reference/ArrayList.html), create an initial grid of `Ball` objects like in homework 2, sketch 4.

  ```Processing
  class Ball {
    float x, y;
    float vx, vy;
    float radius;

    Ball() {
      x = random(width);
      y = random(height);
      radius = 10;
      vx = 3;
      vy = 2;
    }

    void draw() {
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

    b = new Ball();
  }

  void draw() {
    background(255);

    b.draw();
    b.move();
  }
  ```

2. Follow the [Processing Arrays tutorial](https://processing.org/tutorials/arrays/) and read the [ArrayList reference entry](https://processing.org/reference/ArrayList.html). Email me answers to the following questions to [jzamfirescupereira@cca.edu](mailto:jzamfirescupereira@cca.edu) by **Tuesday night**.
  1. When is an array useful? (Answer in 3-4 sentences, please!)
  2. Consider the following code:
    ```Processing
    int[] data; // Declare

    void setup() {
      size(100, 100);
      data = new int[5]; // Create
      data[0] = 19; // Assign
      data[1] = 40;
      data[2] = 75;
      data[3] = 76;
      data[4] = 90;
    }
    ```
    How many entries are there in the `data` array?
    
  3. Consider the following code:
    ```Processing
    int[] data1 = { 19, 40, 75, 76, 90 };
    int[] data2 = { 19, 40 };
    int[] data3 = new int[127];
    ```
    What is the value of `data1[3]`?
    
