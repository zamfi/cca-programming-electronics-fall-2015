### Homework 10 (parts due Sunday, parts due at noon on Tuesday, November 10, 2015)

This assignment has two parts: programming practice, due Sunday, and a project proposal, due Tuesday.

- Programming practice!
  
  Run the following code -- a slightly modified version of the *Handles* example that comes with Processing.
  
  ```Processing
  /**
    * Handles. 
    * 
    * Click and drag the white boxes to change their position. 
    **/
 
  Handle[] handles;

  void setup() {
    size(640, 360);
    int num = height/15;
    handles = new Handle[num];
    int hsize = 10;
    for (int i = 0; i < handles.length; i++) {
      handles[i] = new Handle(width/2, 10+i*15, 50-hsize/2, 10, handles);
    }
  }

  void draw() {
    background(153);
  
    for (int i = 0; i < handles.length; i++) {
      handles[i].update();
      handles[i].display();
    }
  
    fill(0);
    rect(0, 0, width/2, height);
  }

  void mouseReleased()  {
    for (int i = 0; i < handles.length; i++) {
      handles[i].releaseEvent();
    }
  }

  class Handle {
    int x, y;
    int boxx, boxy;
    int stretch;
    int size;
    boolean over;
    boolean press;
    boolean locked = false;
    boolean otherslocked = false;
    Handle[] others;
  
    Handle(int ix, int iy, int il, int is, Handle[] o) {
      x = ix;
      y = iy;
      stretch = il;
      size = is;
      boxx = x+stretch - size/2;
      boxy = y - size/2;
      others = o;
    }
  
    void update() {
      boxx = x+stretch;
      boxy = y - size/2;
    
      for (int i=0; i<others.length; i++) {
        if (others[i].locked == true) {
          otherslocked = true;
          break;
        } else {
          otherslocked = false;
        }  
      }
    
      if (otherslocked == false) {
        overEvent();
        pressEvent();
      }
    
      if (press) {
        stretch = constrain(mouseX-width/2-size/2, 0, width/2-size-1);
      }
    }
  
    void overEvent() {
      if (overRect(boxx, boxy, size, size)) {
        over = true;
      } else {
        over = false;
      }
    }
  
    void pressEvent() {
      if (over && mousePressed || locked) {
        press = true;
        locked = true;
      } else {
        press = false;
      }
    }
  
    void releaseEvent() {
      locked = false;
    }
  
    void display() {
      line(x, y, x+stretch, y);
      fill(255);
      stroke(0);
      rect(boxx, boxy, size, size);
      if (over || press) {
        line(boxx, boxy, boxx+size, boxy+size);
        line(boxx, boxy+size, boxx+size, boxy);
      }

    }
  }

  boolean overRect(int x, int y, int width, int height) {
    if (mouseX >= x && mouseX <= x+width && 
        mouseY >= y && mouseY <= y+height) {
      return true;
    } else {
      return false;
    }
  }
  ```
  
  1. Find the line of the code where the each handle's color is set, and modify it so that the color depends in some way on the value of the handle. Bonus points for HSB.
  2. **Optional challenge:** Draw a rectangle that covers the black area to the left of each handle, in the same color as the color of the handle (as modified in part 1).

- Write a proposal for your final project, and **[send me a link](mailto:jzamfirescupereira@cca.edu) by Tuesday at noon**.
  
  Create a new github repository for your project, and modify the README.md file to include these four sections, each of which should have a heading and a description. (To learn about formatting text in .md files, read [this tutorial](https://help.github.com/articles/markdown-basics/).)
  
  - **Summary**: A few paragraphs (half a page?) or so describing the goals of your project. Include what types of inputs/outputs/data it will use, and how it will be interactive or responsive to the environment.
  
  - **Component Parts**: From what pieces will you build your project? Will you build or buy those pieces?
  
  - **Challenges**: What do you anticipate will be the hardest and most time-consuming parts?
  
  - **Project Timeline**: What parts of the project do you anticipate you will complete in each of the next 5 weeks?
  
  Your proposal should be thoughtful, complete, and should take into consideration the feedback you received from your classmates and from me on Wednesday. You can always change what you're doing after you send me proposal, but your proposal should describe a complete project.
  
  The final project is your opportunity to put to work what you've learned so far in class, and to build the skills you're most interested in taking with you forward into your career. *Each assignment is in the project sequence is required, so put in the time to ensure that each is complete and well-considered!*

  