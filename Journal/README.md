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
