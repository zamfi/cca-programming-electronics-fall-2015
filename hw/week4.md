### Homework 3 (due Sunday, September 20, 2015)

**This homework is just two programming practice sections, both due Sunday.**


**Assignment 1**: Take the following code we worked on in class, that produces a grid of randomly-colorand Balls. Modify it so that the colors in the grid are a rainbow, like in the [in-class assignment](https://youtu.be/Ida7ntOWq28). One possible set of modifications:

- Add a parameter `color c` to the `Ball` constructor function, and set `this.c` equal to that parameter.
- Modify `setup` to add a `hue` variable that increases with every ball created.

```Processing
class Ball {
  float x, y;
  float vx, vy;
  float size = 10;
  color c;
  
  Ball(float x, float y) {
    this.x = x;
    this.y = y;
    c = color(random(255), 255, 255);
    vx = random(1);
    vy = random(1);
  }
  
  void draw() {
    noStroke();
    fill(c);
    ellipse(x, y, size*2, size*2);
  }
  
  void move() {
    x += vx;
    y += vy;
    if (x < size || x > width-size) {
      vx = -vx;
    }
    if (y < size || y > height-size) {
      vy = -vy;
    }
  }
}

ArrayList<Ball> list;

void setup() {
  size(500, 500);
  colorMode(HSB);

  list = new ArrayList<Ball>();

  for (int x = 20; x < width-20; x += 20) {      
    for (int y = 20; y < height-20; y += 20) {
      list.add(new Ball(x, y));
    }    
  }
}

void draw() {
  background(255);
  
  for (int i = 0; i < list.size(); i += 1) {
    list.get(i).draw();
    list.get(i).move();    
  }
}
```

**Assignment 2**: Multipong! In this assignment, you'll start writing the code for the classic arcade game [Pong](http://en.wikipedia.org/wiki/Pong). If you're not familiar with Pong, you can play it online at [ponggame.org](http://www.ponggame.org/)!

We've already got a `Ball` class, but we also need "paddles" for the players to control that the balls will bounce from. Write a `Paddle` class that’s a template for a paddle, just like the `Ball` class is a template for a ball.

The class will be very similar to Ball, but there are a few key differences:
1. Paddles are shaped as a rectangle instead of a circle
2. Paddles only move up and down, that is, veritcally -- there's no horizontal motion

Create two paddle instances, one at each side of the canvas, a paddle's width away from the edge; they should bounce up and down.

Submit a single processing file with a `Ball` and `Paddle` class in it, that has one or more bouncing balls and two bouncing paddles.

Here’s [one way your sketch might look when run](https://youtu.be/x5nrypf_nbc).
