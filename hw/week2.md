### Homework 2 (due Sunday, September 13, 2015)

**This homework has two parts:** programming practice due **Sunday**, and a required tutorial to be completed **before Tuesday night**.

#### Classes Tutorial ####

- **Assignment: Follow the [Processing Objects tutorial](https://processing.org/tutorials/objects).**

- **Assignment: Email me answers to the following questions to [jzamfirescupereira@cca.edu](mailto:jzamfirescupereira@cca.edu) by Tuesday night:** Send 3-4 sentences per question.
  1. In what ways is a class like a cookie cutter?
  
  2. What sets apart instance variables from regular variables?
  
  3. In the following code, how many instances of Ball are created in total?

```Processing
class Ball {
  float x, y;

  Ball(float x, float y) {
    this.x = x;
    this.y = y;
  }

  void display() {
    ellipse(x, y, 50, 50);
  }
}


Ball b = new Ball(100, 100);
Ball b2;

void setup() {
  size(500, 500);
  b = new Ball(120, 200);
  b2 = new Ball(35, 35);
  noStroke();
}

void draw() {
  background(255);
  fill(128, 178, 255);
  b.display();
  b2.display();
}
```  

#### Programming Practice ####

- **Assignment: Pick 5 of the 15 sketches below and recreate them, at least one must be animated.** Bonus points for adding flourishes to your sketches. Create a new [GitHub repository](../github-guide.md#to-create-a-new-repository) for this assignment, and create a new file for each of your five sketches -- include the sketch number in the file name. Email a link to your repository to [jzamfirescupereira@cca.edu](mailto:jzamfirescupereira@cca.edu) by **Sunday, September 13**.

- Not all these sketches are equally difficult -- in fact some are very challenging!

- You may find the following [Processing tutorials](https://processing.org/tutorials/) helpful:
  - The [Processing Overview](https://processing.org/tutorials/overview)
  - [Coordinate System and Shapes](https://processing.org/tutorials/drawing)
  - [Color](https://processing.org/tutorials/color)

- It may also help to read through the [Processing reference](http://processing.org/reference/) to understand all the various functions available to you.

- For extra programming help, consider following the [Khan Academy programming tutorials using Processing](https://www.khanacademy.org/computing/computer-programming/programming).

Without further ado, here are the sketches:

1. Circles in a diagonal line. Use a while loop to draw the balls in sequence. What do you know about the x and y coordinates of each ball? (Spoiler: They're the same!)
   
   ![ball-diagonal](img/hw2/ball-diagonal.png)

2. Circles in a grid. You will likely need a while loop inside another while loop!
   
   ![ball-grid](img/hw2/ball-grid.png)

3. Colored circles in a grid, random version. Check out the `colorMode` function, and HSB, in the [Processing reference](http://processing.org/reference).
   
   ![ball-grid-randoms](img/hw2/ball-grid-randoms.png)

4. Colored circles in a grid, sequential version. Check out the `colorMode` function, and HSB, in the [Processing reference](http://processing.org/reference). Note that the colors shift from left to right *and* from top to bottom!

   ![ball-grid-rainbows](img/hw2/ball-grid-rainbows.png)

5. Circles in an triangle.

   ![ball-triangle](img/hw2/ball-triangle.png)
   
6. Circles in an hourglass.

   ![ball-hourglass](img/hw2/ball-hourglass.png)

7. The grid.
   
   ![grid](img/hw2/grid.png)
   
8. Diagonal lines.

   ![diagonal-lines](img/hw2/diagonal-lines.png)

9. Diagonal lines, interrupted.

   ![big-p](img/hw2/big-p.png)

10. Random bars.

   ![random-bars](img/hw2/random-bars.png)

11. Random bars, animated.

   [![random-bars-animated](img/hw2/random-bars-animated.png)](http://youtu.be/EA9MqlY56LM)

12. Animated bars, mouse-sensitive. Check out the Processing-defined variables `mouseX` and `mouseY` in the [Processing reference](http://processing.org/reference).

   [![random-bars-mouse](img/hw2/random-bars-mouse.png)](http://youtu.be/3OAKqXS5Lkw)

13. Bouncing balls, just two.

   [![bouncing-balls](img/hw2/bouncing-balls.png)](http://youtu.be/7sfC4-4VoM4)

14. **Challenge:** Bouncing balls, more added by clicking. You may need to use an `ArrayList`.

   [![bouncing-balls-with-clicks](img/hw2/bouncing-balls-with-clicks.png)](http://youtu.be/Tnkhya3Tqu0)

15. **Challenge:** Fireworks! They should track the mouse and appear on clicks.

   [![fireworks](img/hw2/fireworks.png)](http://youtu.be/yNTUEe9cof8)
   
