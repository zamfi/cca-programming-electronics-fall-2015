# CCA Programming & Electronics, Fall 2015

This course repository contains homework assignments, useful guides, and code for "Programming & Electronics" at CCA, Fall 2015.

The syllabus for this course is available [in this repository](syllabus.pdf).

### Week 1: Wednesday, September 2, 2015

Lecture:
- Inspirational Videos
- Introductions
- What is programming?
- Goals & course details

Hands-on activities:
- Human Embodiment of Programmer & Robot
  - Programs generally run line-by-line.
  - While loops, if statements, and functions break that up.
  

Videos:
- Basic robots
  - [Coffee-can robot](http://www.youtube.com/watch?v=b0mIshBIbvI#t=24)
  - [Tree-climbing robot](http://www.youtube.com/watch?v=zkpH1BjD6Wc)
  - [Self-balancing robot](http://www.youtube.com/watch?v=Tw9Jr-SPL0Y)
  - [Insect robot](http://www.youtube.com/watch?v=tOsNXg2vAd4#t=120)
  - [Treadbot](http://www.youtube.com/watch?v=YblSltHDbIU)
  - [Velociraptor robot](http://www.youtube.com/watch?v=lPEg83vF_Tw)
- Drink-makers
  - [Textspresso](http://www.youtube.com/watch?v=kx9D74t7GD8#t=89)
  - [The Inebriator](http://www.youtube.com/watch?v=WqY7fchs7H0)
- Art bots
  - [Floating Couch](http://vimeo.com/72826106)
  - [Wooden Segment Mirror](https://www.youtube.com/watch?v=BZysu9QcceM#t=36)
  - [Cubli: Floating Cube](https://www.youtube.com/watch?v=n_6p-1J551Y)
  - [Arc-o-matic](http://vimeo.com/57082262#at=130)
  - [Robo Faber](http://vimeo.com/78771257)
  - [Eggbot](https://www.youtube.com/watch?v=w4cdbV2oaEc)
- Computer Numerical Control (CNC)
  - [Shapoko / tinyg](http://www.youtube.com/watch?v=pCC1GXnYfFI#t=11)
  - [Makerbot Replicator](http://www.youtube.com/watch?v=NAbiAzYhTOQ)
- Music
  - [Laser harp](http://www.youtube.com/watch?v=sLVXmsbVwUs#t=20)
- Vacuuming
  - [Roomba](https://www.youtube.com/watch?v=0DNkbZvVYvc)

[Homework for Week 1](hw/week1.md)


### Week 2: Wednesday, September 9, 2015

Lecture:
- Homework Review

Lab:
- Creating sketches with Processing. Write code to create the following sketches in Processing:

1. ![one](img/one.png)

2. ![two](img/two.png)

3. ![three](img/three.png)

4. [![four](img/four.png)](http://www.youtube.com/watch?v=jWNXFlGHuPA)

5. ![five](img/five.png)

6. Look through the [Processing reference](http://processing.org/reference). Pick a function, and use it in a new sketch of your own choosing.

[Homework for Week 2](hw/week2.md)

### Week 3: Wednesday, September 16, 2015

Lecture:
- Homework Review: understanding & improving code
- Objects!

In today's session, we looked at how you might transform a piece of code that shows a ball bouncing around a screen to use classes. Here's a graphic showing what we did, exactly:

![bouncing ball with or without classes](img/adding-some-class.png)

In the diagram above, the blue boxes show the modified code; the left side of each blue box pair shows the traditional code, while the right side shows the class-enabled code that achieves the same effect. The red arrows show where inside the `Ball` class the traditional code goes.

The variables tracking the position, speed, and radius of the ball, as well as the code for drawing and moving the ball, are all put into the class `Ball`. We say that the variables and functions are "encapsulated" in the `Ball` class. In Processing, `Ball` now describes a new type, like `int` or `float`, but more complex, a "compound" type. Whenever we create an "instance" of the `Ball` class, by writing `new Ball()`, we are creating a new **container** object that includes its own `x`, `y`, `vx`, `vy`, and `radius` variables -- the instance we create **contains** those 5 other variables. Then the `draw` and `move` functions are called **on an object**, for example, `b.move()` is the `move` function of the `b` object, it only uses and alters the variables inside the `b` object.

You can create as many instances of a class as you like, giving them different names (for example, `Ball b2 = new Ball()`) or storing them in arrays. Each will be independent, and calling a function on one object will only affect that one object's variable. The class *describes* the object, and the *instance* contains all the data and can have its functions used.

Try it in the homework!

[Homework for Week 3](hw/week3.md)

### Week 4: Wednesday, September 23, 2015

Lecture:
- Homework Review: classes
- Tools for writing code
- Arrays and ArrayLists

In today's session, we looked at how you can use an `ArrayList` object to store large numbers of objects. Here's a graphic showing how we went from two `Ball` objects to 529 `Ball` objects in a grid:

![bouncing balls with or without arraylists](img/enlisting-balls.png)

In the diagram above, the blue boxes highlight the changes we made. (Note that the `Ball` class itself hasn't changed! What's changed is how the code keeps track of the `Ball` instances we create.) 

In the traditional code, each ball needs a new variable (`b1` or `b2`, for example). To display 529 `Ball` objects in a grid in the traditional way would require creating 529 `Ball`-type variables -- what a nightmare! Instead, the code creates a new object of type `ArrayList<Ball>`, called `list`, that it'll use to keep track of the 529 `Ball` objects.
  
You can think of an `ArrayList` as a new type of variable that can hold many other variables of the same type. For example, `ArrayList<Ball>` holds `Ball` objects, but `ArrayList<Particle>` would only hold `Particle` objects. If you haven't yet, take a look at the [Processing.org ArrayList reference](https://processing.org/reference/ArrayList.html).
  
The rest of the code interacts with the `ArrayList` object in two ways. First, it uses the `add` function to add `Ball` objects to the list inside of `setup`. Then it picks out those objects using from the `list` using the `get` function to draw and move them. In `setup`, two `for` loops give each `Ball` object its own `x` and `y` position in the grid of balls. In `draw`, a single `for` loop to `draw()` and `move()` each ball.

Lab: 

Write code to create the following sketches in Processing:

1. Animated circle drawing
   
   [![one](http://img.youtube.com/vi/35Ohe-EO1Ko/maxresdefault.jpg)](https://youtu.be/35Ohe-EO1Ko)

2. A grid of bouncing circles
   
   [![two](http://img.youtube.com/vi/Ida7ntOWq28/maxresdefault.jpg)](https://youtu.be/Ida7ntOWq28)
   

[Homework for Week 4](hw/week4.md)
