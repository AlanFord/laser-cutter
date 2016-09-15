#Repairing the Z-axis Drive
The Z-axis drive system relies on a stepper motor mounted near the laser tube in the upper, left, back corner of the laser cutter.  The motor uses a short belt to drive a threaded rod.  The threaded rod is attached to the rear, left corner of the build table and drives it in the Z-axis.  The bottom of the threaded rod has a pulley that drives a long, continuous toothed belt.  The belt drives pulleys and threaded rods on the other three corners of the build table.  The belt is tensioned with an idler pulley that can be shifted front-to-back to tension the belt.

##Step 1 - Remove the aluminum hexacomb from the build table
Do this and store the hexacomb in a safe place.  Removing it will make the following steps easier.

##Step 2 - Reseat the back-right threaded rod
The threaded rod in the back-right corner has shifted up and needs to be reseated in the fixture at the bottom.  Because the build table is attached to the threaded rod, the threaded rod will only shift down a little ways.  There are two possible ways to reseat the threaded rod.  First, try twisting the threaded rod clockwise (when looking down at the rod).  This should shift that corner of the build table up, putting a little tension on the rod making it easier to shift the rod down.  Give this a couple of tries to reseat the bearing at the bottom of the threaded rod.  If that doesn't work, try the following.  Second, use a (phillips??) screwdriver to disconnect the build table from the attachment to the threaded rod.  Now the threaded rod and bearing can be reseated.  Hand twist the threaded rod a little to get the connector closer to the build table and replace the screws that attach the build table.  A mirror and a flashlight can help see the bottom of the build table and the attachment points.

##Step 3 - Tram the build table
The build table doesn't need to be level, but it needs to be square with the gantry (the long aluminum beam that moves front-to-back).  This can be accomplished by moving the gantry, slowly, to the rear of the laser cutter and marking the height of the gantry above the build table on a dowel rod or small piece of wood.  Make the measurement close to the left-rear threaded rod.  The dowel/wood with be your measuring stick to get the other three corners the same distance below the gantry. Move to the front/left corner and adjust the height of the build plat by manually twisting the threaded rod in that corner.  Use the dowel/wood to set the height to match the first corner.  Repeat for all the other corners.  Do it all over again and again until all the corners are the same distance from the gantry.  The repeats are necessary because adjusting one corner can affect the others.

##Step 4 - Install the long belt
The long belt needs to be installed around each of the pulleys at the bottom of the threaded rods.  The flat side of the belt also needs to go around the idler pulley.  Loosen the idler pulley attachment bolts to make this easier.  It still won't be easy to get the belt around the pulleys on the threaded rods.  Turn the belt so that it is flat against the bottom of the laser cutter and slide/work the belt under each pulley, being careful to ensure the belt's teeth will be facing each pulley (it's easy to get it flipped).  Once the belt is in place, work the slack toward the idler pulley, trying not to twist the threaded rods (which you aligned in the previous step) Tension the belt by shifting the idler pulley towards the center of the laser cutter and tighten the idler pulley belts.  

##Step 5 - Replace the hexacomb material
You are done!

#Repairing the Laser Carriage
The laser carriage moves right-to-left on the gantry using three "v wheels", wheels with v grooves that ride in the gantry.  The wheels need to be replaced.  However, the carriage is still attached to the laser by a belt, electrical wires, and a cable carrier so the wheels replacement will have to be done in situ.  The parts used in the laser carriage assembly are shown in the drawing <https://github.com/AlanFord/laser-cutter/blob/master/Drawings/c30001-020_rev_6.pdf>.
The fitup of the laser carriage on the gantry in shown in the drawing
<https://github.com/AlanFord/laser-cutter/blob/master/Drawings/d30043_rev_2.pdf>.

##Step 1 - Remove the front v wheels
The v wheels are held in place with bolts and nyloc nuts.  Remove and replace with new v wheels, nuts, bolts, and nylon spacers. Tighten enough to remove any vertical play in the v wheels, but don't not enough to bind the v wheels (they need to turn freely on the bearings).

##Step 2 - Remove the rear v wheel
This wheel is removed and replaced in a similar fashion, but it contains an "eccentric spacer".  Seat the carriage on the gantry and rebuild the rear v wheel assembly, replace all parts but retaining and reusing the eccentric spacer.  The eccentric spacer should turn freely but not rattle around and the carriage should now loosely fit on the gantry.

##Step 3 - Seat the laser carriage to the gantry
Rotate the eccentric spacer to seat the three v wheels onto the gantry, eliminating any excessive play but ensuring the carriage moves freely on the gantry. Now tighten the nyloc nut on the rear v wheel to secure the eccentric spacer, let the v wheel turn freely, but eliminate excess play in the v wheel.

##Step 4 - Test
Wear the safety glasses as a precaution.  You can now hook the laser up to the computer, turn the computer on, and then turn the laser on.  The motors should turn but the laser won't fire as long as the E-stop button (attached to the laser's front panel) is missing.  First try moving the laser carriage right/left (you may have to disable the soft limits to do this).  If excessive noise/vibration occurs, adjust the eccentric nut on the carriage.  Now move the build table down, then up, again listening for squeaking/grinding of threaded rods, bearings, etc.  Adjust as necessary.

#Installing the +Z Limit Switch
The +Z limit switch attaches to a little bracket that is then attached to a vertical aluminum support.  See Sheet 2, Item 9 of drawing <https://github.com/AlanFord/laser-cutter/blob/master/Drawings/d30025_rev_8.pdf >.

##Step 1 - Make up the needed wires
An easy way to make up the wires is to cut the insulation off of a length of ethernet cable.  Make sure the length will be long enough to reach from where the switch is to be mounted over to the control electronics, keeping it away from the laser, high voltage supply, etc.  Removed one twisted pair of wires from the bare ethernet cable, keeping them twisted (this helps prevent electrical noise on the wires).  Strip both ends of each wire.  One end will be soldered to the switch and the other end will be inserted into screw terminals on the control electronics board.

##Step 2 - Soldering the switch
Using a digital voltmeter, determine which two terminals (the center terminal and one of the outer terminals) on the switch are "disconnected" when the switch is pressed.  Solder the wires to these two terminals. 

##Step 3 - Mounting the switch
Use the focal length gauge (the calibrated paint stirrer) and run the build table up until the aluminum honeycomb is slightly closer to the laser than the focal length gauge would indicate is proper.  This will ensure that thin material (card stock paper) can still be cut properly but the build table can't be raised any higher.  Mount the +Z limit switch so that it would "just" open with the build table in this position.  Lower the build table until the switch resets.  Run the wires over to the control electronics, securing the wire so it's not loose.  Hook the wire up to pins 1 and 3 of the 9-DB enclosure connector (see the section "J3 Enclosure Connector in the PCB manual: <https://github.com/AlanFord/laser-cutter/blob/master/Drawings/A40003_Rev_4.pdf>.

##Step 4 - Configure Mach3
Mach3 needs to be configured so that Pin 12 is identified as the +Z limit switch.  Must be performed by someone knowledgeable with Mach3 configuration settings.  Do not enable homing on the +Z limit switch.  For more details on using Pin 12, see "J1 Control Connector" in the PCB manual: <https://github.com/AlanFord/laser-cutter/blob/master/Drawings/A40003_Rev_4.pdf>.

##Step 5 - Test
Verify that the limit switch is working but carefully raising the build plate and verifying the +Z limit switch trips before the honeycomb material runs into anything. 