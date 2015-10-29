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


### Week 5: Wednesday, September 30, 2015

Lecture:
- What parts do we need to make Pong?

Lab:
- Add the following to your Paddle assignment from last week:
  - Modify the balls so they bounce off the paddles
  - Create user control. Two options:
    - Make keys on the keyboard control the paddles, or
    - Make the mouse control one of the paddles
  - Add scoring when balls pass the paddles

Here's one possible set of code that implements the three points above, using keyboard control, based on the techniques covered in class: 

```Processing
class Ball {
  float initialX, initialY;
  float x, y;
  float vx, vy;
  float size = 10;
  color c;

  Ball(float x, float y, color c) {
    this.x = initialX = x;
    this.y = initialY = y;
    this.c = c;
    vx = 2+random(1);
    vy = random(1);
  }

  void draw() {
    noStroke();
    fill(c);
    ellipse(x, y, size*2, size*2);
  }
  
  void reset() {
    x = initialX;
    y = initialY;
    vx = 2+random(1);
    if (random(1) < 0.5) {
      vx = -vx;
    }
    vy = random(2) - 1;
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
    if (x-size < leftPaddle.x + leftPaddle.w) {
      if (y > leftPaddle.y &&
          y < leftPaddle.y + leftPaddle.h) {
        vx = -vx;
      } else {
        rightScore++;
        reset();
      }
    }
    if (x+size > rightPaddle.x) {
      if (y > rightPaddle.y &&
          y < rightPaddle.y + rightPaddle.h) {
        vx = -vx;
      } else {
        leftScore++;
        reset();
      }
    }
  }
}

class Paddle {
  float x, y;
  float vy;
  float w = 15, h = 80;
  color c;

  Paddle(float x, float y, color c) {
    this.x = x;
    this.y = y;
    this.c = c;
    vy = 0;
  }

  void draw() {
    noStroke();
    fill(c);
    rect(x, y, w, h);
  }

  void move() {
    y += vy;
    if (y < 0 || y > height-h) {
      vy = 0;
      y = constrain(y, 0, height-h);
    }
  }
}

ArrayList<Ball> list;
Paddle leftPaddle, rightPaddle;
int leftScore = 0;
int rightScore = 0;

void setup() {
  size(500, 500);
  colorMode(HSB);
  list = new ArrayList<Ball>();
  list.add(new Ball(width/2, height/2, color(random(255), 255, 255)));

  leftPaddle = new Paddle(15, 150, color(0));
  rightPaddle = new Paddle(width-15-15, 150, color(0));
}

void drawScores() {
  textSize(32);
  text(""+leftScore, width/2-30, 40);
  text(""+rightScore, width/2+10, 40);
}

void draw() {
  background(255);

  for (int i = 0; i < list.size(); i += 1) {
    list.get(i).draw();
    list.get(i).move();
  }

  leftPaddle.move();
  leftPaddle.draw();
  rightPaddle.move();
  rightPaddle.draw();
  drawScores();
}

void mousePressed() {
  list.add(new Ball(mouseX, mouseY, color(random(255), 255, 255)));
}

void keyPressed() {
  if (key == 'q') {
    leftPaddle.vy = -4;
  }
  if (key == 'a') {
    leftPaddle.vy = 4;
  }
  if (key == 'o') {
    rightPaddle.vy = -4;
  }
  if (key == 'l') {
    rightPaddle.vy = 4;
  }
}

void keyReleased() {
  if (key == 'q' && leftPaddle.vy < 0) {
    leftPaddle.vy = 0;
  }
  if (key == 'a' && leftPaddle.vy > 0) {
    leftPaddle.vy = 0;
  }
  if (key == 'o' && rightPaddle.vy < 0) {
    rightPaddle.vy = 0;
  }
  if (key == 'l' && rightPaddle.vy > 0) {
    rightPaddle.vy = 0;
  }
}
```

Extend this code in the homework!

[Homework for Week 5](hw/week5.md)


### Week 6: Wednesday, October 7, 2015

Lecture:
- Arduino introduction (slides available in [pdf](img/arduino-slides.pdf))

Lab:
- Building circuits with Arduino and other electronic components!

[Homework for Week 6](hw/week6.md)

### Week 7: Wednesday, October 14, 2015

Lecture:
- Schematic how-to.
  - See [Make's guide to building a breadboard from a schematic](http://makezine.com/2012/04/02/going-from-schematic-to-breadboard/)
  - Also see [Paul Spinrad's guide to reading schematics](http://makezine.com/2011/01/25/reading-circuit-diagrams/) and [Collin's video version](http://makezine.com/2011/11/15/collins-lab-schematics/)

Lab:
-   Start with example **AnalogInOutSerial** (File > Examples > Analog > AnalogInOutSerial). Here's a simplified version of that code:
    ```arduino
    const int analogInPin = A0;  // Analog input pin that the potentiometer is attached to
    const int analogOutPin = 9; // Analog output pin that the LED is attached to

    int sensorValue = 0;        // value read from the pot
    int outputValue = 0;        // value output to the PWM (analog out)

    void setup() {
      // initialize serial communications at 9600 bps:
      Serial.begin(9600);
      pinMode(analogOutPin, OUTPUT);
    }

    void loop() {
      // read the analog in value:
      sensorValue = analogRead(analogInPin);            
      // map it to the range of the analog out:
      outputValue = map(sensorValue, 0, 1023, 0, 255);  
      // change the analog out value:
      analogWrite(analogOutPin, outputValue);           

      // print the results to the serial monitor:
      Serial.print("sensor = " );                       
      Serial.print(sensorValue);      
      Serial.print("\t output = ");      
      Serial.println(outputValue);   

      // wait 2 milliseconds before the next loop
      // for the analog-to-digital converter to settle
      // after the last reading:
      delay(2);                     
    }
    ```
    Make sure you understand what this code does. If not, ask! Here's a schematic of what your circuit should look like:
    
    ![potentiometer and LED on pin 9](img/pot-led-pin-9.png)
    
    Open the serial monitor and see what numbers are printed when you rotate the potentiometer. What's the lowest number you see? Highest?
    
    1. Modify the code so that instead of changing the brightness of the LED, the Arduino turns on or off the LED (using `digitalWrite` instead of `analogWrite`) depending on whether `outputValue` is greater or less than `127`. (Hint: You'll need an `if` statement. What's the `if` statement's condition?)

    2. Add 3 more LEDs (4 total) on pins 10, 11, and 12. (Create new variables for the pins they're connected to.) Here's a new schematic:
       ![potentiometer and LEDs on pins 9, 10, 11, and 12](img/pot-led-pins-9-10-11-12.png)
    
    3. Add new `if` statements so that the 4 LEDs make a "level meter": as you turn the potentiometer from left to right, the LEDs turn on one by one until they're all on when you've turned the potentiometer all the way.
    
    4. Replace the potentiometer in this circuit with a light-dependent resistor (LDR) in a voltage divider circuit. Here's what you should have:
    
       ![LDR and LEDs on pins 9, 10, 11, and 12](img/ldr-led-pins-9-10-11-12.png)
      
       What happens when you cover the LDR?
       
       Open the serial monitor and see what numbers are printed when you cover and uncover the LDR. What's the lowest number you see? Highest?
    
    5. *Show me your breadboard before moving on.*
    
    6. Replace your LDR with a button. Here's what you should have:
    
       ![Button and LEDs on pins 9, 10, 11, and 12](img/switch-led-pins-9-10-11-12.png)
    
       What happens?
       
       Open the serial monitor and see what numbers are printed when you push and release the button. What's the lowest number you see? Highest?
       
       Replace the `analogRead` function with `digitalRead`. What happens in the serial monitor now?
    
-   Use Arduino and Procesing function to create a digital [Etch-a-Sketch](https://www.youtube.com/watch?v=CAGcFy6CYnM#t=120s). 
    
    1. Connect two potentiometers to analog pins `A0` and `A1`. Here's a schematic:
    
       ![two potentiometers](img/two-pots.png)
    
    2. Write an Arduino sketch, using the `Serial` library, that reads the two analog inputs (using `analogRead`) and prints those values to serial port, two per line, separated by commas. The outputs should look like this in the serial monitor:

       ```
       253,124
       253,176
       253,182
       ...
       ```
    
       You will likely need both `Serial.print` and `Serial.println`. The first number should correspond to the value from pin `A0`, and the second from pin `A1`.
    
    3. Here's a Processing sketch that reads these pairs of numbers from the serial port, and then draws a line from the old coordinate to the new coordinate. But it has a bug! So it doesn't quite work. Fix the bug. (Hint: the bug isn't with the `readSerial` function!)
    
       ```processing
       // Etch-a-Sketch
       // based on a sketch by Trevor Shannon

       import processing.serial.*;

       Serial port;
       int oldX = -1;
       int oldY = -1;

       void setup() {
         size(512, 512);
         background(255);
         port = new Serial(this, Serial.list()[Serial.list().length-1], 9600);  
       }

       void drawNextLine(int x, int y) {
         if (oldX >= 0 && oldY >= 0) {
           // draw a line from the old x,y coordinates to the new x,y coordinates
           line(x, y, oldX, oldY);
         }

         // update the "old" x,y coordinates for the next frame
         oldX = x;
         oldY = x;
       }  

       void draw() {
         int[] values = readSerial(2);
         if (values != null) {
           drawNextLine(values[0], values[1]);
         }
       }

       void mouseClicked() {
         background(255);
       }

       int[] readSerial(int minValues) {  
         int x; int y;
         String s = port.readStringUntil('\n');
         if (s != null) {
           String[] parts = s.substring(0, s.length()-2).split(",");
           int[] values = new int[parts.length];
           for (int i = 0; i < parts.length; i++) {
             values[i] = int(parts[i]);
           }
           if (values.length < minValues) {
             return null;
           } else {
             return values;
           } 
         } else {
           return null;
         }
       }
       ```
    
    4. Replace the potentiometer on pin `A1` with a sensing resistor of your choice in a voltage divider -- you can use an LDR like in the previous example, or a force-sensitive resistor, or a thermistor, or... A digital multimeter may help in picking the right corresponding resistor.
    
    5. Modify the Processing code so that it draws a graph of the value of the second coordinate only (that is, the number that changes when you rotate the potentiometer that you've connected to pin `A1`).
       
       You'll need to modify the `drawNextLine` function so that it doesn't draw a line from `x`,`y` to `oldX`,`oldY` anymore. Instead, it will use a slowly-increasing `x` coordinate. Try these two changes:
       
       1. Create a new variable called `columnPosition` and use that instead of `x` in the `line` function. 
       
       2. Increase `columnPosition` a little bit on every frame.
    
    6. **Challenge**: Also graph the value of the first coordinate!

[Homework for Week 7](hw/week7.md)


### Week 8: Wednesday, October 21, 2015

Lecture:
- Homework review
- More electronics

Lab:
- Continuiation of last week's lab; pong with potentiometers.

[Homework for Week 8](hw/week8.md)


### Week 9: Wednesday, October 28, 2015

Lecture:
-  Practice Quiz review
-  Motors, transistors, and motor drivers.

Lab:
-  Experiments with motors!
   
1. Build the following circuits, one at a time, and observe what happens. Pay particular attention to the speed and strength of the motors. (For the latter two schematics, use the blink sketch or write your own.)
  
   ![Motor Circuits](img/motor-experiments.png)

2. In the third schematic above, you're using the transistor as a digital switch. As we discussed, you can control a motor using 4 switches in this configuration, called an H-Bridge:
  
   ![H-bridge](img/h-bridge.png)

3. Using switches `S1`, `S2`, `S3`, and `S4`, figure out how to open or close each switch to cause current to flow from left to right through the motor (spinning it "forward") and from right to left through the motor (spinning it "backward"). Make a handy table.

4. Note that your table never has switches `S1` and `S3` both closed or `S2` and `S4` both closed -- why?

5. That means that the circuit we want is effectively this:

   ![Two switches](img/single-motor-circuit.png)
  
6. This schematic merges `S1` and `S3` into a single switch on the left, and `S2` and `S4` into a single switch on the right. For each switch, there are now three positions: up, down, or "off" (that is, not connected to anything). 

7. This circuit is created for us in the form of a "Half-H Bridge" integrated circuit. We'll use the [SN7544](http://www.ti.com/lit/ds/symlink/sn754410.pdf) in class -- but there are many others (like the [L293D](http://www.ti.com/lit/ds/symlink/l293d.pdf)), with the main difference being voltage and current ratings. Here's what it looks like. Note the position of the notch.
  
   ![Quad H-bridge](img/quad-h-bridge-chip.png)
  
8. The inputs to the chip are the pins labeled with `A`, e.g., `1A`, `2A`, etc. The corresponding outputs (that you connect to your motor) are the pins labeled with `Y`, e.g., `1Y`, `2Y`. Send a high voltage on the input pin, and the output pin will be connected to a high voltage -- and similarly with low voltage.

9. Wire up your motor to one side of the H-bridge.

10. Write a function in Arduino, `void forward()`, that spins the motor forward, using pins connected to `1A` and `2A`

11. Write an analogous function, `void reverse()`, for the reverse.

12. Write an Arduino sketch that uses your two functions to spin the motor forward for 2 seconds, waits for 1 second, then reverses for 1 second.

13. Add a potentiometer to your sketch -- when rotated one way, the motor should spin in one direction, when rotated the other way, the motor should spin in the other direction. In the middle range, the motor shouldn't spin at all. (What code can you write to stop the motor?)

14. Add a second motor, connect it to the other half of the integrated circuit.

[Homework for Week 9](hw/week9.md)