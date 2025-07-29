## Dot‑Board Build Journal
---
Title: "Dot Board"
Author: "Sarah"
Description: "Custom keeeb
created_at: "2025-07-25"
Total time spent: 22.5
---

## July 22 – First Schematic (7.5 hours)
It was one of those nights when the rain had just stopped, my playlist was stuck on Lo-fi beats, and I was just sitting on my bed, staring at my half dead old keyboard. The thing looked like it had survived a zombie apocalypse. And the typing feel? Ugh, don’t even ask. Every keystroke felt like I was arguing with a soggy biscuit. That’s when something clicked. Not on the keyboard, though. In my brain. I thought, “Why not just make my own keyboard?” Not just assemble parts, but actually design everything—the PCB, the schematic, and the whole look. And thus, the dot‑Board idea was born, right there under my cheap fairy lights.

I opened up EasyEDA Pro and started a new project called “dot-Board v0.” No fancy names, just straight to the point. First, I decided I wanted something clean and minimal, like the Apple aesthetic but with actual soul. The layout in my mind was around 60%, no extra fluff, just pure keys and function. I dropped in a Pro Micro clone in the schematic view yeah, the classic one. I know it’s old, but it works.


<img width="504" height="277" alt="image" src="https://github.com/user-attachments/assets/7d244594-3418-4e6c-a06f-15d6c3f88d2d" />



Then came the diodes. I started building out the switch matrix, row by row. Seven rows, five columns nothing too crazy, but enough to feel custom. I carefully placed each 1N4148 diode in series with the switches, making sure the cathode was facing away from the MCU. I’ve messed that up before, trust me, it’s not fun to desolder thirty mistakes. I labelled every net properly this time: ROW0 to ROW6, COL0 to COL4. No shortcuts.

<img width="848" height="636" alt="Screenshot 2025-07-29 224526" src="https://github.com/user-attachments/assets/340fa182-13bf-4072-a528-ec5c9f8db0ea" />

By the time I ran the ERC, the clock had struck 3:30 AM. Zero errors. That moment felt like my brain gave me a high five. I exported the netlist and called it a night, but I already knew tomorrow was going to be all about PCB layout and chai.

## July 24 – PCB Layout and Routing Grind (9 hours)
The next morning—or should I say afternoon—I woke up at 1 PM. Still slightly groggy, but as soon as I saw my notebook filled with layout sketches, I snapped out of it. I booted up EasyEDA’s PCB view and imported the schematic. All the footprints were floating around like pieces of a puzzle. The default board outline was a random square, so I quickly changed it to a custom 280 × 95 mm shape. That size gave me enough breathing room for key spacing while keeping it compact on my desk.

<img width="953" height="458" alt="image" src="https://github.com/user-attachments/assets/4f4f178b-824a-4547-ad69-f7dc68dcd5db" />


The first thing I anchored down was the Pro Micro. I placed it bottom center, with enough clearance on the USB side for a front facing cutout. Then I lined up the switch footprints. This was the most satisfying part. Dragging and dropping each MX switch pad onto the grid, making sure the spacing was exactly 19.05 mm apart, and aligning everything to perfection. I kept imagining the keycaps I’d put on later. I left space on the top-right corner for an OLED too even though I hadn’t added it to the schematic yet. I might revise it later.

Next, I routed the power rails. Thick 32mil traces for GND and VCC, branching out from the USB-C breakout area. I used via stitching to link the top and bottom GND planes, then filled the rest of the space with ground copper pour. For the switch matrix, I went with 10mil traces for both rows and columns. I routed the rows on the top layer and the columns on the bottom, jumping between layers using vias whenever traces got tight.

<img width="988" height="449" alt="image" src="https://github.com/user-attachments/assets/9b5d287d-a46c-4a27-b3c5-1708c9b651bf" />


Around hour four, things started to get messy. A couple of nets refused to cooperate—they kept auto‑snapping to weird corners. I switched off the autorouter and did everything manually, nudging each trace pixel by pixel. For the optional buzzer, I made a small zone in the bottom left corner. I added an M3 mounting hole near each board corner, placed evenly from the edges, and added a silkscreen logo right above the Pro Micro area.

I enabled 3D preview and took a deep breath. Seeing the board in black solder mask with sharp white silkscreen lines made me smile like a madman. It felt like the digital version of holding your own invention. I tweaked the mounting hole alignment once again, ran the DRC, and fixed the last few overlapping traces.


<img width="941" height="417" alt="image" src="https://github.com/user-attachments/assets/3ebe1cdf-cdcd-4228-9243-110fccabd583" />





## July 25 – Bill of Materials and Case Design (5 hours)
I started the day with a mug of hot coffee and an Excel sheet open in front of me. The dreaded BOM. Everyone skips it till the end, but I wanted to get it done early. I listed out every component I used and where I’d get it from.

Sixty‑one Outemu Red switches, ₹1,850 from cosmicbyte.in. A solid set of PBT keycaps, ₹2,450 from neomacro.in. Hot‑swap sockets from Shaarvi Electronics, ₹1,150 for a pack of seventy. The Pro Micro clone, ₹800 on Amazon. Diodes, ₹90. A pack of resistors and caps, ₹130. USB-C breakout, ₹200. Screws, standoffs, and plastic feet, ₹180 total. After some rounding, the grand total stood close to ₹8,900, or around $107. Not bad for a full custom board that’s all mine.


<img width="1449" height="707" alt="Screenshot 2025-07-29 215812" src="https://github.com/user-attachments/assets/eca1e65f-91fe-4c5f-8455-e0a8066ec88c" />



Then I moved on to Fusion 360. The PCB outline was already clear in my head. I sketched the base plate, made it 3mm thick, then extruded the sidewalls to 11mm. I added slots for every key switch, rectangular holes for the stabilizers, and a front cutout for the USB-C port. On the top side, I gave each key a perfect 15×15mm hole, spaced just right. The mounting holes were easy to align using the PCB measurements.

<img width="910" height="521" alt="Screenshot 2025-07-29 225553" src="https://github.com/user-attachments/assets/eac21089-f1cd-419e-92f4-b0650615e9e2" />

I made a second body for the bottom case, this time with screw posts that matched the standoff placements on the PCB. I used the Combine tool to cut matching holes and tested everything using joints. No interference, no overlaps. Then I added a subtle side logo that says “dot-Board” in lowercase, using the Text tool and extruding it just 0.5mm out.

<img width="821" height="573" alt="Screenshot 2025-07-29 225539" src="https://github.com/user-attachments/assets/9933654b-7b94-4833-9b45-5ba2c1de229a" />


Finally, I exported both STL files and dropped them into Cura. At 0.2mm layer height, each half would take about 4.5 hours to print. I configured the bed layout for my Ender 3 and saved the G-code. It was around 7 PM by the time I shut down Fusion. I hadn’t even printed anything yet, but seeing the rendered preview made me whisper: “You’re real now, buddy.”


<img width="896" height="434" alt="Screenshot 2025-07-28 231415" src="https://github.com/user-attachments/assets/66b92d1c-9eb9-4604-847e-096c9b0e5d67" />

<img width="1080" height="562" alt="Screenshot 2025-07-28 231433" src="https://github.com/user-attachments/assets/97f06a1e-f699-4e45-8e08-9b518188afcb" />



<img width="827" height="507" alt="Screenshot 2025-07-29 225708" src="https://github.com/user-attachments/assets/43bc5e97-a341-4c85-933d-c4da70e2a261" />
<img width="971" height="568" alt="Screenshot 2025-07-28 232150" src="https://github.com/user-attachments/assets/6c72bbda-3e2a-450e-9447-12a0b56912d4" />


<img width="807" height="454" alt="Screenshot 2025-07-29 225951" src="https://github.com/user-attachments/assets/2eed1036-0e29-4b34-811a-7bd5a028f93e" />


July 26 – QMK Firmware Setup (1 hour)
With the design all set and the STL files ready to print, I decided to dive into the firmware part—at least the initial setup—because I wanted to lock in the layout while it was still fresh in my head. I opened up the QMK Configurator and began mapping the layout exactly as I imagined it during design. All the main keys were straightforward, and I kept things clean: a compact typing layout on layer 0, and a secondary layer for arrow keys, volume control, and maybe media playback later on.
I added a function key to toggle layers, set up MO(1) on the bottom row, and assigned RESET to one of the top-right keys—just in case I needed it during flashing. Even though I hadn't hooked up the board yet, it felt cool seeing the visual layout evolve into something that was truly mine. Once everything looked solid, I downloaded the .hex and .json files and saved them in my firmware folder labeled “dot‑Board_v0”.


