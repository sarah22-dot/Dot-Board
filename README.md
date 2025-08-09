# Dot-Board
dot‑Board was never meant to be just another mechanical keyboard. It was built for a moment, for a vibe, for a challenge. The entire thing came together during Hack Club’s Highway event, where we were supposed to not just build something, but make it our own. I put my energy into what I love the most designing the PCB and modelling the case. While others were wiring or coding, I was deep inside Fusion 360 and EasyEDA Pro, trying to make sure every detail felt precise and intentional.

It started off as a late-night sketch in my notes app. I wanted something compact but not boring, logical but still unique. A grid layout made the most sense ortholinear, neat rows and columns, the kind of layout that just looks satisfying when you view it from topdown. I fired up EasyEDA Pro and began building the schematic from scratch. No template, no copy-paste from someone else's build. I dropped the Pro Micro, mapped each row and column with proper matrix logic, and added footprints for diodes and a rotary encoder. The goal was clarity and flow every trace should feel like it belongs.



<img width="931" height="472" alt="image" src="https://github.com/user-attachments/assets/aeabdb92-a36b-4475-9e38-1c86e101260e" />


Once the schematic was wired up, I moved to the PCB layout view and began placing the switches in a tight grid. I spent hours just nudging parts to get clean alignment. I added a compact reset switch footprint, labeled the layers carefully, and did final cleanup to make sure the silkscreen looked aesthetic. I chose 1.6 mm board thickness, standard FR4. Then I exported the Gerbers and submitted them to JLCPCB with the deadline pressure running in the back of my head.

<img width="942" height="374" alt="image" src="https://github.com/user-attachments/assets/6221e16c-eaee-43ba-a9e9-e2cce0bd1936" />


<img width="967" height="630" alt="image" src="https://github.com/user-attachments/assets/f6e5cddb-7b39-4a2a-86db-616fd6ffa705" />



At the same time, I jumped into Fusion 360 to work on the case. The case wasn’t just a box to hold the PCB it had to be clean, functional, and vibe with the layout. I designed a simple sandwich-style build, with a flat top plate that holds the switches snugly, and a lower base tray with screw mounts. I gave it slight curvature along the sides, nothing dramatic, just enough so it wouldn’t feel sharp in the hand. There was a cutout for the USB port and small standoffs inside so the board would sit at the right height without needing extra spacers.
<img width="821" height="573" alt="image" src="https://github.com/user-attachments/assets/6cc37e1d-cb1c-48d4-b50f-41464796fe79" />

<img width="910" height="521" alt="image" src="https://github.com/user-attachments/assets/0c728a0c-1f18-403f-ade0-7d4640e27d6f" />

<img width="1008" height="591" alt="Screenshot 2025-07-29 224610" src="https://github.com/user-attachments/assets/fc4d12ff-5968-467d-908b-0d33eb7b7393" />


The project wasn’t about perfection—it was about putting something together that you could be proud of. I didn’t assemble the keyboard physically, but seeing the design take shape and sharing it with others during the event felt like enough. I handed over the filesGerbers, STEP files, BOM references to the rest of the team or anyone who wanted to build it physically. It felt good knowing someone out there could finish what I started and maybe even add their own twist to it.

<img width="827" height="507" alt="image" src="https://github.com/user-attachments/assets/ecd73e3a-03d5-4a3a-ba30-d505c7d73a60" />


dot‑Board, to me, represents the kind of project that grows in a weekend but stays in your mind for a long time. The kind where you learn more by doing than reading. I figured out new quirks in EasyEDA, got better at 3D design in Fusion, and actually worked on finishing something under a deadline with that good kind of pressure. It’s not just a keyboard—it’s a slice of that Hack Club energy, captured in traces and plastic.

<img width="735" height="477" alt="image" src="https://github.com/user-attachments/assets/6cb4e2d7-283a-4184-81a1-a72b7a74e5ae" />

<img width="807" height="454" alt="image" src="https://github.com/user-attachments/assets/6c1f9533-379d-4df6-8507-723b762f7cea" />

Even though I didn’t solder a single switch for this board, I still feel connected to every part of it because I designed it to work, to look sharp, and to invite others to complete it. That’s the spirit of dot‑Board. It starts with a dot, but you never know where it goes.


## updated case

<img width="500" height="299" alt="Screenshot 2025-08-06 121027" src="https://github.com/user-attachments/assets/cc47bb53-64e8-46f8-8aa2-0797802c98c6" />

<img width="734" height="321" alt="Screenshot 2025-08-06 121020" src="https://github.com/user-attachments/assets/8fef5271-eaf6-48b7-974d-1ccfec156f74" />

<img width="844" height="402" alt="Screenshot 2025-08-06 121011" src="https://github.com/user-attachments/assets/b9e9c361-6656-4cf2-a863-2adc57477678" />

<img width="832" height="503" alt="Screenshot 2025-08-06 120942" src="https://github.com/user-attachments/assets/615d35ba-ad12-4110-b1ca-4533ffbf2895" />

## added logo on top
<img width="826" height="563" alt="image" src="https://github.com/user-attachments/assets/3bb74a7e-5cd5-4746-81b6-7205cfa4dc4f" />


## BOM
| Component                          | Source & Link       | Qty   | Total Cost (INR) | Total Cost (USD) |
| ---------------------------------- | ------------------- | ----- | ---------------- | ---------------- |
| Gateron Yellow Mechanical Switches | Amazon.in (70‑pack) | 62    | ₹2,400           | \$25             |
| PBT Dye‑sublimated Keycaps (Black) | neomacro.in         | 62    | ₹2,550           | \$30             |
| Kailh Hot‑swap Sockets             | neomacro.in         | 62    | ₹1,300           | \$15.50          |
| Rotary Encoders                    | neomacro.in         | 2     | ₹340             | \$4              |
| Encoder Knobs                      | neomacro.in         | 2     | ₹170             | \$2              |
| Custom PCB (5 pcs) – Gerber\_Y51   | JLCPCB via EasyEDA  | 5     | ₹2,550           | \$30             |
| Arduino Pro Micro (Clone)          | Amazon.in           | 1     | ₹850             | \$10             |
| Diode Kit (1N4148, 100 pcs)        | Amazon.in           | 1     | ₹85              | \$1              |
| Screws, Standoffs, Mounting HW     | Local/kit           | 1 set | ₹150             | \$1.80           |
| Shipping (PCB from JLCPCB)         | JLCPCB              | 1     | ₹425             | \$5.33           |
| **Total**                          |                     |       | **₹10,820**      | **\$124.63**     |
