### Homework 11

This homework assignment is two project project-related assignments and one Arduino programming practice.

#### Project Homework (due Monday, November 16, 11pm)

1. Start your final project's **debug log**.
  
   I'd like you to keep a **debug log** for your final project. Every time you run in to unexpected behavior in your project (a bug, a component that works differently than you thought, or something else), make an entry in your log. Describe the following:
  
   1. In a sentence, explain the behavior you expected.
   2. In a sentence, explain the observed behavior.
   3. Formulate a hypothesis about what might be causing the mismatch: what part of your code or what part of your circuit is behaving in a way you don't expect?
   4. Test your hypothesis: what action can you take you determine if your hypothesis is true?
   5. What is the result of your test?
   6. Repeat steps iii-v above until you resolve your "bug".
   
   This is a serious bit of work, but it will help you develop very critical skills in debugging; if there is only one valuable thing you take from this class, it will be this ability. Don't skimp on it!

   **The debug log is especially useful now, as you experiment with the pieces that will eventually make up your final project.**

   **Create a `debug-log.md` file in your final project repository, and keep your notes in there. [Send me a link to your file](mailto:jzamfirescupereira@cca.edu) (it should have a record of what you've done so far!) by Monday night, 11pm**.

2. Draft a "Bill of Materials" for your project: this is a list of the components you'll need to build your project. Each entry in the list should include a description, and a "source": where you'll get the part -- a link if you plan to buy it, or "Hybrid Lab" if the lab has one you plan to use, but please confirm in the lab that the part is available! 

   **Create a `bill-of-materials.md` file in your final project repository. [Send me a link](mailto:jzamfirescupereira@cca.edu) by Monday night, 11pm**.

3. **Bring all the parts on your Bill of Materials with you to class this week!** (In addition to your laptop, Arduino, etc.)


#### Arduino Practice (due before class on Wednesday, November 18)

1.  Read the [`BlinkWithoutDelay`](https://www.arduino.cc/en/Tutorial/BlinkWithoutDelay) tutorial sketch and try to understand it. What exactly is going on? (You can use the on-board LED marked `L`, you don't need to add the external LED they show in the diagrams.)

   Send me answers to the following questions:
   
   - What exactly is the role of the `previousMillis` variable?
   - What exactly does the `if` statement check? Explain in your own words what `currentMillis - previousMilis >= interval` means.
   - This code blinks the LED on for a second and off for a second. What modification could you make to blink a second LED on for 220 milliseconds and then off for 220 milliseconds? (Write the code or describe in detail what changes you would make.)
   
2. Take a look at this modified version of `BlinkWithoutDelay`:
   
   ```arduino
   // constants won't change. Used here to set a pin number:
   const int ledPin =  13;                // the number of the LED pin
 
   // Variables will change:
   int majorState = LOW;                  // ledState used to set the LED
   int minorState = LOW;
 
   // Generally, you should use "unsigned long" for variables that hold time
   // The value will quickly become too large for an int to store
   unsigned long previousMillis = 0;      // will store last time LED was updated
   unsigned long previousMillis2 = 0;     // will store last time LED was updated
 
   // constants won't change:
   const long majorInterval = 5000;       // major interval at which to blink (milliseconds)
   const long minorInterval = 500;        // minor interval at which to blink (milliseconds)
   const long minorDuration = 50;         // minor duration for on-time.
 
   void setup() {
     // set the digital pin as output:
     pinMode(ledPin, OUTPUT);
   }
 
   void loop() {
     // check to see if it's time to blink the LED; that is, if the
     // difference between the current time and last time you blinked
     // the LED is bigger than the interval at which you want to
     // blink the LED.
     unsigned long currentMillis = millis();
 
     // here's the major state: on or off.
     if (currentMillis - previousMillis >= majorInterval) {
       // save the last time you blinked the LED
       previousMillis = currentMillis;
 
       majorState = ! majorState;
     }
 
     // here's the minor state: short flashes within that on or off pattern
     if (minorState && currentMillis - previousMillis2 >= minorInterval) {
       previousMillis2 = currentMillis;
       minorState = !minorState;
     } else if (! minorState && currentMillis - previousMillis2 >= minorDuration) {
       previousMillis2 = currentMillis;
       minorState = !minorState;
     }
 
     // set the LED with the state of the variables:
     if (majorState) {
       digitalWrite(ledPin, minorState);
     } else {
       digitalWrite(ledPin, ! minorState);
     }
   }
   ```
   
   Without running it, can you figure out what this code does? [Email me](mailto:jzamfirescupereira@cca.edu) a description.