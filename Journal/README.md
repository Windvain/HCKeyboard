# Journal
## 26th July: Working on Ideas and Designs (00:40 ~ 1:30)
Sketched out a keyboard that I would like by addressing my likes and dislikes with my current keyboard.

**Pros:**
- LINEAR SWITCHES. Gosh I love them.
- The use of the `Fn` key for controlling the LED.
- The design of my current keyboard is simple and quite small.

**Cons:**
- The `F1~F12` keys require `Fn` to be pressed for them to be accessed, so they aren't convenient for shortcuts.
- The `Fn` key on my keyboard has too many bindings, causing me to sometimes press these keybinds on accident.
- I personally use the `Delete` button quite a lot, so having it tied to `Fn` is annoying.
- The keyboard has a slight incline, which hurts my wrist after typing for too long.

From all of these points, I decided on:
1. **Layout:** 75%, so that I get easy access to the `F1~F12` keys.
2. **Design:** As small a form factor as I can make, and as simple as possible.
3. **Incline:** None. 0 degrees, and no feet.
4. **Switches:** Linear switches, kind of switches TBD.
5. **Keycaps:** TBD.

Some things I had to sacrifice: \
The right portion of the keyboard had to, unfortunately, be left empty. This is due to the usage of the 
Raspberry Pi Pico as the microcontroller in this project.

Proof: \
![Image 1](<Day 1/Prototyping.jpeg>) \
![Image 2](<Day 1/Final Layout.png>)

## 27th July: Digitalizing Physical Layout and deciding on keyboard matrix. (11:40 ~ 12:44)
I then used [](keyboard-editor.com) to turn my sketch into an image. Decided on spacng out the `F1~F12 keys`
to make them distinguishable from the `1~0 keys`, so 1 key had to be removed. Other than that, added more space
for the Raspberry Pi Pico to the right of the keyboard. (Hopefully that will fit, I'm just estimating its size visually)

Took a while to get used to typing out the JSON file, but in the end I got a basic layout that looked like this:
![Image 3](<Day 2/Finished Basic Layout.png>) 

I was scared that the microcontroller wouldn't fit into the 1u by 4u space on the right, so I decided to
add more space by seperating the `F1~F12` keys.
![Image 4](<Day 2/Finished Layout Prototype.png>)

Drawing the keyboard matrix was... interesting. Because of the reserved space taken up by the microcontroller,
I found it very hard to draw a sensible keyboard matrix that worked with the `Right Arrow` key. Either I had to
take up another GPIO pin for only 1 key, or I could route the `Enter` key's trace over to the key. I ended up picking
the latter decision, which might come back to bite me when I make the PCB.
![Image 5](<Day 2/Finished Matrix.png>)

## 27th July: Starting work on the PCB. (13:00 ~ 17:54)
Ended up just using one extra GPIO pin for the `Right Arrow` key. \
First, I installed the marbatlib library for keyboard schematics, then started work on the PCB.
Honestly, making the keyboard matrix was the easy bit. Make a switch, copy it in a grid, then remove all of the unmapped keys.
![Image 6](<Day 2/Schematic Matrix.png>)

Thought about adding LEDs to my keyboard, but since they are tiny and have to be hand-soldered, theres a high likelihood
that they would break off during usage. And they are also a pain to solder, no.

![Image 7](<Day 2/Half Done.png>) \
![Image 8](<Day 2/Finished Layout.png>)

Well, well, well. Turns out that after finishing the layout, I realized that the connections were kind of, strange.
When I rechecked my schematic, I realized that the switches for **4 entire rows** were named incorrectly, and so I had to
redo all of those rows again.

![Image 8](<Day 2/Schem Annotation Order.png>) \
![Image 9](<Day 2/Redo.png>) \
![Image 10](<Day 2/Finished Redo.png>)

After redoing the keyboard, I drew in some of the traces before clocking off for dinner.
![Image 11](<Day 2/Stopping for Dinner.png>)

## 27th July: Finished PCB (19:50 ~ 20:21)
Finished the PCB! Drew all of the traces in, and checked using the Design Rules Checker tool.
There are 2 warnings that showed up though, stuff about the USB port of the Raspberry Pi Pico clipping the board.
It **shouldn't** be an issue though.

![Image 12](<Day 2/Traces Made.png>) \
![Image 13](<Day 2/PCB DONEEEEE.png>)
