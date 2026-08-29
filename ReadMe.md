# How to Modernize the Exidy Sorcerer's Linear Power Supply

This repo documents in pictures how I replaced the original Exidy Sorcerer's (version 1) linear power supply with a modern switched mode supply, all hidden within the original case.

The main problem with the original Exidy Sorcerer was with its linear power supply and heat dissipation. It ran very hot and had little or no airflow. The LM323K +5v regulator had a 5ohm (10W) bypass register across it which also ran very hot. What I did back in the day was to (1) build a custom fan unit to suck out the heat and (2) to add additional heat sinks to the +5v regulator.

<img src="https://github.com/rcl9/Imagery-of-Past-Projects/blob/main/Hardware/1980%20-%20Fan%20enclosure%20for%20very%20hot%20Exidy%20Sorcerer%20%232.jpg" alt="" style="width:30%; height:auto;">     <img src="https://github.com/rcl9/Imagery-of-Past-Projects/blob/main/Hardware/1981%20to%201982%20-%20Various%20hardware%20modifications%20for%20Exidy%20Sorcerer.webp" alt="" style="width:65%; height:auto;">

After recently recapping the tantalums in my Sorcerer I was 100% all set to replace the original filtering caps and the LM323K +5v regulator with new components. However, I then discovered that the LM323K had become obsolete 15 years ago and its price had skyrocketed to well over $120 or more. And I did not want to replace it with a tiny little switched-mode variation due to their inherent noise.

Some people will argue that a rare Exidy Sorcerer should remain in its original condition and not be modified, such as with the major changes needed for a new switched mode power supply. However, in my case I was able to (eventually) justify these modifications based on these arguments:

- By 1982 my machine (as seen in the photo above) was already a "Franken-Sorcerer" and  heavily kludged. Hence, I was doing the machine a favour to simplify its power supply system and clean it up visually + modernize the PSU.

- It will run a lot cooler and there should be ample "clean" power for the machine. But much more importantly, I'll have the peace of mind that the machine will not blow up if the linear power supply fails in the future.

- After my current rounds of machine maintenance, I'd ideally like it to operate for another 40 years.

- As a minor benefit, the machine does not weight as much with the new PSU.

For the S-100 box, I felt that its simple linear supply was okay and that the LM323K would be fine to handle the few ICs on the interface board (but I did recap it anyway).

Also, I would never have considered even starting this project without seeing Thomas Riesen's post to the "Vintage S100 Computer Enthusiasts" Facebook group on March 27 2025 which showed that it was physically possible to put a small Mean Well PSU within the machine.  I had also bumped into 1 or 2 other people who had done such a similar change-over to switched-mode. But no one had documented the process.

Up front I'll state (and warn you) that "it is a very tight fit" to get the Mean Well RQ-65 inside the machine, without it hitting the keyboard's PCB. I had about 1mm or less clearance after all was said and done, and that was after a few weeks of careful fiddling.

## Step-by-Step Guide

First, both power switches of the Exidy Sorcerer and the S-100 box had failed. It is recommended that you remove them and pry them open with a small screwdriver. The problem was that the "green gel" placed inside had gone bad and seeped out everywhere. It took  about 45mins to carefully pick out this junk from each switch. It is also a bit tricky to snap the plastic piece back into the switch with the copper rocker on the correct side - I tended to get this right 1 out of 3 attempts but it can be done.

<img src="/Images/switch2.jpg" alt="" style="width:60%; height:auto;">    <img src="/Images/switch1.jpg" alt="" style="width:35%; height:auto;">

The old power supply components need to be removed first. You can start with the power transformer and line filter:

<img src="/Images/img1.jpg" alt="" style="width:75%; height:auto;">

While you have this unit out of the computer you will need to use a hack saw to remove the vertical lip since it'll be in the way of the new PSU:

<img src="/Images/img2.jpg" alt="" style="width:75%; height:auto;">

Afterwards, use a metal file to remove excess metal and to smooth out the burrs:

<img src="/Images/img3.jpg" alt="" style="width:75%; height:auto;">

The next phase may take you some time and effort to complete. You need to unsolder and remove all of the linear power supply components as shown in the following photo. This photo also shows how the power supply wires have been mended and tinned.

<img src="/Images/img4.jpg" alt="" style="width:75%; height:auto;">

After the fact I'll also mention that the 6 pin power connector and its black plastic mount needs to be completely removed from the motherboard in order to provide the necessary tolerance clearances for the PSU. It was a real pain to remove the black mounted portion.

<img src="/Images/img5.jpg" alt="" style="width:75%; height:auto;">

With the system cleaned up from the old components, we need to move onto the tricky part of securely mounting the PSU. I spent a few weeks toiling over this phase given that there is literally no room for error as the clearance tolerances are very tight. I also did not want the PSU to sit on the motherboard nor did I wish to have to drill holes through the motherboard for the stand-offs (as I had 100% thought would have to be the case). Through "too much thinking" I came up with a robust and good solution.

Another core problem which I quickly encountered was that the Mean Well PSU wasn't meant to be secured in place horizontally as it does not have any holes in all 4 corners. Rather they wish the unit to be mounted vertically on its side. Also, purchasing the official Mean Well mounting plate did not solve this problem at all. But I did come up with an engineered solution, thanks to my Meccano set from the 1960s. Additionally, I was able to make a mounting hole on one corner via a small "Z" shaped bracket (which I'll reference in a photo later on) which allowed me to mount that corner without having to drill through the motherboard.

As shown in the following photo, the basic idea is to mount the PSU via 3 stand-offs, all of which do not intersect the motherboard. The white plastic stand-off was cut down in length to the correct offset needed. The yellow ink-pen casing was cut to size for the second stand-off. But how could I mount the unit at the other corner?!? What I saw in my mind was some kind of "slotted piece of metal which I could use to adjust the pitch of the PSU in the case". My Meccano set came to mind and indeed I found the most ideal piece which I needed (see the second photo). I bent the oval piece into a "L" shape. The slot will allow me to adjust the height of the PSU near to the keyboard later on.

<img src="/Images/img8.jpg" alt="" style="width:75%; height:auto;">

<img src="/Images/img7.jpg" alt="" style="width:75%; height:auto;">

The next major task was to figure out where and how to attach the +5v, +12v, -10v and ground wires to the motherboard. That took a while because I didn't want to mess up the power supplies at all. Determining an appropriate location for the -10v was particularly time consuming.

I cleaned out the holes in the motherboard very well then used an old IBM PC 4-wire power cable to wire the power into the motherboard. That only took 30 to 45mins at most.

<img src="/Images/img9.jpg" alt="" style="width:75%; height:auto;">

The +5v main rail is on the bottom side of the board so I chose to solder the +5v line to the beefy trace located close to the output of the LM323K regulator:

<img src="/Images/img10.jpg" alt="" style="width:75%; height:auto;">

Lastly, I connected the ground wire to the top ground plane of the motherboard:

<img src="/Images/img11.jpg" alt="" style="width:75%; height:auto;">

<img src="/Images/img12.jpg" alt="" style="width:75%; height:auto;">

New lug crimp terminals were added to the 120v and ground wires:

<img src="/Images/img13.jpg" alt="" style="width:75%; height:auto;">

Given the overall tight space tolerances that I had pre-determined, there is literally no space between the PSU and the 120v power section, especially the fuse holder. In the next photo I added electrical tape around the switch and fuse folder.

This photo also clearly shows the "Z" (or "L") bracket which I attached to the PSU on the left side which would allow me to secure it to the yellow stand-off. The bolt shown on the right side of the PSU (above the new white plastic stand-off) was "nearly impossible" to set in place but through magic it did catch the screw. Again, I'll say that Mean Well doesn't make it easy to mount these units in a horizontal plane.

<img src="/Images/img14.jpg" alt="" style="width:75%; height:auto;">

This photo shows how the 120v power and chassis ground were connected to the PSU. Due to the tight tolerances I had to bend up the crimp terminals to 30-40deg or thereabouts. Notice also the placement of the electrical tape.

<img src="/Images/img15.jpg" alt="" style="width:75%; height:auto;">

As we are getting close to completion, I had to come up with a way to insulate the metal enclosure of the PSU from the traces of the motherboard and its large ground plane. I opted to use a cut portion of a silicon-based cooking mat. This photo also shows the completed wiring to the PSU with crimp lug terminals.

<img src="/Images/img16.jpg" alt="" style="width:75%; height:auto;">

The last 3 photos show the completed PSU and its mounting within the computer. Please note that the PSU does not sit on nor touch the motherboard. I was able to use the Meccano vertical "L" bracket to adjust the height of the PSU which turned out to be super-ideal for this situation.

<img src="/Images/img17.jpg" alt="" style="width:75%; height:auto;">
<img src="/Images/img18.jpg" alt="" style="width:75%; height:auto;">
<img src="/Images/img19.jpg" alt="" style="width:75%; height:auto;">

I wanted to close out this tutorial by showing "just how tight" the tolerances are for placing this Mean Well PSU within the Sorcerer. The core problem is that the keyboard's PCB protrudes quite a bit into the interior space around the old power supply section. I had taken note of this early into my review of this spacing issue and it had worried me as to whether I could get the PSU mounted all while providing some space tolerance for the keyboard's PCB. As you see, I was fortunate to get a bit of space where needed. I could have also dropped the height of the PSU a tiny bit via the adjustment screw (shown on the "L" bracket in this photo) to get a bit more clearance, if needed.

And for those that many be wondering why there is a large round hole in the side of my Sorcerer, it is due to the square 120v cooling fan that I used to have bolted onto the side of the computer in the early 1980s. I suppose the hole now comes in handy to provide better ventilation for the Mean Well PSU.

<img src="/Images/img20 - keyboard pcb clearance.jpg" alt="" style="width:75%; height:auto;">

## Was it worth all of the work? Yes and no.

In retrospect, for others to consider before they launch into doing the same modifications:

1) First, it took a considerable amount of planning, execution and work to pull off the project. It wasn't a quick and easy retrofit.

2) However, the original goal was met, such that the Sorcerer now has a stable and not-so-hot power supply, modernized for 40 years into the future.
