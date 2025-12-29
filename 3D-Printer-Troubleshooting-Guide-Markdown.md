# 1\. Not Extruding at Start of Print

## 1\) Extruder was not primed before beginning the print

Most extruders have a bad habit of leaking plastic when they are sitting idle at a high temperature. The hot plastic inside the nozzle tends to ooze out of the tip, which creates a void inside the nozzle where the plastic has drained out. This idle oozing can occur at the beginning of a print when you are first preheating your extruder, and also at the end of the print while the extruder is slowly cooling. If your extruder has lost some plastic due to oozing, the next time you try to extrude, it is likely that it will take a few seconds before plastic starts to come out of the nozzle again. If you are trying to start a print after you nozzle has been oozing, you may notice the same delayed extrusion. To solve this issue, make sure that you prime your extruder right before beginning a print so that the nozzle is full of plastic and ready to extrude. A common way to do this in Simplify3D is by including something called a skirt. The skirt will draw a circle around your part, and in the process, it will prime the extruder with plastic. If you need extra priming, you can increase the number of skirt outlines on the Additions tab in Simplify3D. Some users may also prefer to manually extrude filament from their printer using the Jog Controls in Simplify3D’s Machine Control Panel prior to beginning the print.



## 2\) Nozzle starts too close to the bed

If the nozzle is too close to the build table surface, there will not be enough room for plastic to come out of the extruder. The hole in the top of the nozzle is essentially blocked so that no plastic can escape. An easy way to recognize this issue is if the print does not extrude plastic for the first layer or two, but begins to extrude normally around the 3rd or 4th layers as the bed continues to lower along the Z-axis. To solve this problem, you can use the very handy G-Code offsets which can be found on the G-Code tab of Simplify3D’s process settings. This allows you to make very fine adjustments to the Z-axis position without needing to change the hardware. For example, if you enter a value of 0.05mm for the Z-axis G-Code offset, this will move the nozzle 0.05mm further away from the print bed. Keep increasing this value by small increments until there is enough room between the nozzle and the build platform for the plastic to escape.



## 3\) The filament has stripped against the drive gear

Most 3D printers use a small gear to push the filament back and forth. The teeth on this gear bite into the filament and allow it to accurately control the position of the filament. However, if you notice lots of plastic shavings or it looks like there is a section missing from your filament, then it’s possible that the drive gear has removed too much plastic. Once this happens, the drive gear won’t have anything left to grab onto when it tries to move the filament back and forth. Please see the Grinding Filament section for instructions on how to fix this issue.



## 4\) The extruder is clogged

If none of the above solutions of the topic are able to resolve the issue, then it is likely that your extruder is clogged. This can happen if foreign debris is trapped inside the nozzle, when hot plastic sits inside the extruder too long, or if the thermal cooling for the extruder is not sufficient and the filament begins to soften outside of the desired melt zone. Fixing a clogged extruder may require disassembling the extruder, so please contact your printer manufacturer before you proceed. We have had great success using the “E” string on a guitar to unclog extruders by feeding it into the nozzle tip, however, your manufacturer should also be able to provide recommendations.



# 2\. Not Sticking to the Bed

## 1\) Build platform is not level

Many printers include an adjustable bed with several screws or knobs that control the position of the bed. If your printer has an adjustable bed and you’re having trouble getting your first layer to stick to the bed, the first thing you will want to verify is that your printer’s bed is flat and level. If the bed is not level, one side of your bed may be too close to the nozzle, while the other side is too far away. Achieving a perfect first layer requires a level print bed.



## 2\) Nozzle starts too far away from bed

Once your bed has been properly leveled, you still need to make sure that the nozzle is starting at the correct height relative to the build platform. Your goal is to locate your extruder the perfect distance away from the build plate — not too far and not too close. For good adhesion to the build plate, you want your filament to be slightly squished against the build plate. While you can adjust these settings by modifying the hardware, it is typically much easier (and much more precise!) to make these changes from Simplify3D. To do this, click “Edit Process Settings” to open your process settings and then go to the G-Code tab. You can use the Z-Axis global G-Code Offset to make very fine adjustments to your nozzle position. For example, if you enter -0.05mm for the Z-axis G-Code offset, the nozzle will begin printing 0.05mm closer to your build platform. Each layer of your part is usually only around 0.2mm thick, so a small adjustment goes a long way.



## 3\) First layer is printing too fast

As you extrude the first layer of plastic on top of the build platform, you want to make sure that plastic can properly bond to the surface before starting the next layer. If you print the first layer too fast, the plastic may not have time to bond to the build platform. For this reason, it is typically very useful to print the first layer at a slower speed so that the plastic has time to bond to the bed. Simplify3D provides a setting for this exact feature. If you click on “Edit Process Settings” and go to the Layer tab, you will see a setting labeled “First Layer Speed”. For example, if you set a first layer speed of 50%, it means that your first layer will print 50% slower than the rest of your part. If you feel that your printer is moving too fast on the first layer, try reducing this setting.



## 4\) Temperature or cooling settings

Plastic tends to shrink as it cools from a warm temperature to a cool temperature. To provide a useful example, imagine a 100mm wide part that is being printed with ABS plastic. If the extruder was printing this plastic at 230 degrees Celsius, but it was being deposited onto a cold build platform, it is likely that the plastic would quickly cool down after leaving the hot nozzle. Some printers also include cooling fans that speed up this cooling process when they are being used. If this ABS part cooled down to a room temperature of 30C, the 100mm wide part would shrink by almost 1.5mm! Unfortunately, the build platform on your printer is not going to shrink this much, since it is typically kept at a fairly constant temperature. Because of this fact, the plastic will tend to separate from the build platform as it cools. This is an important fact to keep in mind as you print your first layer. If you notice that the layer seems to stick initially, but later separates from the print bed as it cools, it is possible that your temperature and cooling settings are to blame.



Many printers that are intended to print high-temperature materials like ABS include a heated bed to help combat these problems. If the bed is heated to maintain a temperature of 110C for the entire print, it will keep the first layer warm so that it does not shrink. So if your printer has a heated bed, you may want to try heating the bed to prevent the first layer from cooling. As a general starting point, PLA tends to adhere well to a bed that is heated to 60-70C, while ABS generally works better if the bed is heated to 100-120C. You can adjust these settings in Simplify3D by clicking on “Edit Process Settings” and then selecting the Temperature tab. Choose your heated build platform from the list on the left-hand side and then edit the temperature setpoint for the first layer.



If your printer has a cooling fan, you may also want to try disabling that cooling fan for the first few layers of your printer so that the initial layers do not cool down too quickly. You can do this by clicking “Edit Process Settings” and going to the Cooling tab. You can adjust the fan speed setpoints on the left-hand side. For example, you may want the first layer to start with the fan disabled and then turn on the fan to full power once you reach the 5th layer. In that case, you will need to add two setpoints into that list: Layer 1 at 0% fan speed, and Layer 5 at 100% fan speed. If you are using ABS plastic, it is common to disable the cooling fan for the entire print, so entering a single setpoint would suffice (Layer 1 at 0% fan speed). If you are working in a breezy environment, you may also want to try to insulate your printer to keep the wind away from your part.



## 5\) The build platform surface (tape, glues, and materials)

Different plastics tend to adhere better to different materials. For this reason, many printers include a special build platform material that is optimized for their materials. For example, several printers use a BuildTak sheet on the top of their bed that tends to stick very well to PLA. Other manufacturers opt for a heat treated glass bed such as Borosilicate glass, which tends to work very well for ABS when heated. If you are going to print directly onto these surfaces, it is always a good idea to make sure that your build platform is free of dust, grease, or oils before starting the print. Cleaning your print bed with some water or isopropyl rubbing alcohol can make a big difference. There are several types of tape that stick well to common 3D printing materials. Strips of tape can be applied to the build platform surface and easily removed or replaced if you want to print with a different material. For example, PLA tends to stick well to blue painter’s tape while ABS tends to stick better to Kapton tape (otherwise known as Polyimide film). Many users have also had great success using a temporary glue or spray on the top of their build platforms. Hair spray, glue sticks, and other sticky substances tend to work very well if everything else has failed.



## 6\) Brims and Rafts

Sometimes you are printing a very small part that simply does not have enough surface area to stick to the build platform surface. Simplify3D includes several options that can help increase this surface area to provide a larger surface to stick to the print bed. One of these options is called a “brim.” The brim adds extra rings around the exterior of your part, similar to how a brim of a hat increases the circumference of the hat. This option can be enabled by going to the “Additions” tab end enabling the “Use Skirt/Brim” option. Simplify3D also allows users to add a raft under their part, which can also be used to provide a larger surface for bed adhesion. If you are interested in these options, please take a look at our Rafts, Skirts, and Brims tutorial which explains things in greater detail.



# 3\. Under-Extrusion

## 1\) Incorrect filament diameter

The first thing you want to verify is that the software knows the filament diameter that you are using. You can find this setting by clicking “Edit Process Settings” and going to the Other tab. Check to make sure that this value matches the filament that you purchased. You may even want to measure your filament yourself using a pair of calipers to make sure that you truly have the correct diameter specified in the software. The most common values for the filament diameter are 1.75mm and 2.85mm. Many spools of plastic also include the correct diameter on the packaging.



## 2\) Increase the extrusion multiplier

If your filament diameter is correct, but you are still seeing under-extrusion issues, then you need to adjust your extrusion multiplier. This is a very useful setting in Simplify3D that allows you to easily modify the amount of plastic that is extruded (otherwise known as the flow rate). You can find this setting by clicking “Edit Process Settings” and going to the Extruder tab. Each extruder on your printer can have a unique extrusion multiplier, so if you are trying to modify the flow rate for a specific extruder, make sure to select it from the list on the left to load the settings for that extruder. As an example, if your extrusion multiplier was 1.0 previously and you change it to 1.05, it means you will be extruding 5% more plastic than you were previously. It is typical for PLA to print with an extrusion multiplier near 0.9, while ABS tends to have extrusion multipliers closer to 1.0. Try increasing your extrusion multiplier by 5%, and then reprint the test cube to see if you still have gaps between your perimeters.



## 3)First layer calibration too close

Make sure you have performed the First Layer Calibration correctly. Avoid compensating for a lack of adhesion by squishing the first layer too much. If the nozzle is too close to the build plate, the filament can be obstructed from pushing through. We recommend running the first layer calibration every time you move the printer to a different location or do maintenance on the hotend, like changing the nozzle. Moreover, when you swap the steel sheet from the textured one to the smooth one you must recalibrate due to the sheet's different thickness.



## 4\) Slicer settings

Each profile in the PrusaSlicer contains settings that determine temperature, speeds, and how much filament the 3D printer should extrude. The printer does not provide any feedback on how much filament actually leaves the nozzle. It can be that less filament is extruded than the firmware expects. If that happens, you may notice gaps in and/or in between printed layers.



## 5\) Nozzle

If you had the nozzle removed from the hotend at some point, make sure it has been correctly reinstalled. Please see the dedicated guide for your hotend:
● Changing or replacing the nozzle (MK2.5S/MK3S/MK3S+/MK3.5)
● Changing/replacing the nozzle (MINI)
Incorrect installation can cause both clogging and leaks. The nozzle must be tightened when heated and there must be a gap between the nozzle and the heater block. Also, inspect the extruder and hotend for any damage, like the heater element or thermistor's wires or a bent heatbreak (only on V6 hotend).
If the installation of the nozzle is correct, then performing a Cold pull will often resolve a clog.



## 6\) Using specialty nozzles

If you are using specialty nozzles like hardened steel or stainless steel, etc., you may have to increase the nozzle temperature when printing, usually within a range of 5-10 °C. Steel has different thermal properties compared to a brass nozzle, which can affect print results, mainly the inter-layer adhesion. But remember that higher temperatures can also lead to increased stringing. If the issue persists, try replacing the nozzle with the original 0.4mm brass nozzle and see if it makes a difference.
Furthermore, not all nozzle sizes will be suitable for all filaments. Filament that contains particles of wood or metal will most often be unsuitable for nozzles with a diameter below 0.4, and some will require an even larger nozzle, like 0.6 mm or 0.8 mm.
A 0.1 mm nozzle can be considered experimental; Its small diameter will not work with all filaments, the tolerances required in its manufacturing are hard to guarantee and the excessive printing time it requires can be beyond reasonable. For these fine resolutions, you may want to consider SLA printing.



## 7\) Extruder gears

Check both Bondtech gears for any dirt or misalignment so they are able to push filament through. Please see Checking/re-aligning the Bondtech gear (MK3S/MK2.5S) for details.
Additionally, make sure that your printer’s extruder idler is at the correct tension. Having the idler screw too loose or too tight can cause under extrusion.



## 8\) Insufficient hotend cooling

Controlling the "melt-zone" of the filament is very important. With insufficient cooling, the filament can start melting too far away from the nozzle. Check that your extruder fan is installed in the correct orientation and whether the fan is blocked by a piece of filament or some other debris.
Unless you have turned off "Fan check", the printer will give an error if it detects if either fan is not spinning when it should (hotend fan or print fan).
If you are using your printer in an enclosure, make sure the temperature inside is not too hot, as overheating can result in Heat creep, where the filament will start melting before it reaches the nozzle The hotend fan will always spin if the nozzle is heated above 50 °C.



## 9\) Filament

Too low or too high printing temperature can cause print issues as well. If your filament brand and type is not listed in PrusaSlicer, you can try to adjust the print temperature by +/- 5-15°C to see if this resolves the issue. Some specialty materials, like Flexible materials, may require many adjustments and tweaks to print them successfully. Composite materials, like Woodfill filament, may require at minimum a 0.6 mm nozzle, and 0.2 mm layer height to prevent clogging. If there are composite materials like kevlar or carbon fiber, a hardened nozzle is required. Be sure to see our extensive material table, where most types of filament and their considerations are covered. Some filaments can also have a varying thickness, due to quality or infused materials like wood, which will cause unexpected changes in the volume of extruded filament. The industry standard of variations in diameter is +/- 0.05 mm. Keep your filament dry, free of moisture because damp filaments have a negative impact on printing, especially soluble filament, PETG, and ABS. We highly recommend putting spools back inside their original bag when it’s not in use, along with a silica gel. We recommend storing your filaments in a dry area or ideally in a “dry box”.



# 4\. Over-Extrusion

The software is constantly working together with your printer to make sure that your nozzle is extruding the correct amount of plastic. This precise extrusion is an important factor in achieving good print quality. However, most 3D printers have no way of monitoring how much plastic is actually extruded. If your extrusion settings are not configured properly, the printer may extrude more plastic than the software expects. This over-extrusion will result in excess plastic that can ruin the outer dimensions of your part. To resolve this issue, there are only a few settings you need to verify in Simplify3D. Please see the Under-extrusion section for a more detailed description. While those instructions are for under-extrusion, you will adjust the same settings for over-extrusion, just in the opposite direction. For example, if increasing the extrusion multiplier helps with under-extrusion, then you should decrease the extrusion multiplier for over-extrusion issues.



# 5\. Gaps in Top Layers

To save plastic, most 3D printed parts are created to have a solid shell that surrounds a porous, partially hollow interior. For example, the interior of the part may use a 30% infill percentage, which means that only 30% of the interior is solid plastic, while the rest is air. While the interior of the part may be partially hollow, we want the exterior to remain solid. To do this, Simplify3D allows you to specify how many solid layers you want on the top and bottom of your part. For example, if you were printing a simple cube with 5 top and bottom solid layers, the software would print 5 completely solid layers at the top and bottom of the print, but everything else in the middle would be printed as a partially hollow layer. This technique can save a tremendous amount of plastic and time, while still creating very strong parts thanks to Simplify3D’s great infill options. However, depending on what settings you are using, you may notice that the top solid layers of your print are not completely solid. You may see gaps or holes between the extrusions that make up these solid layers. If you have encountered this issue, here are several simple settings that you can adjust to fix it.



## 1\) Not enough top solid layers

The first setting to adjust is the number of top solid layers that are used. When you try to print a 100% solid layer on top of your partially hollow infill, the solid layer has to span across the hollow air pockets of your infill. When this happens, the extrusions for the solid layer have a tendency to droop or sag down into the air pocket. Because of this, you generally want to print several solid layers at the top of your print to ensure a nice flat, completely solid surface. As a good rule of thumb, you want the solid section at the top of your print to be at least 0.5mm thick. So if you are using a 0.25mm layer height, you would need at least 2 top solid layers. If you are printing at a lower layer height such as 0.1mm, you may need 5 solid layers at the top of your print to achieve the same effect. If you are noticing gaps between the extrusions in your top surface, the first thing you should try is increasing the number of top solid layers. For example, if you noticed the problem using only 3 top solid layers, try printing with 5 top solid layers to see if the problem is improved. Note that additional solid layers will occur within your part dimension and do not add size to the exterior of your part. You can adjust the solid layer settings by clicking “Edit Process Settings” and selecting the Layer tab.



## 2\) Infill percentage is too low

The infill on the inside of your part will act as the foundation for the layers above it. The solid layers at the top of your part will need to print on top of this foundation. If your infill percentage is very low, there will be large air gaps in your infill. For example, if you are using an infill percentage of only 10%, the remaining 90% of the interior of your part would be hollow, and this would create some very large air gaps that the solid layers would need to print on top of. If you have tried increasing the number of top solid layers and you are still seeings gaps in the top of your print, you may want to try increasing your infill percentage to see if the gaps go away. For example, if your infill percentage was previously 30%, try using a 50% infill percentage, as this would provide a much better foundation for the solid layers at the top of your print.



## 3\) Under-Extrusion

If you have tried increasing the infill percentage and the number of top solid layers, yet you are still seeing gaps in the tops of your print, then you likely have an under-extrusion issue. This means that your nozzle is not extruding as much plastic as the software expects. For a full description of this issue and how to correct it, please read the Under-extrusion section.



# 6\. Stringing or Oozing

Stringing (otherwise known as oozing, whiskers, or “hairy” prints) occurs when small strings of plastic are left behind on a 3D printed model. This is typically due to plastic oozing out of the nozzle while the extruder is moving to a new location.



## 1\) Retraction distance

The most important retraction setting is the retraction distance. This determines how much plastic is pulled out of the nozzle. In general, the more plastic that is retracted from the nozzle, the less likely the nozzle is to ooze while moving. Most direct-drive extruders only require a retraction distance of 0.5-2.0mm, while some Bowden extruders may require a retraction distance as high as 15mm due to the longer distance between the extruder drive gear and the heated nozzle. If you encounter stringing with your prints, try increasing the retraction distance by 1mm and test again to see if the performance improves.



## 2\) Retraction speed

The next retraction setting that you should check is the retraction speed. This determines how fast the filament is retracted from the nozzle. If you retract too slowly, the plastic will slowly ooze down through the nozzle and may start leaking before the extruder is done moving to its new destination. If you retract too quickly, the filament may separate from the hot plastic inside the nozzle, or the quick movement of the drive gear may even grind away pieces of your filament. There is usually a sweet spot somewhere between 1200-6000 mm/min (20-100 mm/s) where retraction performs best. Thankfully, Simplify3D has already provided many pre-configured profiles that can give you a starting point for what retraction speed works best, but the ideal value can vary depending on the material that you are using, so you may want to experiment to see if different speeds decrease the amount of stringing that you see.



## 3\) Temperature is too high

Once you have checked your retraction settings, the next most common cause for excessive stringing is the extruder temperature. If the temperature is too high, the plastic inside the nozzle will become less viscous and will leak out of the nozzle much more easily. However, if the temperature is too low, the plastic will still be somewhat solid and will have difficulty extruding from the nozzle. If you feel you have the correct retraction settings, but you are still encountering these issues, try decreasing your extruder temperature by 5-10 degrees. This can have a significant impact on the final print quality. You can adjust these settings by clicking “Edit Process Settings” and selecting the Temperature tab. Select your extruder from the list on the left, and then double-click on the temperature setpoint you wish to edit.



## 4\) Long movements over open spaces

Stringing occurs when the extruder is moving between two different locations, and during that move, plastic starts to ooze out of the nozzle. The length of this movement can have a large impact on how much oozing takes place. Short moves may be quick enough that the plastic does not have time to ooze out of the nozzle. However, long movements are much more likely to create strings. Thankfully, Simplify3D includes an extremely useful feature that can help minimize the length of these movements. The software is smart enough that it can automatically adjust the travel path to make sure that nozzle has a very short distance to travel over an open space. In fact, in many cases, the software may be able to find a travel path that avoids crossing an open space all together! This means that there is no possibility to create a string, because the nozzle will always be on top of the solid plastic and will never travel outside the part. To use this feature, click on the Advanced tab and enable the “Avoid crossing outline for travel movement” option.



## 5\) Movement Speed

Finally, you may also find that increasing the movement speed of your machine can also reduce the amount of time that the extruder can ooze when moving between parts. You can verify what movement speeds your machine is using by clicking on the Speeds tab of your process settings. The X/Y Axis Movement Speed represents the side-to-side travel speed, and is frequently directly related to the amount of time your extruder spends moving over open air. If your machine can handle moving at higher speeds, you may find that increasing this settings can also reduce stringing between parts.



## Solution #2

Stringing or oozing, also known as "hairy prints", is the name given for when small strings of filament are left on a printed model. This usually happens when the filament keeps flowing from the nozzle while the extruder is moving to another object. You can see this as a marginal line of filament left between the objects. This issue is caused by very high printing temperatures and/or using incorrect retraction settings.



## 1\) Stringing from material left on the nozzle

If you print for a long time from a single type of filament, such as PET-G, the filament can create a thin layer in the nozzle. This can cause stringing as the strands of the filament stick to the surface of the print. Therefore, thoroughly clean the nozzle before printing and make sure that any dirt or remnants of previous filaments are removed from the nozzle.



## 2\) The retraction settings

● Retraction length: Amount that the filament is pulled back when a retraction is triggered. On the MK2.5/S and MK3/S/+, the retraction length should be a maximum of 2 mm.

● Lift z: lifts the extruder during movement. Having this setting lower will improve stringing. Note that disabling this feature may cause the nozzle to hit the printed part.

● Retraction Speed: Extruder motor speed on retraction. A higher value improves stringing, but if it is too high it may skip steps in the motor.

● Minimum travel after retraction: Amount of move that will trigger a retraction (mm). The preset number in PrusaSlicer is 1 mm, which is a low amount. Having this number higher will get lower printing times, but increase oozing and stringing.

● Retract on layer change: Activates retraction when the layer changes to the next one. It is recommended to leave this option on.

● Wipe while retracting: Moves the nozzle (wipe) while the retraction is happening. It is recommended to leave this option on.

● Retract amount before wiping: This option does a quick retract before doing the wiping movement. More suitable for the Original Prusa MINI/MINI+.



## 3\) Other settings that affect retraction:

● Only retract when crossing perimeters: (Print settings -> Infill -> Advanced): Disables retraction when the travel path does not exceed the upper layer's perimeter. Any oozing that happens will be within the walls and should be invisible.

● Avoid crossing perimeters: (Print settings -> Layers and perimeters -> Quality): Optimize travel moves in order to minimize the crossing of perimeters. This will lower the stringing amount, especially in the MINI/MINI+.

● Sequential printing: (Print settings -> Output options -> Sequential printing): Printing each object individually has a smaller chance of causing stringing between the parts. When using this feature, PrusaSlicer will warn you of any possibility of the extruder colliding with an already printed part, but follow the print closely.

● Nozzle temperature: (Filament settings -> Filament -> Nozzle): Lowering the temperature decreases the occurrence of strings. Try decreasing the nozzle temperature by 5 – 10°C and check whether there’s less stringing.



## 4\) Filament

Try using a different spool than the one that is causing the stringing. The filament might have gathered moisture, which will cause a lot of stringing.



## 5\) Hotend

Stringing in the nozzle might be caused by a heat dissipation issue in the nozzle. Try re-applying thermal paste on the threads between the heatbreak and the heatsink.
If you have recently changed any component in the hotend, it is also possible that some individual parts are not in place. Go over the assembly of the hotend and check for any parts that may be different from the instructions.



## 6\) Enough settings, pass me my heat-gun.

If you don’t feel like tweaking any of the settings, well, then there is an alternative. You can get rid of the strings with a heat gun (or often with a lighter – but be very careful). Set your heat-gun to around 200 °C and aim at the strings for one or two seconds. This will melt the strings, and the printed object should remain undamaged. Do not leave the heat source on the printed model for longer than one or two seconds, as this may deform the part.



# 7\. Overheating

The plastic that exits your extruder may be anywhere from 190 to 310 degrees Celsius. While the plastic is still hot, it is pliable and can easily be formed into different shapes. However, as it cools, it quickly becomes solid and retains its shape. You need to achieve the correct balance between temperature and cooling so that your plastic can flow freely through the nozzle, but it can quickly solidify to maintain the exact dimensions of your 3D printed part. If this balance is not achieved, you may start to notice some print quality issues where the exterior of your part is not as precise and defined as you would like.



## 1\) Insufficient Cooling

The most common cause for overheating is that the plastic is not being cooled fast enough. When this happens, the hot plastic is free to change shapes as it slowly cools. For many plastics, it is much better to quickly cool the layers to prevent them from changing shape after being printed. If your printer includes a cooling fan, try increasing the power of the fan to cool the plastic faster. You can do this by clicking “Edit Process Settings” and selecting the Cooling tab. Simply double-click on the fan speed setpoint you wish to edit. This additional cooling will help the plastic retain its shape. If your printer does not include an integrated cooling fan, you may want to try installing an aftermarket fan or using a small handheld fan to cool down the layers faster.



## 2\) Printing at too high of a temperature

If you are already using a cooling fan and you are still seeing this issue, you may want to try printing at a lower temperature. If the plastic is extruded at a lower temperature it will be able to solidify faster and retain its shape. Try lowering the print temperature by 5-10 degrees to see if it helps. You can do this by clicking “Edit Process Settings” and selecting the Temperature tab. Simply double-click the temperature setpoint you wish to change. Be careful not to lower the temperature too far, as otherwise the plastic may not be hot enough to extrude through the small opening in your nozzle.



## 3\) Printing too fast

If you are printing each layer very quickly, you might not allow enough time for the previous layer to properly cool before you are trying to deposit the next layer of hot plastic on top of it. This is particularly important for very small parts where each layer only requires a few seconds to print. Even with a cooling fan, you may still need to decrease the printing speed for these small layers to ensure you provide enough time for the layer to solidify. Thankfully, Simplify3D includes a very simple option to do exactly that. If you click on “Edit Process Settings” and select the Speeds tab, you will see a section labeled “Speed Overrides.” This section is used to automatically slow down the printing speed for small layers to ensure they have enough time to cool and solidify before printing the next layer. For example, if you allow the software to adjust the printing speed for layers that take less than 15 seconds to print, the program will automatically slow down the printing speed for these small layers.



## 4\) Try printing multiple parts at once

Create a copy of the part you are trying to print (Edit > Copy/Paste) or import a second object that can be printed at the same time. By printing two objects at once, you can provide more cooling time for each individual part. The hot nozzle will need to move to a different location on the build platform to print the second part, which provides a short relief for your first part to cool down. This is a simple, yet very effective strategy for fixing overheating problems.



# 8\. Layer Shifting

Most 3D printers use an open-loop control system, which is a fancy way to say that they have no feedback about the actual location of the toolhead. The printer simply attempts to move the toolhead to a specific location, and hopes that it gets there. In most cases, this works fine because the stepper motors that drive the printer are quite powerful, and there are no significant loads to prevent the toolhead from moving. However, if something does go wrong, the printer would have no way to detect this. For example, if you happened to bump into your printer while it was printing, you might cause the toolhead to move to a new position. The machine has no feedback to detect this, so it would just keep printing as if nothing had happened.



## 1\) Toolhead is moving too fast

If you are printing at a very high speed, the motors for your 3D printer may struggle to keep up. If you attempt to move the printer faster than the motors can handle, you will typically hear a clicking sound as the motor fails to achieve the desired position. If this happens, the remainder of the print will be misaligned with everything that was printed before it. If you feel that your printer may be moving too fast, try to reduce the printing speed by 50% to see if it helps. To do this, click “Edit Process Settings” and select the Speeds tab. Adjust both the “Default Printing Speed” and the “X/Y Axis Movement Speed.” The default printing speed controls the speed of any movements where the extruder is actively extruding plastic. The X/Y axis movement speed controls the speed of rapid movements where no plastic is being extruded. If either of those speeds are too high, it can cause shifting to occur. If you are comfortable adjusting more advanced settings, you may also want to consider lowering the acceleration settings in your printer’s firmware to provide a more gradual speed up and slow down.



## 2\) Mechanical or Electrical Issues

If the layer misalignment continues, even after reducing your print speed, then it is likely due to mechanical or electrical issues with the printer. For example, most 3D printers use belts that allow the motors to control the position of the toolhead. The belts are typically made of a rubber material and reinforced with some type of fiber to provide additional strength. Over time, these belts may stretch, which can impact the belt tension that is used to position the toolhead. If the tension becomes too loose, the belt may slip on top of the drive pulley, which means the pulley is rotating, but the belt is not moving. If the belt was originally installed too tight, this can also cause issues. An overtightened belt can create excess friction in the bearings that will prevent the motors from spinning. Ideal assembly requires a belt that is somewhat tight to prevent slipping, but not too tight to where the system is unable to rotate. If you start noticing issues with misaligned layers, you should verify that your belts all have the appropriate tension, and none appear to be too loose or too tight. If you think there may be a problem, please consult the printer manufacturer for instructions on how to adjust the belt tension. Many 3D printers also include a series of belts that are driven by pulleys attached to a stepper motor shaft using a small set-screw (otherwise known as a grub screw). These set-screws anchor the pulley to the shaft of the motor so that the two items spin together. However, if the set-screw loosens, the pulley will no longer rotate together with the motor shaft. This means that the motor may be spinning, but the pulley and belts are not moving. When this happens, the toolhead does not get to the desired location, which can impact the alignment of all future layers of the print. So if layer misalignment is a reoccurring problem, you should verify that all of the motor fasteners are properly tightened. There are also several other common electrical issues that can cause the motors to lose their position. For example, if there is not enough electrical current getting to the motors, they won’t have enough power to spin. It is also possible that the motor driver electronics could overheat, which causes the motors to stop spinning temporarily until the electronics cool down.



# 9\. Layer Separation and Splitting

3D printing works by building the object one layer at a time. Each successive layer is printed on top of the previous layer, and in the end this creates the desired 3D shape. However, for the final part to be strong and reliable, you need to make sure that each layer adequately bonds to the layer below it. If the layers do not bond together well enough, the final part may split or separate.



## 1\) Layer height is too large

Most 3D printing nozzles have a diameter between 0.3-0.5mm. The plastic squeezes through this tiny opening to create a very thin extrusion that can produce extremely detailed parts. However, these small nozzles also create some limitations for what layer heights can be used. When you print one layer of plastic on top of another, you want to make sure that the new layer is being pressed against the layer below it so that the two layers will bond together. As a general rule of thumb, you want to make sure that the layer height you select is 20% smaller than your nozzle diameter. For example, if you have a 0.4mm nozzle, you can’t go too far past a layer height of 0.32mm, or each layer of plastic will not be able to properly bond to the layer beneath it. So if you notice that your prints are separating and the layers are not sticking together, the first thing you should check is your layer height compared to the size of your nozzle. Try reducing the layer height to see if it helps the layers bond together better. You can do this by clicking “Edit Process Settings” and selecting the Layer tab.



## 2\) Print temperature is too low

Warm plastic will always bond together much better than cold plastic. If you notice that your layers aren’t bonding together and you are certain that your layer height isn’t too large, then it is possible that your filament needs to be printed at a higher temperature to create a strong bond. For example, if you tried to print ABS plastic at 190C, you would likely find that the layers of your part will easily break apart. This is because ABS typically needs to be printed around 220-235C to create a strong bond between the layers of your print. So if you feel this may be the problem, verify that you are using the correct temperature for the filament you have purchased. Try increasing the temperature by 10 degrees to see if the adhesion improves. You can do this by clicking “Edit Process Settings” and selecting the Temperature tab. Simply double-click the temperature setpoint you wish to change.



## Solution #2

This refers to the de-lamination of the printed layers. It is mostly caused by an incorrect preset/(custom)profile with wrong temperatures and/or too much cooling from either the print fan or the sorrounding environment. Layer-separation is more an issue from the "old days" of unheated print-beds and less accessible materials, past ABS. This is rarely an issue on the MK-series hardware with PrusaSlicer presets, especially with materials like PLA and PETG. It’s not difficult to tell the difference between cracking and missing layers. Best way to identify cracked layers are the clean cuts that show a bit of an upward bend or warp. Layer separation occurs when the object cracks due to forces exerted on the print when layers cool down at different rates. Warping forces exceed the layer adhesion strength and the layers separate.



## 1\) How to prevent Layer separation and Splitting

ABS is highly susceptible to layer separation when there’s any sort of cold air blowing on the print before it has cooled down fully. We suggest turning fans OFF for ABS prints completely. ABS is best printed in an enclosed chamber (even heated). Here we made one from an Ikea Lack table. Please remember that you may probably not be able to print objects covering the whole print area using ABS, so it is better to replace ABS with PETG filament. PETG has similar advantages ABS, but it’s much better for printing large objects and it does not have the same tendency to crack/de-laminate. ASA is also a great alternative but is still more dependent on a stable environment when printing than PETG. PLA may suffer from cracking and layer separation problems if you’re printing with insufficient temperature. Depending on the brand, PLA is printed at a range between 195-220. If you are having issues, try increasing the printing temperature in 5°C increments, until you get a good layer adhesion.



## 2\) Flow-rate / extrusion multiplier

Increase your printer’s flow rate (in PrusaSlicer called extrusion multiplier). More material extruded will create a stronger bond between layers. increase on 5% increments. Extrusion-multiplier is located where you set temperatures, but only accessible when PrusaSlicer is set to Advanced- or Expert-mode.



# 10\. Grinding Filament

Most 3D printers use a small drive gear that grabs the filament and sandwiches it against another bearing. The drive gear has sharp teeth that allow it to bite into the filament and push it forward or backward, depending on which direction the drive gear spins. If the filament is unable to move, yet the drive gear keeps spinning, it can grind away enough plastic from the filament so that there is nothing left for the gear teeth to grab on to. Many people refer to this situation as the filament being “stripped,” because too much plastic has been stripped away for the extruder to function correctly. If this is happening on your printer, you will typically see lots of small plastic shavings from the plastic that has been ground away. You may also notice that the extruder motor is spinning, but the filament is not being pulled into the extruder body.



## 1\) Aggressive Retraction Settings

One of the first things you will want to check are the retraction settings for your extruder. If the retraction speed is too fast, or you are trying to retract far too much filament, it may put excessive stress on your extruder and the filament will struggle to keep up. As an easy test, you can try reducing your retraction speed by 50% to see if the problem goes away. If so, you know that your retraction settings may be part of the problem.



## 2\) Increase the extruder temperature

If you continue to encounter filament grinding, try to increase the extruder temperature by 5-10 degrees so that the plastic flows easier. You can do this by clicking “Edit Process Settings” and selecting the Temperature tab. Select your extruder from the list on the left and then double-click on the temperature setpoint you wish to change. Plastic will always flow easier at a higher temperature, so this can be a very helpful setting to adjust.



## 3\) Printing too fast

If you continue to encounter filament grinding, even after increasing the temperature, then the next thing you should do is decrease the printing speed. By doing this, the extruder motor will not need to spin as fast, since the filament is extruded over a longer period of time. The slower rotation of the extruder motor can help avoid grinding issues. You can adjust this setting by clicking “Edit Process Settings” and selecting the Speeds tab. Adjust the “Default Printing Speed,” which controls the speed of any movements where the extruder is actively extruding plastic.



## 4\) Check for a nozzle clog

If you are still encountering filament grinding after increasing the temperature and slowing down the print speed, then it’s likely your nozzle is partially clogged. Please read the Clogged Extruder section for instructions on how to troubleshoot this issue.



# 11\. Clogged Extruder

Your 3D printer must melt and extrude many kilograms of plastic over its lifetime. To make things more complicated, all of this plastic must exit the extruder through a tiny hole that is only as big as a single grain of sand. Inevitably, there may come a time where something goes wrong with this process and the extruder is no longer able to push plastic through the nozzle. These jams or clogs are usually due to something inside the nozzle that is blocking the plastic from freely extruding.



## 1\) Manually push the filament into the extruder

One of the first things you may want to try is manually pushing the filament into the extruder. Open Simplify3D’s Machine Control Panel and heat your extruder to the appropriate temperature for your plastic. Next, use the Jog Controls tab to extruder a small amount of plastic, for example, 10mm. As the extruder motor is spinning, lightly use your hands to help push the filament into the extruder. In many cases, this added force will be enough to advance the filament past the problem area.



## 2\) Reload the filament

If the filament still isn’t moving, the next thing you should do is unload the filament. Verify that the extruder is heated to the appropriate temperature, and then use Simplify3D’s machine control panel to retract the filament out of the extruder. As before, you may need to apply some additional force if the filament isn’t moving. Once the filament is removed, use a pair of scissors to cut away the melted or damaged portion of the filament. Then reload the filament and see if you are able to extrude with the new, undamaged section of filament.



## 3\) Clean out the nozzle

If you weren’t able to extrude the new section of plastic through the nozzle, then it’s likely you will need to clean out the nozzle before proceeding. Many users have had success heating their extruder to 100C and then manually pulling the filament out. Others prefer to use the E string from a guitar to push the material backwards through the nozzle tip. There are plenty of other methods and each extruder is different, so please consult your printer manufacturer for precise instructions.



# 12\. Stops Extruding Mid Print



## 1\) Out of filament

This one is pretty obvious, but before checking the other issues, first verify that you still have filament leading into the nozzle. If the spool has run out, you will need to load a new spool before continuing the print.



## 2\) The filament has stripped against the drive gear

During a print, the extruder motor is constantly spinning trying to push the filament into the nozzle so that your printer can keep extruding plastic. If you try to print too quickly or you try to extrude too much plastic, this motor may end up grinding away the filament until there is nothing left for the drive gear to grab onto. If your extruder motor is spinning, but the filament is not moving, then this is likely the cause. Please see the Grinding Filament section for more details on how to resolve the issue.



## 3\) The extruder is clogged

If none of the above causes apply to you, then it is very likely that the extruder is clogged. If this happens in the middle of the print, you may want to check and make sure that the filament is clean and that there is no dust on the spool. If enough dust is attached to the filament, it can cause a clog as it builds up inside the nozzle. There are several other possible causes for a clogged extruder, so please see the clogged extruder description in the Not Extruding at Start of Print section for more details.



## 4\) Overheated extruder motor driver

The extruder motor has to work incredibly hard during your print. It is constantly spinning back and forth, pushing and pulling plastic back and forth. This quick motion requires quite a bit of current, and if the printer’s electronics do not have sufficient cooling, it can cause the motor driver electronics to overheat. These motor drivers typically have a thermal cutoff that will cause the driver to stop working if the temperature gets too high. If this happens, the X and Y axis motors will be spinning and moving the extruder toolhead, but the extruder motor will not be moving at all. The only way to resolve this issue is to turn off the printer and allow the electronics to cool down. You may also want to add an extra cooling fan if the problem continues.



# 13\. Weak Infill

The infill inside your 3D printed part plays a very important role in the overall strength of your model. The infill is responsible for connecting the outer shells of your 3D print, and must also support the upper surfaces that will be printed on top of the infill.



## 1\) Try alternate infill patterns

One of the first settings you should investigate is the infill pattern that is used for your print. You can find this setting by clicking “Edit Process Settings” and going to the Infill tab. The “Internal Fill Pattern” determines what pattern is used for the interior of your part. Some patterns tend to be more solid than others. For example, Grid, Triangular, and Solid Honeycomb are all strong infill patterns. Other patterns like Rectilinear and Fast Honeycomb may sacrifice some strength for faster printing speeds. If you are having trouble producing strong reliable infill, try a different pattern to see if it makes a difference.



## 2\) Lower the print speed

The infill is typically printed faster than any other portion of your 3D print. If you try to print the infill too fast, the extruder won’t be able to keep up and you will start to notice under-extrusion on the inside of your part. This under-extrusion will tend to create weak, stringy infill since the nozzle is not able to extrude as much plastic as the software would like. If you have tried several infill patterns, but continue to have problems with weak infill, try reducing the print speed. To do this, click “Edit Process Settings” and select the Speeds tab. Adjust the “Default Printing Speed”, which directly controls the speed that is used for the infill. For example, if you were previously printing at 3600 mm/min (60 mm/s), try decreasing that value by 50% to see if the infill starts to become stronger and more solid.



## 3\) Increase the infill extrusion width

Another very powerful feature within Simplify3D is the ability to modify the extrusion width that is used for the infill of your part. For example, you could print the outline perimeters with a very fine 0.4mm extrusion width, but transition to a 0.8mm extrusion width for the infill. This will create thicker, stronger infill walls that greatly improve the strength of your 3D printed part. To adjust this setting, click “Edit Process Settings” and select the Infill tab. The “Infill Extrusion Width” is set as a percentage of the normal extrusion width. For example, if you enter a value of 200%, the infill extrusions will be twice as thick as the outline perimeters. One thing to keep in mind when adjusting this setting is that the software must also maintain the infill percentage that you specify. So if you set the infill extrusion width to 200%, the infill will use twice as much plastic for each line. To maintain the same infill percentage, the infill lines must be spaced further apart.



# 14\. Blobs and Zits

During your 3D print, the extruder must constantly stop and start extruding as it moves to different portions of the build platform. Most extruders are very good at producing a uniform extrusion while they are running, however, each time the extruder is turned off and on again, it can create extra variation. For example, if you look at the outer shell of your 3D print, you may notice a small mark on the surface that represents the location where the extruder started printing that section of plastic. The extruder had to start printing the outer shell of your 3D model at that specific location, and then it eventually returned to that location when the entire shell had been printed. These marks are commonly referred to as blobs or zits.



## 1\) Retraction and coasting settings

If you start to notice small defects on the surface of your print, the best way to diagnose what is causing them is to watch closely as each perimeter of your part is printed. Does the defect appear the moment the extruder starts printing the perimeter? Or does it only appear later when the perimeter is completed and the extruder is coming to a stop? If the defect appears right away at the beginning of the loop, then it’s possible your retraction settings need to be adjusted slightly. Click on “Edit Process Settings” and go to the Extruders tab. Right below the retraction distance, there is a setting labeled “Extra Restart Distance.” This option determines the difference between the retraction distance when the extruder is stopping and the priming distance that is used when the extruder is restarting. If you notice a surface defect right at the beginning of the perimeter, then your extruder is likely priming too much plastic. You can reduce the priming distance by entering a negative value for the extra restart distance. For example, if your retraction distance is 1.0mm, and the extra restart distance is -0.2mm (note the negative sign), then each time your extruder stops, it will retract 1.0mm of plastic. However, each time the extruder has to start extruding again, it will only push 0.8mm of plastic back into the nozzle. Adjust this setting until the defect no longer appears when the extruder initially begins printing the perimeter. If the defect does not occur until the end of the perimeter when the extruder is coming to a stop, then there is a different setting to adjust. This setting is called coasting. You can find it right below the retraction settings on the Extruder tab. Coasting will turn off your extruder a short distance before the end of the perimeter to relieve the pressure that is built up within the nozzle. Enable this option and increase the value until you no longer notice a defect appearing at the end of each perimeter when the extruder is coming to a stop. Typically, a coasting distance between 0.2-0.5mm is enough to have a noticeable impact.



## 2\) Avoid unnecessary retractions

The retraction and coasting settings mentioned above can help avoid defects each time the nozzle retracts, however, in some cases, it is better to simply avoid the retractions all together. This way the extruder never has to reverse direction and can continue a nice uniform extrusion. This is particularly important for machines that use a Bowden extruder, as the long distance between the extruder motor and the nozzle makes retractions more troublesome. To adjust the settings that control when a retraction takes place, go to the Advanced tab and look for the “Ooze Control Behavior” section. This section contains many useful settings that can modify the behavior of your 3D printer. As was mentioned in the Stringing or Oozing section, retractions are primarily used to prevent the nozzle from oozing as it moves between different parts of your print. However, if the nozzle is not going to cross an open space, the oozing that occurs will be on the inside of the model and won’t be visible from the outside. For this reason, many printers will have the “Only retract when crossing open spaces” option enabled to avoid unnecessary retractions. Another related setting can be found in the “Movement Behavior” section. If your printer is only going to retract when crossing open spaces, then it would be beneficial to avoid these open spaces as much as possible. Simplify3D includes an extremely useful feature that can divert the travel path of the extruder to avoid crossing an outline perimeter. If the extruder can avoid crossing the outline by changing the travel path, then a retraction won’t be needed. To use this feature, simply enable the “Avoid crossing outline for travel movement” option.



## 3\) Non-stationary retractions

Another extremely useful feature in Simplify3D is the ability to perform non-stationary retractions. This is particularly useful for bowden extruders that build up a lot of pressure inside the nozzle while printing. Typically when these types of machines stop extruding, the excess pressure is still likely to create a blob if the extruder is standing still. So Simplify3D has added a unique option that allows you to keep the nozzle moving while it performs its retraction. This means you are less likely to see a stationary blob since the extruder is constant moving during this process. To enable this option, we have to adjust a few settings. First, click “Edit Process Settings” and go to the Extruder tab. Make sure that the “Wipe Nozzle” option is enabled. This will tell the printer to wipe the nozzle at the end of each section when it stops printing. For the “Wipe Distance”, enter a value of 5mm as a good starting point. Next, go to the Advanced tab and enable the option labeled “Perform retraction during wipe movement”. This will prevent a stationary retraction, since the printer has now been instructed to wipe the nozzle while it retracts. This is a very powerful feature and a great option to try if you are still having trouble removing these defects from the surface of your print.



## 4\) Choose the location of your start points

If you are still seeing some small defects on the surface of your print, Simplify3D also provides an option that can control the location of these points. Click on “Edit Process Settings” and select the Layer tab. In most cases, the locations of these start points are chosen to optimize the printing speed. However, you also have the ability to randomize the placement of the start points or align them to a specific location. For example, if you were printing a statue, you could align all of the start points to be on the backside of the model so that they were not visible from the front. To do this, enable the “Choose start point that is closest to specific location” option and then enter the XY coordinate where you want the start points to be placed.



# 15\. Gaps Between Infill and Outline

Each layer of your 3D printed part is created using a combination of outline perimeters and infill. The perimeters trace the outline of your part creating a strong and accurate exterior. The infill is printed inside of these perimeters to make up the remainder of the layer. The infill typically uses a fast back-and-forth pattern to allow for quick printing speeds. Because the infill uses a different pattern than the outline of your part, it is important that these two sections merge together to form a solid bond.



## 1\) Not enough outline overlap

Simplify3D includes a setting that allows you to adjust the strength of the bond between the perimeter outlines and the infill. This setting is called the “Outline overlap” and determines how much of the infill will overlap with the outline to join the two sections together. This setting can be found by going to “Edit Process Settings” and selecting the Infill tab. The setting is based on a percentage of your extrusion width, so that it easily scales and adjusts for different nozzle sizes. For example, if you are using a 20% outline overlap, it means that the software will instruct the printer so that the infill overlaps with 20% of the inner-most perimeter. This overlap helps to ensure a strong bond between the two sections. As an example, if you were previously using an outline overlap of 20%, try increasing that value to 30% to see if the gaps between your perimeters and infill disappear.



## 2\) Printing too fast

The infill for your part is generally printed much faster than the outlines. However, if the infill is printed too fast, it will not have enough time to bond to the outline perimeters. If you have tried increasing the outline overlap, but you are still seeing gaps between your perimeters and infill, then you should try decreasing the print speed. To do this, click “Edit Process Settings” and select the Speeds tab. Adjust the “Default Printing Speed”, which controls the speed of any movements where the extruder is actively extruding plastic. For example, if you were previously printing at 3600 mm/min (60 mm/s), try decreasing that value by 50% to see if the gaps between your perimeters and infill disappear. If the gaps are no longer present at the lower speed, gradually increase the default printing speed until you find the best speed for your printer.



# 16\. Curling or Rough Corners

If you are seeing curling issues later on in your print, it typically points to overheating issues. The plastic is extruded at a very hot temperature, and if it does not cool quickly, it may change shape over time. Curling can be prevented by rapidly cooling each layer so that it does not have time to deform before it has solidified. Please read the Overheating section for a more detailed description of this issue and how to resolve it. If you are noticing the curling at the very beginning of your print, please see the Print Not Sticking to the Bed section to address first layer issues.



# 17\. Scars on Top Surface

One of the benefits of 3D printing is that each part is constructed one layer at a time. This means that for each individual layer, the nozzle can freely move to any portion of your print bed, since the part is still being constructed down below. While this provides for very fast printing times, you may notice that the nozzle leaves a mark when it travels on top of a previously printed layer. This is typically most visible on the top solid layers of your part. These scars and marks occur when the nozzle tries to move to a new location, but ends up dragging across previously printed plastic.



## 1\) Extruding too much plastic

One of the first things you should verify is that you are not extruding too much plastic. If you extrude too much plastic, each layer will tend to be slightly thicker than intended. This means that when the nozzle tries to move across each layer, it may drag through some of the excess plastic. Before you look at any other settings, you should make sure that you are not extruding too much plastic.



## 2\) Vertical lift (Z-hop)

If you know you are extruding the correct amount of plastic, but are still having trouble with the nozzle dragging across your top surface, then it might be worth looking at the vertical lift settings in Simplify3D. Enabling this option will cause the nozzle to lift up a set distance above the previously printed layer before moving to a new location. When it arrives at its final location, the nozzle will lower back down to prepare for printing. By moving at an elevated height, this can avoid the nozzle scratch on the top surface of your print. To enable this option, click “Edit Process Settings” and select the Extruder tab. Make sure that retraction is enabled, and then set the “Retraction Vertical Lift” to the distance that you would like the nozzle to raise. For example, if you enter 0.5mm, the nozzle will always raise up 0.5mm before moving to a new location. Please note that this vertical lift will only occur when the nozzle is performing a retraction. If you want to ensure that a retraction is taking place for every single move that the printer does, click on the Advanced tab and make sure that “Only retract when crossing open spaces” and “Minimum travel for retraction” are disabled.



# 18\. Gaps in Floor Corners

When building a 3D printed part, each layer relies on the foundation from the layer below. However, the amount of plastic that is used for the print is also a concern, so a balance must be achieved between the strength of the foundation and the amount of plastic that is used. If the foundation is not strong enough, you will start to see holes and gaps between the layers. This is typically most obvious in the corners, where the size of the part is changing (for example, if you were printing a 20mm cube on top of a 40mm cube). When you transition to the smaller size, you need to make sure that you have a sufficient foundation to support the sidewalls of the 20mm cube.



## 1\) Not enough perimeters

Adding more outline perimeters to your part will greatly improve the strength of the foundation. Because the interior of your part is typically partially hollow, the thickness of the perimeter walls has a significant effect. To adjust this setting, click “Edit Process Settings” and click on the Layer tab. For example, if you were previously printing with two perimeters, try the same print with four perimeters to see if the gaps disappear.



## 2\) Not enough top solid layers

Another common cause for a weak foundation is not having enough solid layers for the top surfaces of your print. A thin ceiling will not be able to adequately support the structures that are printed on top of them. This setting can be adjusted by clicking “Edit Process Settings” and selecting the Layer tab. If you were previously using only two top solid layers, try the same print with four top solid layers to see if the foundation is improved.



## 3\) Infill percentage is too low

The final setting you should check is the infill percentage used for your print, illustrated by a slider under the Process Settings or found under the Infill tab. The top solid layers will be built on top of the infill, so it is important that there is enough infill to support these layers. For example, if you were previously using a infill percentage of 20%, try increasing that value to 40% to see if the print quality improves.



# 19\. Lines on the Side of Print

The sides of your 3D printed part are composed of hundreds of individual layers. If things are working properly, these layers will appear to be a single, smooth surface. However, if something goes wrong with just one of these layers, it is usually clearly visible from the outside of the print. These improper layers may appear to look like lines or ridges on the sides of your part. Many times the defects will appear to be cyclical, meaning that the lines appear in a repeating pattern (i.e. once every 15 layers).



## 1\) Inconsistent extrusion

The most common cause for this issue is poor filament quality. If the filament does not have very tight tolerances, then you will notice this variation on the side walls of your print. For example, if your filament diameter varied by just 5% over the length of the spool, the width of the plastic extruded from the nozzle could change by as much as 0.05mm. This extra extrusion will create a layer that is wider than all the others, which will end up looking like a line on the side of the print. To create a perfectly smooth side wall, your printer needs to be able to produce a very consistent extrusion which requires high-quality plastic.



## 2\) Temperature variation

Most 3D printers use a PID controller to regulate the temperature of the extruder. If this PID controller is not tuned properly, the temperature of the extruder may fluctuate over time. Due to the nature of how PID controllers work, this fluctuation is frequently cyclical, meaning that the temperature will vary with a sine wave pattern. As the temperature gets hotter, the plastic may flow differently than when it is cooler. This will cause the layers of the print to extrude differently, creating visible ridges on the sides of your print. A properly tuned printer should be able to maintain the extruder temperature within +/-2 degrees. During your print, you can use Simplify3D’s machine control panel to monitor the temperature of your extruder. If it is varying by more than 2 degrees, you may need to recalibrate your PID controller. Please consult your printer manufacturer for exact instructions on how to do this.



## 3\) Mechanical issues

If you know that inconsistent extrusion and temperature variation are not to blame, then there may be a mechanical issue that is causing lines and ridges on the sides of your print. For example, if the print bed wobbles or vibrates while printing, this can cause the nozzle position to vary. This means that some layers may be slightly thicker than others. These thicker layers will produce ridges on the sides of your print. Another common issue is a Z-axis threaded rod that is not being positioned properly. For example, due to backlash issues or poor motor controller micro-stepping settings. Even a small change in the bed position can have a major impact on the quality of each layer that is printed.



# 20\. Vibrations and Ringing

Ringing is a wavy pattern that may appear on the surface of your print due to printer vibrations or wobbling. Typically, you will notice this pattern when the extruder is making a sudden direction change, such as near a sharp corner. For example, if you were printing a 20mm cube, each time the extruder changes to printing a different face of the cube, it would need to change directions. The inertia of the extruder can create vibrations when these sudden direction changes occur, which will be visible of the print itself.



## 1\) Printing too fast

The most common cause for ringing is that your printer is trying to move too fast. When the printer suddenly changes direction, these quick movements will create additional force that can cause the lingering vibrations. If you feel that your printer may be moving too fast, try to reduce the printing speed. To do this, click “Edit Process Settings” and select the Speeds tab. You will want to make adjustments to the “Default Printing Speed” and the “X/Y Axis Movement Speed”. The first controls the speed of any movements where the extruder is actively extruding plastic, while the second controls the speed of rapid movements where no plastic is being extruded. You may need to adjust both settings to see an effect.



## 2\) Firmware acceleration

The firmware that runs on your 3D printer’s electronics typically implements acceleration controls to help prevent sudden direction changes. The acceleration settings will cause the printer to slowly ramp up in speed and then to slowly decelerate before changing directions. This functionality is vital for preventing ringing. If you are comfortable working with your printer’s firmware, you may even want to try decreasing the acceleration settings so that the speed changes more gradually. This can help reduce ringing even further.



## 3\) Mechanical issues

If nothing else has been able to resolving the ringing issues, then you may want to look for mechanical issues that could be causing the excessive vibrations. For example, there could be a loose screw or a broken bracket that is allowing excessive vibrations to occur. Watch your printer closely while it is running and try to identify where the vibrations are coming from. We’ve had many users that eventually traced these issues back to mechanical problems with the printer, so it’s worth checking if none of the suggestions above were able to help.



# 21\. Gaps in Thin Walls

Because your 3D printer includes a fixed size nozzle, you may encounter issues when printing very thin walls that are only a few times larger than the nozzle diameter. For example, if you were trying to print a 1.0mm thick wall with a 0.4mm extrusion width, you may need to make some adjustments to ensure your printer creates a completely solid wall and does not leave a gap in the middle.



## 1\) Adjust the thin wall behavior

The first settings that you need to verify are the dedicated thin wall settings that Simplify3D includes. To view these settings, click “Edit Process Settings” and select the Advanced tab. The software includes several different options for the Internal Thin Wall Type. The default option typically uses something called “gap fill” to fill the small gaps between your thin walls. This will create a back-and-forth infill pattern that adjusts to fill the space between these thin gaps. However, the software also includes another useful option that can fill these thin walls with a single pass. To enable this option, change the Internal Thin Wall Type to “Allow single extrusion fill”. This will use a dynamic single extrusion that will adjust in size to perfectly fill the gap between these walls.



## 2\) Change the extrusion width to fit better

In some cases, you may find that you have better luck changing the size of the plastic that is extruded from the nozzle. For example, if you were printing a 1.0mm thick wall, you could achieve a fast and strong print if your nozzle was setup to create a 0.5mm extrusion. This works best for parts that have fairly consistent wall thicknesses. You can adjust the extrusion width that the software creates by clicking “Edit Process Settings” and selecting the Extruders tab. Choose a manual extrusion width and enter a value of your choosing.



# 22\. Small Features Not Printed

Most 3D printers have a fixed nozzle size that determines the part resolution in the XY direction. Popular nozzle sizes are 0.4mm or 0.5mm in diameter. While this works well for most parts, you may start to encounter issues when trying to print extremely thin features that are smaller than the nozzle size. For example, if you were trying to print a 0.2mm thick wall with a 0.4mm diameter nozzle, you may notice that this thin wall does not show up in the Simplify3D preview.



## 1\) Enable single extrusion walls

Simplify3D includes a specialty printing mode specifically for very thin walls and exterior features. To enable this special mode, click “Edit Process Settings”, go to the Advanced tab, and change the External Thin Wall Type to “Allow single extrusion walls”. After you save these settings, if you return to the Simplify3D preview, you will notice that many of these thin features are now printed using these specialty single extrusions.



## 2\) Redesign the part to have thicker features

If you are still having issues printing these thin features, another option is to redesign the part so that it only includes features that are larger than your nozzle diameter. This typically involves editing the 3D model in the original CAD package to modify the size of the small features. Once you have thickened the small features, you can re-import the model into Simplify3D to verify that your printer is capable of reproducing the 3D shape you created.



## 3\) Install a nozzle with a smaller tip size

In many cases, you are not able to modify the original 3D model. For example, it may be a part that someone else designed or one that you downloaded from the internet. In this case, you may want to consider obtaining a second nozzle for your 3D printer that allows it to print smaller features. Many printers have a removable nozzle tip, which makes these aftermarket adjustments quite easy. For example, many users purchase a 0.3mm nozzle as well as a 0.5mm nozzle to provide two options. Consult your printer manufacturer for exact instructions on how to install a smaller nozzle tip size.



# 23\. Inconsistent Extrusion

For your printer to be able to create accurate parts, it needs to be capable of extruding a very consistent amount of plastic. If this extrusion varies across different parts of your print, it is going to affect the final print quality. Inconsistent extrusion can usually be identified by watching your printer closely as it prints. For example, if the printer is printing a straight line that is 20mm long, but you notice that the extrusion seems rather bumpy or seems to vary in size, then you are likely experiencing this issue



## 1\) Filament is getting stuck or tangled

The first thing you should check is the spool of plastic that is feeding into your printer. You need to make sure that this spool is able to rotate freely and that the plastic is easily being unwound from the spool. If the filament becomes tangled, or the spool has too much resistance to spin freely, it will impact how evenly the evenly the filament is extruded through the nozzle. If your printer includes a Bowden tube (a small hollow tube that the filament is routed through), you should also check to make sure that the filament can easily move through this tube without too much resistance. If there is too much resistance in the tube, you may want to try cleaning the tube or applying some lubrication inside the tube.



## 2\) Clogged Extruder

If the filament is not tangled and can easily be pulled into the extruder, then the next thing to check is the nozzle itself. It is possible that there is some small debris or foreign plastic inside the nozzle that is preventing proper extrusion. An easy way to check this is to use Simplify3D’s machine control panel to manually extrude some plastic from the nozzle. Watch to make sure that the plastic is extruding evenly and consistently. If you notice problems, you may need to clean the nozzle. Please consult your manufacturer for instructions on how to properly clean the inside of the nozzle.



## 3\) Very low layer height

If the filament is spinning freely and the extruder is not clogged, it may be useful to check a few settings within Simplify3D. For example, if you are trying to print at an extremely low layer height, such as 0.01mm, there is very little room for the plastic to exit the nozzle. This gap below the nozzle is only 0.01mm tall, which means that the plastic may have a difficult time exiting the extruder. Double check to make sure you are using a reasonable layer height for your printer. You can view this setting by clicking “Edit Process Settings” and selecting the Layer tab. If you are printing at a very small layer height, try increasing the value to see if the problem goes away.



## 4\) Incorrect extrusion width

Another setting to check within Simplify3D is the extrusion width that you have specified for your extruder. You can find this setting by clicking “Edit Process Settings” and going to the Extruder tab. Each extruder can have its own unique extrusion width, so make sure you select the appropriate extruder from the list of the left to view the settings for that specific extruder. If you extrusion width is significantly smaller than your nozzle diameter, this may cause extrusion issues. As a general rule of thumb, the extrusion width should be within 100-150% of the nozzle diameter. If your extrusion width is far below the nozzle diameter (for example, a 0.2mm extrusion width for a 0.4mm nozzle), then your extruder won’t be able to push a consistent flow of filament.



## 5\) Poor quality filament

One of the most common causes of inconsistent extrusion that we have not mentioned yet is the quality of the filament that you are printing with. Low-quality filament may contain extra additives that impact the consistency of the plastic. Others may have an inconsistent filament diameter, which will also cause inconsistent extrusion. Finally, many plastics also have a tendency to degrade over time. For example, PLA tends to absorb moisture from the air, and over time, this will cause the print quality to degrade. This is why many spools of plastic include a desiccant in the packaging to help remove any moisture from the spool. If you think your filament may be at fault, try swapping the spool for a new, unopened, high-quality spool to see if the problem goes away.



## 6\) Mechanical extruder issues

If you have verified everything above and are still having problems with inconsistent extrusion, then you may want to check for mechanical issues with your extruder. For example, many extruders use a drive gear with sharp teeth that bite into the filament. This allows the extruder to move the filament back and forth easily. These extruders also typically include an adjustment that changes how hard the drive gear is pressed into the filament. If this setting is too loose, the drive gear teeth won’t cut far enough into the filament, which impacts the extruder’s ability to accurately control the position of the filament. Check with your manufacturer to see if your printer has a similar adjustment.



# 24\. Warping

As you start printing larger models, you may start to notice that even though the first few layers of your part successfully adhered to the bed, later on the part begins to curl and deform. This curling can be so severe that it actually causes part of your model to separate from the bed, and may cause the entire print to eventually fail. This behavior is particular common when printing very large or very long parts with high temperature materials such as ABS. The main reason for this problem is the fact that plastic tends to shrink as it cools. For example, if you printed an ABS part at 230C and then allowed it to cool to room temperature, it will shrink by almost 1.5%. For many large parts, this could equate to several millimeters of shrinkage! As the print progresses, each successive layer will deform a bit more until the entire part curls and separates from the bed.



## 1\) Use a Heated Bed

Many machines come equipped with a heated bed that can help keep the bottom layers of your part warm throughout the print. For materials such as ABS, it is common to set the heated bed temperature to 100-120C, which will significantly reduce the amount of plastic shrinkage in these layers. To adjust your heated bed temperature, click on “Edit Process Settings”, select the Temperature tab, and then choose your Heated Bed from the list on the left-hand side. You can double-click on the temperature setpoint to edit the value.



## 2\) Disable Fan Cooling

By now, you probably realize that cooling can be a problem for parts that tend to warp. For this reason, many users prefer to disable any external cooling fans entirely when printing with materials such as ABS. This allows all of the layers to stay warm for a longer period of time, increasing your chance of success.



## 3\) Use a Heated Enclosure

While a heated bed can keep the bottom layers of your part warm, it may struggle to keep the upper layers of the part from contracting once you start printing taller and taller objects. In this situation, you may find it useful to place your printer inside of an enclosure that can help regulate the temperature of the entire build volume. Some machines may already include an external enclosure specifically for this reason. If your machine does include a heated enclosure, make sure to keep the doors closed during the print, which will keep the heat from escaping.



## 4\) Brims and Rafts

If you have already tried all of the other suggestions, but your parts are still curling later on in the print, then you can also try including a brim or a raft with your print. These features will help hold the edges down and may warp less, since they are typically only a few layers tall.



## 5\) Troubleshooting

● Use PrusaSlicer profiles – Make sure you are starting off by using corresponding default profiles in PrusaSlicer. You may save yourself a lot of hassle with figuring out the ideal settings yourself. Profiles are already refined for each material.

● Keep the surface free of grease – Before starting any of your prints, simply wipe the print surface clean with IPA 90%+. A complete guide on how to prepare the print surface can be found at First layer issues.

● Lower the Live Adjust Z slightly to increase bed adhesion. But not too much. Do not over-squish the first layer. Be aware the bed adhesion might be too high with PETG or PC and might result in a damaged PEI surface.

● Print cooling.  Some materials such as PLA or PETG need a lot of cooling. If corners of your print are lifting up, check if the print fan is enabled, try increasing the print fan speed. Check if the print fan actually works and the fan shroud isn´t obstructed or molten.

● If steep overhangs and small parts of your print are warping, you may try enabling the print fan at low speeds (10-20%) even for materials that do not require a lot of print-cooling such as ABS or PC-Blend. This may help for example if you have a printer in an enclosure or if the problematic part is drowned in between supports that are retaining heat. Be aware that too much print-fan speed may warp and lift up the whole object and may decrease layer-to-layer adhesion. Our goal is to cool the part neither too fast nor too slow.

● If you experience lower layer-to-layer adhesion or even print cracking after raising the print-fan speed, try increasing the nozzle temperature to restore the bonding of the individual layers together properly.

● Ambient temperature – For high-temperature filaments, try to maintain a stable ambient temperature. An open window or an AC unit nearby the printer will increase the occurrence of warps. High-temperature materials generally require higher ambient temperature not to warp during printing. If you print with these materials most of the time, you should consider having the printer in an enclosure. Printing PLA or PETG in an enclosure might not be a good idea. These materials need a lot of print cooling, which is harder to achieve with a higher ambient temperature. It is possible to either purchase an enclosure in our e-shop. You can purchase the Original Prusa Enclosure in our e-shop. It is also possible to make your own enclosure.

● Use a skirt and try to print more objects at once. For high-temperature materials such as PC-Blend, ASA, or ABS, try using a printed skirt (draft shield) to retain heat in and around the printed object. Printing more objects at once may also help with retaining heat. Try to orient the problematic parts of the objects towards the center of the heatbed.

● Decrease the print speed. This may help a lot with high-warping materials. Although Prusament PC-Blend is low-warping compared to other PC-Blend filaments, decreasing the print speed will help your part as a whole to settle down, melt individual layers together properly and warp less. It also increases the layer-to-layer adhesion and part strength.

● Use the brim – A brim is a good way how to increase the adhesion to the print surface.

● If the brim isn't enough, try adding a small geometry (like a tiny cylinder) specifically to the culprit area. The object should only be a few layers tall so it is also easy to remove.



# 25\. Poor Surface Above Supports

One of the major benefits of Simplify3D is the ability to create innovative support structures which allow you to create incredibly complex parts that would be hard to manufacture otherwise. For example, if you have a steep overhang or part of your model with nothing below it, then a support structure can provide a foundation for these layers. The support structures created by Simplify3D are disposable and can be easily separated from the final part. However, depending on your settings, you may find that some adjustments are needed to perfect the surface quality on the underside of your parts, right above the support structure foundation.



## 1\) Lower Your Layer Height

The overhang performance of your printer can be greatly improved by lowering your layer height. For example, if you reduced your layer height from 0.2mm to 0.1mm, your printer will create twice as many layers, which allows your printer to take smaller steps when creating an overhang. For this reason, your may find that you need support structures for any overhang above 45 degrees when using a 0.2mm layer height, but your overhang performance may improve to 60 degrees if you lower your layer height to 0.1mm. This has the obvious advantage of decreasing your print time and reducing the amount of support structures required for the print, but it will also allow you to create a smoother surface on the underside of your parts. If you find that you need to increase the print quality in this area, this is one of the first settings you will want to adjust.



## 2\) Support Infill Percentage

Just like the interior of your part, you can also adjust the density of your support structures by changing the Support Infill Percentage. It is common to use a value around 20-40%, but you may find that you need to increase this value if the bottom layers of your part are drooping too much. Many users also prefer to use Dense Support Structures for this task, as they allow you to use a lower density for the majority of your supports, and only use a higher infill percentage near the very top of the support structures.



## 3\) Vertical Separation Layers

Creating removable support structures involves a fine balance between the amount of support provided to the model, and how easy the supports are to remove. If you provide too much support to the model, the support structures may start to bond to the part, making them difficult to separate. If you provide very little support, the disposable support structures will be easy to remove, but the part may not have enough of a foundation to print successfully. Simplify3D allows your to customize the separation settings, so that you can choose the correct balance between these different factors. The first setting you will want to check is the Upper Vertical Separation Layers. This setting determines how many empty layers are left between the support structures and the part. For example, if you are printing your support structures with the same material as your part, it is common to use at least 1-2 vertical separation layers. Otherwise, if you used 0 separation layers and you are printing everything with the same material, the supports may bond to the part and can become difficult to remove. So this is one of the first settings you want to adjust as you try to perfect your print quality.



## 4\) Horizontal Part Offset

The next separation setting you should check is the Horizontal Offset from your part. This setting controls the side-to-side distance between your part and the support structures. So while the Vertical Separation Layers can help keep the top of your supports from bonding to the bottom of your part, the Horizontal Offset will keep the sides of your supports from bonding to the side of your model. It is common to use a value between 0.2-0.4mm for this setting, but you may need to experiment and see what works best for your specific extruder and filament.



## 5\) Use a Second Extruder

If your machine comes with 2 or more extruders, you can achieve a significant improvement by using a different material for your support structures. For example, it is quite common to print parts in PLA using water dissolvable PVA for the supports. Because the model and support structures are printed with different materials, they won’t bond together as easily, which allows you to do a better job of supporting the part. If you are using a different material for the support structures, you can frequently decrease your Upper Vertical Separation Layers to zero, and reduce your Horizontal Offset from the part to around 0.1mm.



# 26\. Dimensional Accuracy

The dimensional accuracy of your 3D printed parts can be extremely important if you are creating large assemblies or parts that need to precisely fit together. There are many common factors that can affect this accuracy such as under or over-extrusion, thermal contraction, filament quality, and even the first layer nozzle alignment.



## 1\) First Layer Impact

Settings for your first layer can have an impact on dimensional accuracy. If your nozzle is too high or too low for the first layer of your print, it can drastically affect the next 10-20 layers of the part. For example, if you are printing a 0.2mm thick layer, but your nozzle is only positioned 0.1mm away from the bed, then this extra plastic may create a first layer that is a bit too large. Future layers can also be affected by the extra plastic on this layer, which creates several oversized layers at the bottom of the part. So before you spend too much time trying to perfect the dimensional accuracy of your prints, you need to verify that your measurements are not being affected by the first layer position. One common way to do this is by printing a model with 50-100 layers and then only measuring the top 20 or so layers. These top layers are far away from the very first layer that was printed on the bed, so it minimizes the impact of nozzle positioning. Before proceeding to the sections below, make sure that your measurements follow these guidelines.



## 2\) Under or Over-Extrusion

Now that you know you are using accurate measurements that are not affected by the first layer position, the next setting you want to verify is your extrusion multiplier. This setting affects the flow rate for the entire print. If the extrusion multiplier is too low, you may start to see gaps between perimeters, holes in your top surfaces, and parts that are smaller than their intended size. If your extrusion multiplier is too high, you may notice top layers that tend to bulge upwards and parts that are larger than intended. So again, before proceeding to the sections below you will want to verify that your extrusion multiplier is properly calibrated. For more advice on these topics, please see the Under-Extrusion and Over-Extrusion sections.



## 3\) Constant Dimensional Error

If you have completed the steps above and the prints are still not sized correctly, Simplify3D offers the ability to precisely offset the edges of your print to account for these differences. This setting is labeled “Horizontal size compensation” and can be found on the Other tab of your Process Settings. For example, setting this value to -0.1mm will shrink your model by 0.1mm in the X and Y directions. This setting works best when the dimensional error is consistent, even when printing models of different sizes. For example, if the part is always 0.1mm too large, regardless of if the model is 20mm wide or 100mm wide, then this setting can easily account for that difference.



## 4\) Increasing Dimensional Error

If you notice that the dimensional error tends to increase as you print larger parts, then there is a different setting you can adjust. For example, if your print was 0.1mm too small for a 20mm wide part, but increased to 0.5mm too small for a 100mm wide print, then it is likely the problem may be due to thermal contraction. This can be a common issue for high temperature materials like ABS, since plastic tends to shrink as it cools. Simplify3D includes several options to help with this. First, you need to determine the shrinkage percentage. In the above example, the part is shrinking by 0.1mm over a 20mm print, so the shrinkage percentage is 0.1 / 20 = 0.5%. The easiest way to fix this error is to double-click on your model in the Simplify3D interface and set the scale to 100.5%. If you find yourself making these changes consistently, you can also setup an Import Action to perform this scaling automatically each time you import a new model.



# 27\. Poor Bridging

Bridging is a term that refers to plastic that needs to be extruded between two points without any support from below. For larger bridges, you may need to add support structures, but short bridges can typically be printed without any supports to save material and print time. When you are bridging between two points, the plastic will be extruded across the gap and then quickly cooled to create a solid connection. To get the best bridging results, you will need to make sure that your printer is properly calibrated with the best settings for these special segments. If you notice sagging, drooping, or gaps between the extruded segments, you may need to adjust your settings for the best results.



## 1\) Verify bridging settings are being used

Bridging segments are identified with a special color in the Simplify3D preview. Click “Prepare to Print” to enter the Preview Mode and then change the coloring mode on the left-hand side to “Feature Type”. This will use a different color for each feature type, with bridging regions shown in yellow. Use the sliders at the bottom of the preview to scroll to the layer where you expect to see bridging extrusions and verify that these lines are shown in yellow. If the bridging area is not shown in yellow, there are a two settings you will want to check. Exit the preview, click “Edit Process Settings”, and go to the Other tab to view your Bridging settings. The first option in this section is the “Unsupported area threshold”. This allows the software to ignore very small bridging areas and focus on the larger bridging regions that may need special settings. If you think your bridging area is not being included, make sure that the area of your bridging region is larger than this threshold value. The second setting to check is towards the bottom of this list. By default, Simplify3D uses special perimeter settings for any perimeters that are printed as part of a bridging region, but you can also choose to use bridging settings for these regions if you wish. To do this, enable the “Apply bridging settings to perimeters” option, save your settings, and then return to the Simplify3D preview to verify your changes.



## 2\) Check the angle used for the bridging infill

Simplify3D will automatically calculate the best infill direction to use for your bridging regions. For example, if you are bridging between two pillars aligned on the X-axis, the software will automatically change the infill direction for that area to ensure the infill is also being extruded along the X-axis. This greatly improves your odds of success, so if you notice that you are getting poor bridging results, you want to double-check to make sure the infill is oriented in the correct direction. If you have already verified that your bridging region is properly identified as a yellow bridging region in Simplify3D, then this change should happen automatically. If you ever want to try a different infill angle for these bridging layers, you can also do this by enabling the “Use fixed bridging angle” option in your process settings.



## 3\) Adjust settings for optimal performance

The bridging regions in Simplify3D are printed with special extrusion, speed, and cooling settings to achieve optimal performance. The extrusion and speed adjustments for these regions can be found on the Other tab of your process settings. Typically, you will want to set the “Bridging extrusion multiplier” to 100% or more, as lower values may have trouble properly sealing the bottom of these surfaces. The “Bridging speed multiplier” may require some experimentation, as some printers will perform better with slow bridging, while others get better results by moving quickly. Finally, you can find the bridging fan speed settings on the Cooling tab of your process settings. Typically, you will want to set the “Bridging fan speed override” to a large value to make sure the bridges are cooled as quickly as possible. Experiment with these settings to find the best combination for your specific 3D printer and filament. There are many bridging test models available that can help with this calibration.



## 4\) Use supports for longer bridges

In the event that you are unable to get the results you want after tuning the settings mentioned above, you may find that adding support structures will allow you to achieve the best quality. The support structures will provide an extra foundation for the bridging regions, greatly improving their odds of success. You can enable support generation for the entire model, or use Simplify3D’s customizable support structures for extra control.



# 28\. First Layer Issues

This is by far the most common 3D printing problem, and probably the first one you may encounter. The first layer is the essential one because it is the base of the printed object. Therefore, if it isn’t perfect, the chance of print failure increases. Many common 3D printing problems stem from a poor first layer.



## 1\) How to prepare your print surface

If you don't touch the print surface with your hands or dirty tools, then you don't have to clean it before every print. Clean your tools the same way you would the bed, and you will be able to start your next print right away.

\- Isopropyl alcohol

To achieve the best adhesion of the print surface, it is vital to keep it clean. The best option when printing with ABS, PLA, and many other materials is 90% Isopropyl alcohol, which can usually be sourced locally at drugstores or hardware stores. Denatured alcohol is also an option. We recommend always using 90% IPA. Solutions with lower percentages may contain unsuitable chemicals and oils.

PETG, ABS, ASA, XT, and CPH filaments are an exception - the adhesion may be too strong, and you can damage your Smooth PEI sheet. We recommend using a separating agent (e.g. a glue stick).

\- Dish soap and water

If the adhesion seems to decrease over time even when using IPA, you can clean the steel sheet with a few drops of dish soap and warm water (not hot!). This should not be done often, and do not submerge the sheet completely in hot water, but it will dissolve some oils and sugars that gather over time and that IPA does not remove. Make sure to use only dish soap and dry the sheet well before using it.

\- Acetone

PEI can lose its adhesive powers after a couple of hundred hours. When you see models coming loose regularly, wipe the surface thoroughly with acetone to restore the adhesion. This should only be used in the smooth PEI sheet and only around once per month. Do not overuse acetone. Extended use makes PEI surface brittle. Also, do not use acetone before printing with PETG.

\- Glue

Glue is a great, easy-to-use tool to increase adhesion. It also creates a protective separation layer. No need for glue specially made for 3D printing. You can use a basic (PVA-based) glue stick. From our experience, it is not needed when printing PLA, but may it be advisable when printing:

● Polyamide (Nylon)

● PETG

● Polycarbonate (PC)

● PET-based materials

● ABS

● ASA

● Other more exotic materials

● Flexible materials



## 2\) Resurface it

It can happen that you will leave some small marks on the print surface with your nozzle or tools. Typically, they will be shinier than the rest of the pad. It does not affect functionality or adhesion. However, if you want to have the same surface look on the whole print bed, you can resurface it. The easiest way is to take the hard side of a dry kitchen sponge and gently wipe the affected area in a circular motion a few times. Another option is to use fine-grit sandpaper (400-600) and lightly give the sheet a rub. Wipe over with IPA after doing so.



## 3\) The nozzle is too close/far from the sheet (MK2/MK2.5/MK3/MK3.5)

If the nozzle is too close to the printing bed, there won’t be enough room for the plastic to come out of the extruder. By having the nozzle too close to the print surface, you will essentially block its opening, so that no plastic can be extruded. You can easily recognize this issue when the printer does not extrude plastic for the first layer or two. Use the Live Adjust Z function and First Layer Calibration (i3) options to tweak the height of the nozzle. You perform the calibration from LCD Menu –> Calibration –> First layer calibration.



## 4\) Speed and temperature

\- Decrease the printing speed

If the steps described above didn’t help, then try decreasing the printing speed. The easiest way how to do it is by rotating the knob during the printing process, lowering the percentage. Counterclockwise = decrease speed, Clockwise = increase speed. We suggest decreasing the speed to about 75% for the first three layers, and then returning it to normal.

\- Use recommended printing temperatures

Make sure to use the recommended nozzle and heatbed temperatures. PrusaSlicer will configure them correctly based on the selected material, so you don’t need to adjust the temperatures manually on the printer itself. If you are experimenting with new materials that don’t adhere well, you can try to increase the heatbed temperature by 5-10 °C. This way the plastic will stick a bit better.



## 5\) A full or partial clog

The extruder could be clogged. This can happen either when excessive debris gets stuck inside the nozzle, when hot plastic is kept inside the extruder for too long, or when the thermal cooling for the extruder is not sufficient and the filament begins to soften outside of the desired melt zone.



## 6\) Uneven surface

If your print surface is not flat and the alignment of the mesh does not help, to achieve a flat print surface, a temporary solution is to add a piece of paper under the uneven area of the steel sheet. A more permanent solution would be to perform the firmware Bed Level Correction.

\- Correctly placed sheet

Before printing, make sure that you have the print plate properly installed, and that there are no leftovers from the previous print or a piece of loose filament that could affect the sheet position. Also, make sure that the sheet is straight and not bent or damaged.



## 7\) Brim

Before you consider applying extra adhesion materials onto the bed, consider using the Brim option in PrusaSlicer, which increases the surface area of the first layer.



## 8\) Expansion joints (MK4, MK3.9, MK3.5)

On the Original Prusa MK4, having the Magiboxes in the wrong orientation can cause an uneven first layer. Make sure that all of them have the full side facing the center of the carriage.



## 9\) Nozzle conditions (MK4, MK3.9, XL)

The nozzle on the Nextruder has to be at the correct height. If you are not sure if the height is correct, open the thumb screws on the side of the heatbreak, and push the nozzle up. Tighten the thumb screws just by hand, do not use any tools. If you have a Nozzle Adapter, check the installation again to make sure that the nozzle has not been lowered with the installation of the adapter.



## 10\) LoadCell check (MK4, MK3.9, XL)

If the filament is loaded while the printer is doing the leveling at the start of a print, check if the extruder is not pulling the filament down by loosening the filament spool a little. If you have the filament being fed by a PTFE tube, make sure that the tube is not short. After the previous checks, go into the printer menu to Control -> Calibrations \& tests -> 4. Loadcell test, and make the LoadCell test per screen instructions.



## 11\) Mechanical checks (XL)

\- Core XY

If your first layer is showing one side higher than the others on the Original Prusa XL, check the assembly of the Core for any loose screws which hold the Core to the four extrusions. Also, use the torque indicator to make sure the screws are tightened correctly.

\- Heatbed Tiles

Check if any of the screws under each heatbed tiles are loose.

\- Z-axis bearing housing

Re-print the two Z axis bearing housing parts, and replace them in the printer.



# 29\. Layer Shifting

Layer shifting is a printing issue, which causes the layers of the printed object to shift from their intended positions.  It is usually associated with an abnormal movement of the X-axis and/or the Y-axis, leading the extruder head to be misaligned mid-printing.



## 1\) Check your printer’s power mode

Run the printer in Normal mode rather than in the Stealth mode. You can change Power mode in the LCD Menu -> Settings -> Mode. The stealth mode is perfect for small and simple objects. For bigger or more complex prints, the Normal mode is recommended. Also, note that in Stealth mode, the Crash detection feature is not available.



## 2\) Make sure the extruder and the heatbed can move freely

Make sure there are no obstructions in the path of the extruder or heatbed and their bearings. For example, there might be a piece of filament stuck around the belt (usually around the Y-axis pulley) from your previous prints. Another instance of obstruction is when the zip ties or another part of the extruder cable bundle are not arranged according to 5. E-axis assembly. If the cables hit the frame before the extruder assembly does (if it's an MK3) or before the X end-stop does (if it's an MK2/S or an MK2.5) the printer detects an inaccurate end position. See the photo below and make sure the cables are arranged accordingly. Also, verify if the smooth rods don't bear any deep scratches and if the bearings are properly lubricated. According to our testers, the best lubricant is a homogeneous, soft grease with lithium additives, such as the GLEIT-µ HF 400. Another good lubricant is the Mogul LV 2-EP. In general, Super-lube or any other multi-purpose grease will do as well.



## 3\) Check your X/Y axis motors and pulleys

Make sure the X and Y motor is tightened in the motor mount, that the pulley (orange arrows in the picture below) is secured on the motor shaft and aligned with the pulley on the opposite end, and that the pulley can move freely. Both grub screws need to be tight, one of them has to be tightened against the flat part of the motor shaft. A loose pulley is usually the main cause of staircase layer shifts. Both pulleys on both axes also have to be aligned, meaning the motor pulley has to be well centered and the belt has to be moving in a straight line, not traveling from right to left while the pulley is turning.



## 4\) Check the tension of your belts

Check your belt-tension. If you have an MK3 or MK3S, check the Belt Status numbers via LCD menu -> Support -> Belt Status. The values should not be under 240 and above 300, but there is no single ideal value. The number does not represent any quantity.

● If your value is under (or close to) 240, you need to loosen the belt

● If your value over (or close to) 300, you need to tighten the belt

● The values are updated every time you run the Selftest or run the belt test in LCD menu -> Calibration -> Belt test.

The MK2.5S, MK2.5, and lower models do not have the belt status option. The clue we can give you is that the belt should sound roughly like a low bass string when plucked. It should be possible to pinch the two sides together with your thumb and index finger, but you should feel a little bit of resistance.



## 5\) Print geometry and settings

Objects with overhangs are generally harder to print. Some overhangs might even warp upwards during the print, and the nozzle might crash into them. The same can happen in some cases if you choose too small infill percentage when slicing the 3D model. To prevent printing overhangs, you can cut the object (check out our article on the Cut tool). You can also try to increase the print fan speed or increase the Z-hop distance in PrusaSlicer. Print fan speed is found in Filament settings -> Cooling and Z-hop distance in Printer Settings -> Extruder 1.



# 30\. Print doesn't appear / Resin does not solidify

## 1\) Insufficient/Incorrect exposure times

Make sure you are using the correct preset with the recommended exposure times for your resin, in PrusaSlicer. If your resin does not have a dedicated preset, use the Resin Calibration (SL1/SL1S) to determine the correct values.



## 2\) Old or separated resin

If the resin is not stored correctly, or you use the same batch, again and again, it can lose its original properties and won’t solidify anymore. Try a new batch of resin if you kept re-using one batch several times. If the resin remains in the vat for too long it can start separating its reactive components and its oil solution (notice the lines of color difference in the picture below). Even though the printer will stir the resin using its tilt platform it may not be sufficient. With a gloved finger or a spatula, carefully stir the resin until its color is uniform.



## 3\) A large amount of Isopropyl alcohol (IPA) in the resin/on the platform

If the platform is still wet of IPA after cleaning when the print begins, the IPA will repel the resin and the print will not stick to the platform upon exposure. Make sure you wipe the platform dry before starting your print. If a lot of IPA has dripped into the resin tank it can dilute the resin to the point where it will lose some of its properties. Empty the tank and try a new batch of resin.



## 4\) Faulty print display or UV LED panel

Check whether the UV panel and LCD screen work as intended – Run the Display test, found at Settings -> Calibration-> Display test. If the logo does not appear on the display, but it is lit from the back, check the display’s wiring. To do so, remove the black cover secured by eight screws, then inspect the cable leading from the exposition (print) display. You can carefully disconnect and reconnect the cable header from the mainboard to ensure that it is seated correctly. If it remains completely dark may be due to a faulty UV LED panel. Check its wiring by unplugging it and plugging it back in, making sure the connector is seated properly. Test the display again and if it still does not work it will have to be replaced. Make sure the cooling fan for the UV LED panel is working. Without it, both the UV LED panel and print display can overheat and be damaged. If you need to change your print display, you need to calibrate the display to your machine. Both are available in the e-shop as a bundle, if you do not have a calibrator already.



# 31\. Watertight Prints

## 1\) Geometry

The shape of the model obviously matters. Thick walls which require infill is often waste in this case. It can cause irregularities and may leak into the void between the inner and outer walls, creating a place where all kinds of nasty stuff can grow. A wall should be even. Artifacts like protrusions for showing the water-level etc. can cause issues. In the picture below is a PLA print where everything is water-tight, except by a little nubbin for this purpose.



## 2\) Perimeters

You want to go with at least 3-4 perimeters for a single wall. Depending on the geometry you can also increase this to 5-6, but is rarely necessary.



## 3\) Temperature

To ensure a proper bond between the layers we would recommend raising the Nozzle-temperature with 5-10C over the presets available or use the highest recommended temperature on the box of the filament (You can also go about 5c above this).



## 4\) Extrusion-multiplier

This refers to the flow rate of the filament and is set in PrusaSlicer under Filament Settings. Increase this by 5-10 percent from the default value. Another way of manipulating this is to set the line width 5-10% wider (i.e. from 0.4mm to 0.44mm), but this can affect other aspects of your print. If in doubt experiment, or do the simple option.



## 5\) Layer-height

Very high layer-heights just won't do, but having very tight layers will also increase the number of places where something can go wrong. CNC-kitchen found that the most durable prints were at 0.15mm height, but 0.2 will do fine. If you want to print fast and have very high layers (like 0.4mm+) get a larger nozzle. Generally, for best results, you should not use a height of more than 60-65% of your nozzle width.



## 6\) XY-Overlap and other settings

This applies more to if your print leaks from the bottom, and you have tested with the previous suggestions. XY-Overlap is a variable in PrusaSlicer that says how much a line of solid infill crosses the perimeter. This is by default set to 10% (of nozzle diameter, so 0.04mm). Increasing the temperature and extrusion multiplier will affect this, but if you still see leakage you can try to increase this to 25-35%. This XY overlap is meant to be used with the standard Monotonic line top fill pattern, which requires less overlap.



# 32\. Object missing details

The Original Prusa SL1 3D printer can produce objects with an incredible amount of detail – tiny wrinkles on cloth of a figure, texture of skin, thin railings on buildings, etc. However, in case the printed object is missing small details (not entire parts of the model), it can be due to incorrect exposure times. Make sure you are using the correct preset for your color/resin in PrusaSlicer.



## 1\) Insufficient exposure

Too short exposure times will result in details being “melted” together. Increase the exposure times to recommended values to fix this issue.



## 2\) Overexposed layers

Long exposure times will result in a “staircase” effect – the layers won’t blend into each other perfectly and some details may be lost due to this effect. Use the recommended exposure time values to fix this issue.



# 33\. Scratches/bubbles on prints

Bubbles or small scratches (also appearing like cracks) on the object are caused by small pieces of dirt or debris in the tank (vat) you are using. These small objects travel in the tank during printing, creating paths that resemble scratches as they move. Make sure that the resin is 100% pure and free of small dirt particles. Filter the contaminated resin, for example, through a coffee filter. Also make sure your print tray is 100% clean and there are no dirt particles on the FEP film. Rinse the tank in warm water and then dry it with a paper towel.

Example – The Benchy Hull Line

The 3DBenchy is a 3D model designed by CreativeTools specifically for testing and benchmarking 3D printers. And everyone wants to know, how to print a perfect Benchy. Ever since it’s release, one specific problem seems to be present, in varying degrees of severity, in all of its prints - the infamous Benchy hull line. It’s visible on prints from all FFF printers on the market, cheap or expensive. It’s visible no matter the slicing software. It’s visible when printing from any material. It’s visible even in the Benchy release video from 2015. Again, in varying degrees of severity - with some combinations of printer, slicer, and material, it can be almost invisible. Other times, it’s clearly defined, leaving the user disappointed and confused. But once you see it, you’ll be able to find it on essentially all of its prints.



## 1\) A hardware problem?

When you search for the problem online, you’ll often get an (incorrect) suggestion, that it might be a hardware problem. To give you an example, here are some of the suggestions we found online:

● loose belts

● bent Z-axis rods

● irregularity in your z-axis lead screw at that height



## 2\) The culprit

We believe that the main culprit is the sudden transition from sparse infill into full top layers around the 8 mm height (may vary a bit depending on your layer height and number of top layers).  At this point, there is an abrupt difference in the time a layer takes to print. And a few layers later, another sudden change happens. When the deck is finished it’s no longer an almost solid layer, but just a few perimeters again. Here are the factors that influence the severity of the Benchy hull line

● Filament material thermal expansion coefficient

● Print cooling

● Print environment

● Other filament properties - dryness, composition

A seemingly similar, yet partly different problem is when printing boxes. They also tend to have a line at the height where the bottom solid layers transition into walls. This has more to do with thin walls, extrusion width, and the material has nowhere to go, but outside. Our slicer team knows about this problem and it's something that will likely improve in the future.



## 3\) Why can’t the slicer automatically detect and correct for this?

It’s physics. Plastics, if extruded first from pellets into a filament, and then from filament into a very thin rectangular extrusion, will behave neither as a liquid nor as a solid. The stretching of the plastic will align the long molecular chains of the polymer, introducing internal stresses to the extrusion. This internal stress will pull the extrusion together if not cooled quickly enough. For example, on the MK2 the 3D Benchy has the line more pronounced on the side away from the cooling fan. It depends on the environment too. Indeed, as many of you found out, in a cool basement the effects are more pronounced. The same G-code printed on the same printer with the same filament can have a Benchy hull line in one room and not in the other. It’s very difficult to automatically compensate for that. And to compensate for the internal stresses and cooling effects of the filament. One of the reasons being the viscoelastic behavior of the molten plastics, and the dependence of the plastic behavior on its composition, temperature, hydrolysis of the polymer molecular chains. If the filament is not 100% dry (polyesters - PLA \& PET are sensitive to hydrolysis, hydrolyzed filament contains shorter polymer chains, thus being less viscous), the effectivity of the cooling, reflections of the cooling air from the already printed objects, etc.



## 4\) How did we modify the G-code to eliminate it?

Something that helps, is to make a modifier mesh in the shape of the deck. When aligned at the problematic spot, it can be used to split the hull and the deck. They are then printed separately, plus the infill doesn’t fill the entire area all the way to the hull perimeters. Then there’s the order of elements inside a layer. For some reason, we got better results when always printing the deck perimeters first, then infill of the deck and then the rest of the layer. We manually edited this order using a text editor. We’re not sure if it ended up helping, but we also manually edited the G-code in order to slightly lower the flow of solid infill, except for the very top layer (of the deck). Another thing is to print the perimeters as continuously as possible. Rather than printing perimeters, then infill and then transitioning to the next layer it’s better to print two (or more) layers of perimeters one right after another. The printer then can go back and print the infill, again two layers at a time. We most likely haven’t discovered all factors and in precisely what ratios they influence the severity of the Benchy hull line. Still, we wanted to share our findings. If you make your own research and tests, let us know of your findings.



# 1\. Out of Filament

Nothing is printing even though the model has been set and configured correctly in the slicing software. However, try as you might when repeatedly sending the print to the printer still nothing happens bar the odd spit of filament emerging from the nozzle. Alternatively a model is part way through the print and the filament extrusion stops but the nozzle continues to print into air.

Cause

It’s an obvious problem that’s unmissable in many printers such as the Prusa i3 style machines where the filament reel is in full view, but on other printers such as XYZ DaVinci, Cel Robox and Ultimaker machines, the issue isn’t always immediately obvious. These and many other printers either encase the filament within the design of the printer, or the filament is hidden round the back. Of course, some printers feature smart spools that feed back data to the software and highlight if the filament reel is close to, or out of material. However we all like to tinker and use our own tweaked firmware or third party software, and these sometimes work around such failsafes. And then there are other printers that simply don’t feature any type of failsafe at all. In all cases, especially with Bowden style extrusion systems, you’re going to have to extract some remaining filament and then feed in fresh material.



## 1\) Check the filament reel

Look at the filament reel and see if there’s any filament left. If not load a new reel. Easy.



# 2\. Nozzle Too Close to Print Bed

Inexplicably, despite loading the filament and the print head moving without a hitch, no filament is depositing on the print bed.

Cause

Quite simply, your nozzle may be too close to the print bed. If you’ve somehow tuned your print bed to mere microns from your nozzle opening, it’s unlikely the melted filament has room to escape. At best your print will be missing its first layers, and have a higher chance of not sticking once the filament does extrude. At worst, you’ll cause a backup of melted filament in your hot end, possibly leading to a blockage.



## 1\) Z-AXIS OFFSET

Just raising the height of the nozzle slightly can often help. Most 3D printers in their system settings will allow you to set a Z-axis offset. To raise your nozzle away from the print bed you’ll need to increase the offset into the positive value. This also works for the reverse, with a negative offset helping to address your prints not sticking to your bed.



## 2\) LOWER THE PRINT BED

Alternatively if your printer allows for it, you can achieve the same effect by lowering your print bed. This is the more troublesome fix though, as it requires you to re-calibrate and level the bed for even prints.



# 3\. Blocked Nozzle

You initiate a print job but whatever you try, nothing comes out of the nozzle. Extracting the filament and reinserting doesn’t work.

Cause

A small piece of filament has been left behind in the nozzle after changing spools, often because the filament has snapped off at the end. When the new filament is loaded, the piece of old filament that is left in the nozzle doesn’t allow the new filament to be pushed through. A little printer maintenance can go a long way to reducing the chance of problems like a blocked nozzle affecting your extrusions. In fact you’ll often find that before a clog even appears, there is old carbonized filament sitting inside your nozzle. It can and will sit there for weeks or even months without you realizing, but there will be small signs in the quality of your prints. The effects are often overlooked; such as small nicks in the outer walls, small flecks of dark filament, or small changes in print quality between models. These defects are often simply put down to the slight variations we come to expect from 3D printers, but really there could be something a little more sinister going on. A cleaning method known as the Atomic Pull or Cold Pull (which we detail below) can clear this up. You’ll commonly see this if you frequently switch from a PLA to ABS, for example. A small amount of PLA is left in the nozzle, and it is heated beyond its normal melting point. That can mean it will carbonize and burn. Likewise, switch between ABS and Nylon and again you’ll witness something similar. It’s not uncommon to see a wisp of smoke appear briefly as the new filament is fed through.



## 1\) UNBLOCK WITH A NEEDLE

If you’re lucky then unblocking can be a quick and easy process. Start by removing the filament. Then using your printer’s control panel (if it has one) select the “heat up nozzle” setting and increase it to the melting point of the stuck filament. Alternatively, hook your printer up to a computer running compatible control software and heat the nozzle using that. For PLA set the temperature to 220 °C. Once the nozzle reaches the correct temperature, use a small pin to clear the hole (being careful not to burn your fingers). If your nozzle is 0.4mm then you need a pin that is smaller; an airbrush cleaning kit works perfectly.



## 2\) PUSH OLD FILAMENT THROUGH

If you find that the nozzle is still blocked then you may be able to push the filament through with another bit of filament. Start by removing the filament as before and then remove the feeder tube from the print head. Heat up the hot end to 220 °C for PLA and then use another piece of filament to push this through from the top to try to force the stuck filament in the nozzle out. Usually, if the new filament hasn’t succeeded in unblocking then the extra pressure you can exert by hand might just do the job. However, don’t push too hard as you’ll risk bending the horizontal printer rods.



## 3\) DISMANTLE AND REBUILD THE HOT END

In extreme cases when the nozzle remains blocked, you’ll need to do a little surgery and dismantle the hot end. If you’ve never done this before then it’s a good idea to make notes and take photographs so you know where everything fits when you reassemble. Start by removing the filament, then check your printer’s manual to see exactly how to dismantle the hot end.

\+ The Atomic Pull

1\) ATOMIC PULL PART I – CHOOSE A MATERIAL

You can use ABS or Nylon for this, but over time we’ve found that the most consistent results come from Nylon due to its higher melting point. The filament also holds its shape far better. ABS is more common however, so we’ll use it here.

2\) ATOMIC PULL PART II – REMOVE FILAMENT

Start by removing the filament that’s already in the print head in the usual way for your printer. Then remove the Bowden tube or release the direct drive, so that when the time comes you can manually feed the filament through.

3\) ATOMIC PULL PART III – INCREASE THE NOZZLE TEMPERATURE

Increase the nozzle temperature to 240 degrees. We’re using ABS, but if using Nylon check the melting point temperature on the packaging. Leave it at this temperature for 5 minutes without pushing the filament through.

4\) ATOMIC PULL PART IV – PUSH THE FILAMENT THROUGH

Slowly apply pressure to the filament until it starts to come out of the nozzle. Pull it back slightly and push it back through again until it starts to flow from the nozzle.

5\) ATOMIC PULL PART V – REDUCE THE NOZZLE TEMPERATURE

Reduce the temperature to 180 degrees for ABS or 140 degrees for Nylon (you’ll need to experiment a little for your filament). Leave the printer at this temperature for 5 minutes.

6\) ATOMIC PULL PART VI – EXTRACT THE FILAMENT

Pull out the filament from the head. When you look at the end you should see some black carbonized material at the end. Repeat the process until clean. If the filament won’t pull from the nozzle, increase the hot end temperature slightly.



# 4\. Print Head Misses the Bed

There’s really no missing this one. At its most severe the noise will instantly alert you that something is very wrong. When the printhead misses the bed it will usually also have reached the limit of either the X or Y position. As the head tries to travel beyond its furthest point noise will be generated through slipping belts, grinding cogs, or the head simply trying to rip through the side of the printer. It’s very unlikely that your printer will succeed in producing a print in this state. And while it’s easy to fix, it’s not a problem that can be overlooked or dealt with at a later time.

Cause

Misconfiguration, wrong printer selection, or worn-out or broken end stops are all common issues. If the problem starts with a new printer then the likelihood is that something is amiss with the printer’s configuration. Run through the setup process again and ensure that you have the correct firmware version for your printer. Accidentally selecting the wrong printer from a dropdown list in your slicer program can be a common cause for this 3D printing problem. For example, trying to print using Ultimaker Go using print files configured for the Ultimaker 2. When you set up your printer ensure that you have specified the correct print volume, again either in the printer’s firmware or through software. If the printer thinks it has a bigger print platform than it has then it’s going to try to use it, even if it’s not there. If your printer is usually fine and then the problem occurs suddenly, start by double-checking your print preparation software. Something may have reset or been altered by an update! It’s not unusual for software to either revert to the default settings or to automatically select the latest printer version, even if that’s not the one you’re using. And if all else looks fine then it could be that one of your end stops in the printer has stopped working.



## 1\) CHECK SLICER FOR CORRECT PRINTER

Before trying anything else make sure that you have the correct printer selected in your printing software. All printers are different so even if the print beds of two printers are the same it’s highly unlikely the other dimensions and settings will match exactly.



## 2\) UPDATE FIRMWARE

If you’ve just purchased the printer and this issue is happening make sure you have the latest version of the firmware installed. Once updated run through the setup process and double-check all settings, especially around the size of the print area are correct.



## 3\) CHECK END STOPS

This will take a little more effort to diagnose. Watch the print head move. If it tries to push past the furthest point of one of its axes, check that an end stop hasn’t disconnected. If all looks fine (and none of the above steps fixed the issue for you) then replacing the end stops with new ones should be your next step.



# 5\. Snapped Filament

The filament spool still looks full, and when you check there appears to be filament in the feed tube, but nothing’s coming out of the nozzle. This is more of an issue with Bowden feed printers than direct feed as the filament is hidden so breakages aren’t always immediately obvious.

Cause

Caused by a number of issues but primarily old or cheap filament. Although the majority of filaments such as PLA and ABS do last a long time, if they’re kept in the wrong conditions such as in direct sunlight then they can become brittle. Then once fed into the printer no amount of adjustment is going to help. Another issue is filament diameter, and this can vary through manufacturer and batch. Sometimes if the idler tensioner is too tight then some filament that still has a good amount of life left in it can snap under the pressure.



## 1\) REMOVE THE FILAMENT

The first thing to do is to remove the filament from the printer in the usual way. In the case of the Ultimaker select Maintenance and Change Material. As the filament will usually have snapped inside the tube you’ll need to remove the tube from both the extruder and hot end. Then heat the nozzle and pull out the filament.



## 2\) TRY ANOTHER FILAMENT

If after reloading the filament it happens again, use another filament to check to see if it’s not just the old brittle filament that should be disposed of.



## 3\) LOOSEN THE IDLER TENSION

If the new filament snaps check that the idler tensioner isn’t too tight by loosening all the way. As the print starts, tighten until there is no slippage of the filament.



## 4\) CHECK THE NOZZLE

Check the nozzle isn’t blocked and give it a good clean.



## 5\) CHECK FLOW RATE AND TEMPERATURE

If the problem continues check that the hot end is getting hot and to the correct temperature. Also, check that the flow rate of the filament is at 100% and not higher.



# 6\. Stripped Filament

Stripped or slipping filament can happen at any point of the print process, and with any filament. The result is that no filament is extruded from the hot end bringing your print to an abrupt end.

Cause

Blockage, loose idler tensioner, wrong hot end temperature, these are just a few of the common causes, but all are usually easy to correct. The result of the problem is that the knurled nut or toothed gear in the extruder is unable to pull or push the filament through the printer. As the motor spins the small teeth on the gear that would usually grip and feed the filament through the system, instead wear it away until there is no longer any grip, and the gear and filament slip.



## 1\) HELP FEED THE SYSTEM

If the filament has just started to slip, you can usually tell by the noise and the appearance of plastic shavings, then apply some gentle pressure to the filament to help it through the system. This will often help to get the machine to print smoothly again.



## 2\) ADJUST THE IDLER TENSION

Start by loosing the idler, feed in the filament and tighten until it stops slipping. Filaments vary in diameter so although the idler will absorb some difference in diameter some filaments will require fine adjustment.



## 3\) REMOVE THE FILAMENT

In most cases you’ll need to remove and replace the filament and then feed it back through the system. Once the filament has been removed, cut the filament below the area that shows signs of slipping and then feed it back into the system. If the filament has snapped it may be past its usable best. Try it again and if it snaps again and you find the filament appears brittle discard and use another filament.



## 4\) CHECK THE HOT END TEMPERATURE

If you have just inserted a new filament as the issue started, double-check that you have the right temperature.



# 7\. Extrusion Stopped Mid-Print

Sometimes, for any of a number of reasons, the hot end will stop extruding molten filament.

Cause

Typically this 3D printing problem is attributable to two parts of the printing process — either something is wrong with your filament supply, or there’s a problem with the hot end/nozzle itself. It could be as simple a case as your filament has run out. Some printers obscure the spool, so you never know! Or it could be too tight of an idler on your extruder resulting in stripped filament that isn’t being fed into the hot end. Alternatively, you could have a blockage in your hot end, preventing any further filament from being extruded.



## 1\) CHECK YOU HAVE ENOUGH FILAMENT

A little obvious, but even the best of us have momentary lapses in concentration. Many slicers now give a material estimation for your prints, and judging that against the weight of your spool of filament and how much is left on it can give you a feeling for if there’s enough filament to complete your print.



## 2\) CHECK FOR STRIPPED FILAMENT

Stripped filament can be responsible for a print failing mid-way through, and can be caused by a myriad of issues. Check out our dedicated 3D printing troubleshooting tip on how to deal with stripped filament.



## 3\) CHECK FOR A CLOGGED NOZZLE

A nozzle caked in old burnt filament can cause a few different print issues, one of which is blocking any new extrusions from being laid down. Check out our dedicated 3D printing troubleshooting tip on how to deal with a clogged nozzle.



## 4\) CHECK FOR SNAPPED FILAMENT

An issue that mainly affects Bowden-style extruder setups, snapped filament can cause a disjoin between the extruder and hot end. Thankfully, it’s easy to diagnose and fix, but it may be a sign that your filament is past its best. Check out our dedicated 3D printing troubleshooting tip on how to deal with snapped filament.



# 8\. Print Doesn't Stick to Print Bed

Losing a print due to it not sticking to the print platform is a common issue and one that’s usually relatively easy to resolve. Unfortunately, a 3D print can break free at almost any time, from the first layer through to the last, which is especially infuriating. Of course, it’s not always the printer’s fault and if you’ve tried to print a model that only has a small amount of contact with the platform then undoubtedly that’s going to be the issue. Imagine you’re trying to print a plane and the only contact the model has with the print platform is the wheels. It’s therefore unlikely to print without some type of build plate adhesion and brim, and that’s before you even start to look at supports.

Cause

The most common cause is simply that the print just doesn’t bond to the surface of the print platform. The filament needs a textured base in order to adhere, so to solve the issue you’ll need to create a better bonding surface. An unlevel print platform can be another major issue. If the platform is uneven then for some parts of the print the nozzle won’t be close enough to the platform to correctly extrude and bond the first layer. Calibration can also be a major issue, over time the distance between the nozzle and platform can increase to the point where the initial layer is dragged rather than pushed into the print platform. In all of these cases you’re likely to see a spaghetti of filament appear above your half-formed model, just filament spaghetti or parts of your model dotted around the print platform.



## 1\) ADD TEXTURE

To increase the chances that filament will bond to the platform you need to add another material to add texture. The most common solution is to apply a thin layer of stick glue to the print platform, which can then be easily washed away with hot water. Another alternative for PLA is to add decorator’s tape. For filaments that require a heated platform of 40º and above, there is a variety of special tapes now available that are a little more heat resistant.



## 2)LEVEL THE PRINT BED

Every printer has a different process for print platform leveling, some like the latest Prusa models utilize an extremely reliable auto leveling system, others such as the Ultimaker have a handy step-by-step approach that guides you through the adjustment process. Refer to your printer’s manual for how to level your print bed.



## 3\) ADJUST THE NOZZLE HEIGHT

If the nozzle is too high then the filament won’t stick to the platform, too low and the nozzle will actually start to scrape the print off. Find the Z-axis offset option in your printer’s settings and make small adjustments — into the positive to raise the nozzle away from the bed, and negative to lower it closer.



## 4\) CLEAN THE PRINT PLATFORM

If you’re printing on a material such as glass, every so often it’s a good idea to give it a good clean, especially if you frequently apply glue. The grease from your fingerprints and the excessive build up of glue deposits can all contribute to the non-stickiness of the print platform.



## 5\) APPLY BUILD PLATE ADHESION

Some models will print fine without a brim, but smaller items and those with only a small footprint in contact with the platform will require some type of Build Plate Adhesion. These can be added in your slicer software- — look for “Brim” and “Raft”. Brim will add a single layer of a specified number of perimeter lines radiating out from where your print makes contact with the print bed; it’s the least wasteful of the two, and in our experience is the better option, provided you don’t mind taking a knife to your print to trim the brim away. Raft adds just that to your print. Depending on the parameters you specify, you will get a shadow of your print’s footprint, printed in a thicker, better-adhering layer. Your print is then printed as usual on top of this. Rafts tend to create a rough, unpleasant surface where it touches your print, and use up more material than a brim. The benefit of a raft though lies in being able to simply snap the part off.



## 6\) ADD SUPPORTS

As well as adding build plate adhesion, if your model has complex overhangs or extremities be sure to add supports to hold the print together during the process.



# 9\. Supports Fell Apart

Printing complex models will require a support or two, and whilst supports can be a pain to remove, they’re unfortunately an essential part of modeling. The job of support is simple, it supports, but occasionally they fail, leaving your model unsupported. You’ll notice that as your print is extruded parts of the support structure will look uneven, cracks may appear or they’ll just start to look stingy. Not only are the supports failing but the additional filament is ruining your model rather than ensuring it prints correctly.

Cause

Support structures are complex things and most slicer applications will provide you with several options. It’s all too easy to stick with the default settings, but this doesn’t guarantee success with your 3D printed overhangs. An important consideration is the type of support that will keep your model steady and supported throughout the print. Lines and zig zags are generally easy to remove after the print has finished, but offer less rigidity during the print process. Triangles and grids offer more support but can be a pain to remove. Take a simple bridge structure with thin uprights and then think about the supports. They will have a great deal of work to do keeping the model rigid, if you’ve opted for lines or zig zags then the likelihood is the model will move during the print process, breaking the delicate supports as it goes.



## 1\) SELECT THE CORRECT SUPPORTS

Look at the type of model you’re about to print. If there are large overhangs that connect sections of the model and these have good contact with the platform, try using lines or zig zag supports. If the model has less bed contact or needs much stronger supports, use grid or triangle supports.



## 2\) ADD PLATFORM ADHESION

Make sure you have added some type of platform adhesion, such as a brim, so that the mounts have plenty of foundation to bond to.



## 3\) INCREASE THE SUPPORT DENSITY

Try this as a last resort. Increasing the support density will offer your model a denser structure to rest on and will be less affected by any model movement, but will be much tougher to remove.



## 4\) CREATE IN-MODEL SUPPORTS

Supports that are overly tall can be susceptible to weakness. By adding a tall block as part of your print that ends just below where the supports are required, the supports are given a solid base without the need to print tall and weak.



## 5\) CHANGE FILAMENT

Filament can become brittle as it reaches the end of its usable life span, and this usually shows in the quality of the supports. Swap the filament for a fresh reel and see if the problem improves



## 6\) CHECK EVERYTHING IS TIGHT

Printer shakes and wobble can be a real issue. Give your machine the once over and make sure that everything is tight and re-calibrate if needed.



# 10\. First Layer is Messy

The first layers of a print can often prove problematic. It could be that the print simply does not stick (which we covered with a different 3D printing troubleshooting tip, up top), or you’re finding unwanted lines that cause the bottom shell to have an unexpected look. Additionally, it’s entirely possible for any fine detail on the bottom of your print to congeal into a blur with little semblance of any surface design.

Cause

These 3D printing problems are typical signs that the print bed hasn’t been leveled properly. If the nozzle is too far away from the bed, the bottom surface often shows unwanted lines, and/or the first layer does not stick. If the nozzle is too close, blobs may be the result. Where you find detail is becoming undefined and blurry, the chances are your print bed temperature is a little too high.



## 1\) LEVEL THE PRINT BED

Every printer has a different process for print platform leveling. The latest Prusa models feature an extremely reliable auto leveling system, while others such as Ultimaker have a handy step-by-step approach that guides you through the adjustment process.



## 2\) LOWER BED TEMPERATURE

Try knocking the bed temperature down by 5 °C increments, until you hit that sweet spot of adhesion, without loss of detail.



# 11\. Print Bows Out at Bottom (Elephant's Foot)

The base of the model is slightly bulging outwards, an effect otherwise known as “elephant foot”.

Cause

This ungainly print defect can be caused by the weight of the rest of the model pressing down on the lower before they have properly cooled back into a solid – this is particularly an issue when your printer has a heated bed.



## 1\) BALANCE BED TEMP \& COOLING

To stop elephant foot from appearing in your 3D prints the base layers of the model need to be cooled sufficiently so that they can support the structure above. Apply too much cooling however, and you risk the base layers warping. Getting the balance right can be tricky, start by lowering the temperature of the print platform by intervals of 5 degrees, (to within +/- 20 degrees of the recommended temperature). If your Bottom / Top Thickness is set to 0.6mm then start the fan at a slightly lower height.



## 2\) LEVEL PRINT BED

More often than not the majority of print issues can be traced back to the level of the print platform. Each printer has a slightly different technique for print platform leveling. Start by calibrating yours according to your printer manufacturer’s recommended procedure. Try printing a calibration cube and watch how the printer lays the filament on the bed. From printing the cube you should easily be able to see if your bed is level from how evenly (or not) your layers are on the bed. Similarly, you will be able to see if the nozzle is too close to the print platform and scraping through the molten filament, or too high and causing the filament to build up and blob.



## 3\) RAISE THE NOZZLE

Just raising the height of the nozzle slightly can often help, but be careful too high and it won’t stick to the platform.



## 4\) CHAMFER THE BASE

Another option is to chamfer the base of your model. Of course, this is only possible if you have either designed the model yourself or you have access to the original file. Start with a 5mm and 45º chamfer, but experiment a little to get the best result.



# 12\. Print Edges are Bending (Warping)

At the base of the model, the print bends upwards until it’s no longer level with the print platform. This can also result in horizontal cracks in upper parts and cause your print to come unstuck from the print bed.

Cause

Warping is common as it’s caused by the natural characteristics of plastics. As the ABS or PLA filament cools it starts to contract very slightly; the problem of warping arises if the plastic is cooled too quickly.



## 1\) USE A HEATED PRINT PLATFORM

The easiest solution is to use a heated print platform and set the temperature to a point just below the plastics melting point. This is called the “glass transition temperature”. If you get that temperature right then the first layer will stay flat on the print platform. The print platform temperature is often set by the slicer software. You’ll normally find the recommended temperature for your filament printed on the side of the packaging or on the spool.



## 2\) APPLY AN ADHESIVE TO THE PRINT BED

If you still find your print lifting at the edges then apply a tiny amount of stick glue evenly on the bed to increase adhesion.



## 3\) TRY A DIFFERENT PLATFORM TYPE

Change your print bed to one that offers better adhesion. Manufacturers such as Prusa use a PEI (Polyetherimide) print surface that offers excellent adhesion without glue. XYZPrinting supply textured tape in the box with some of their printers, basically a large sheet of masking tape, and again adding this works excellently, although only with nonheated print platforms. Zortrax 3D printers have a perforated print bed, models weld themselves to this surface eliminating the issue completely.



## 4\) LEVEL THE PRINT PLATFORM

Print platform calibration can be another cause, run through the calibration process to check that the bed is level and nozzle height is correct.



## 5\) INCREASE CONTACT

Increasing the contact between the model and bed is an easy fix and most print software has the option to add rafts or platforms.



## 6\) ADJUST ADVANCED TEMPERATURE SETTINGS

If all else fails then you’ll need to take a look at your advanced print settings both on your printer and in your printer software. Try increasing the print bed temperature by increments of 5 degrees. In the slicer software take a look at the fan cooling, this is usually set so the cooling fans switch to full power at a height of around 0.5mm, try extending this to 0.75 to give the base layers a little more time to cool naturally. Even if your printer has a heated print platform, it’s always recommended that you use glue and regularly calibrate the bed level.



# 13\. Infill Looks Messy and Incomplete

The internal structure of your print is missing or broken.

Cause

There are a number of reasons for the misprinting of the internal structure. The most common is incorrect settings within the slicing software, but it can also be due to a slightly blocked nozzle.



## 1\) CHECK THE FILL DENSITY

In your slicing software check the infill density. A value of around 20% is normal; any less than this and you’re likely to have issues. For larger prints, you may want to increase this to ensure that the model has enough support.



## 2\) DECREASE INFILL SPEED

The speed at which the infill is printed can have a major effect on the quality of the structure. If the infill is looking weak then decrease the infill print speed.



## 3\) CHANGE THE INFILL PATTERN

Most slicing software enables you to change the internal structure. You can have a grid pattern, triangle, honeycomb, and more. Try selecting a different option.



## 4\) CHECK YOUR NOZZLE

It might be that there is a slight blockage in the nozzle. While the blockage doesn’t affect the printing of the thicker exterior walls, because there is less flow for the internal structure the filament is getting caught.



# 14\. Gaps Between Infill and Outer Wall

When you look at the top or bottom of the print, you can see a slight gap between the infill and the outer perimeter walls.

Cause

Gaps between the perimeter and top layers used to be a common problem, but as printer accuracy has improved and the support for different materials extends, it’s now less of an issue than it was. However the new wave of advanced materials is far less forgiving than the likes of PLA and ABS, and we’re starting to see a slight resurgence of the problem. Gaps are caused by the filament used for the infill and outer walls not quite meeting and bonding. Handily, it’s one of the easiest things on this list to fix. The most obvious cause of the problem is that the infill overlap is not set, or it’s set to zero. This means that the slicing software is actually telling the printer not to allow the two parts of the print to meet. Another issue could be the order in which you have set the infill and outer walls to be printed. If you’re printing the perimeter first, then there is generally little or no overlap which can again cause the problem.



## 1\) CHECK THE INFILL OVERLAP

This is by far the most common issue and is really easy to resolve. In your slicing software locate the ‘Infill Overlap’ option and increase the value.

● In Cura, this is set to 15% by default. Raise it to 30%.

● In Simplify3D you’ll find the option in ‘Edit Process Settings > Infill > Outline Overlap’. Again increase the value. This setting is directly linked to the extrusion width, so the % value will be a % of whatever you’re extrusion width is. When adjusting this setting always keep it below 50% or you’ll start to see the effects of the overlap in the outer perimeters of your print.



## 2\) PRINT INFILL BEFORE THE PERIMETER SHELL

If you’re printing with a relatively thin outer wall the structure of the infill can show through. If this happens then you can switch the order by which the printer lays down the infill and perimeter layers. For example, in Cura check to see if you have ‘Infill prints after perimeters’ ticked.



## 3\) INCREASE HOT END TEMPERATURE

Some of the latest advanced materials such as XT-CF20 are a little less forgiving when it comes to spreading due to the carbon fibers that make up part of their structure. When printing with these materials you may find that a slight 5-10º increase in hot end temperature makes all the difference.



## 4\) LOWER PRINT SPEED

Okay, so you may be in a rush to get the printout, but printing at higher speeds can cause all sorts of issues if the printer isn’t perfectly calibrated. If you need to print quickly you can still avoid gaps by decreasing the speed of the top layer.



# 15\. Infill is Visible from the Outside

The final print looks fine but an outline of the internal support structure can be seen through the walls of the print. This is also often referred to as ghosting.

Cause

The issue with ghosting happens due to the infill encroaching into the path of the perimeter. This effect is most visible when your print has thin walls. The problem is caused by the infill structure overlapping with the perimeter line as it’s being laid down. Although this ghosting is an issue it’s actually an important part of the printing process, as it helps the internal structure bond effectively to the external walls. Luckily it’s very easy to overcome. Another cause of ghosting can be that you have set an incorrect wall thickness in relation to the nozzle size that you’re using. In normal printing conditions, wall thickness should be directly related to the nozzle size, so if you have a 0.4mm nozzle the wall thickness should be a multiple of this: 0.4, 0.8, 1.2, and so forth.



## 1\) CHECK THE SHELL THICKNESS

Make sure that the value you have selected for the shell thickness is a multiple of the nozzle size.



## 2\) INCREASE THE SHELL THICKNESS

The easiest solution is to increase the shell thickness. By doubling the size it should cover any overlap caused by the infill.



## 3\)  USE INFILL AFTER PERIMETERS

Most slicing software will enable you to activate Infill prints after perimeters.

● In Cura open up the ‘Expert Settings’ and under the Infill section tick the box next to ‘Infill prints after perimeters’

● In Simply3D Click ‘Edit Process Settings’ then select ‘Layer’ and under ‘Layer Settings’ select ‘Outside-in’ next to the ‘Outline Direction’.



## 4\) CHECK PRINT PLATFORM

Check around the model and if you see that the effect is more prevalent on one side than the other, the effect could be due to calibration. If so run through the usual calibration process.



## 5\) PRINT SHELLS TO YOUR ADVANTAGE

Depending on the type of model that you’re printing you can use the internal and shell printing order to your advantage. When you want a high-quality print with a good surface finish where the actual strength of the model isn’t important, select print from the Outside-in. If however the strength of the print is paramount then select Print from Inside-Out and double the wall thickness. The reason for the difference in strength is that when you print from the Outside-in you eliminate the small amount of overlap that causes the ghosting issue, but this also means that the actual structure won’t create the same bonding strength between the internal and external structure due to the lack of overlap.



# 16\. Cracks Have Appeared in Tall Objects

There are cracks on the sides, especially on taller models. This can be one of the most surprising issues in 3D printing as it tends to manifest itself in larger prints and usually happens while you’re not looking.

Cause

In a print’s higher layers, the material cools faster. The heat from the heated print bed doesn’t reach that high, and because of this, adhesion in the upper layers is lower.



## 1\) EXTRUDER TEMPERATURE

Start by increasing the extruder temperature; a good start would be to increase it by 10ºC. On the side of your filament box you’ll see the working hot end temperatures, try to keep the temperature adjustment within these values.



## 2\) FAN DIRECTION AND SPEED

Double-check your fans and make sure that they’re on and aimed at the model. If they are, try reducing their speed.



# 17\. Layers Don't Line Up Well

As the print is forming, there appear to be a few issues with the quality. Look closer and you see that the layers aren’t aligning quite as they should. Look at the internal support structure and again the pattern looks slightly out. The outer wall, rather than being smooth, features slight misalignments that cause an uneven face. It’s highly likely that the issue only affects the print in one direction; front to back or left to right.

Cause

Over time the parts of your 3D printer — such as nuts, bolts, and belts — will become loose and require a tightening. The effect of misaligned layers is similar to the cause of the more pronounced effects of shifting layers and there is no doubt that there is a crossover. If left unchecked, this problem will eventually result in shifting layers, but as the issue starts the visual effect on the prints is far less pronounced and can look very different. The cause is usually linked directly to a loose belt.



## 1\) CHECK THE BELTS PART I

Start by checking each of the belts is tight but not overly tight. You should feel a little resistance from the two belts as you pinch them together. If you find that the top section of the belt is tighter than the bottom then this is a sure-fire sign that they need a tweak and tighten. Some printers, such as the Original Prusa i3, come with belt tensioners built into them. Others can be retrofitted with 3D printed ones. If neither of these is an option for you, you may have to get your hands dirty and manually tighten the belt.



## 2\) CHECK THE BELTS PART II

The printer belts are normally just one continuous loop hooked around two pulleys. A common issue is that over time the belt can slip on one pulley and gradually gets tighter on the top compared to the bottom — or visa versa — and again this can cause misaligned layers.



## 3\) CHECK THE RODS ARE CLEAN AND OILED

Over time debris can build up on the rods, causing odd patches of higher friction which in turn can affect the free movement of the head and again cause layer shifting. A quick wipe and re-oil of the rods usually solves the issue.



## 4\) CHECK FOR BENT OR MISALIGNED RODS PART I

If you see the print head falter at certain points then it could be that one of the rods has become slightly bent. You can usually tell by switching off the machine so there’s no power going through the steppers and then moving the print head through the X- and Y-axis. If you feel resistance then you know something is amiss. Start by seeing if the rods are aligned. If they are, remove them and roll them on a flat surface. If any are bent then it will be quite obvious.



## 5\) CHECK FOR BENT OR MISALIGNED RODS PART II

Many printers use threaded rods rather than lead screws and although these do the job, they do have a tendency to bend over time. Don’t worry about dismantling your printer to see if they’re straight, simply use control software such as ‘Printrun’ to move the print head up or down. If one of the Z-axis rods is bent you’ll instantly see. Unfortunately, it’s almost impossible to accurately straighten a rod once it’s bent, but on the upside, it’s a good excuse to replace the old threaded rods for lead screws.



## 6\) CHECK THE DRIVE PULLEYS

These are usually connected directly to a stepper motor or to one of the main rods that drive the print head. If you carefully rotate the pulley you’ll see a small grub screw. Holding both the rod and the attached belt, give the belt a tug to force the pulley to turn. You should find that there is no slip between the pulley and stepper or rod. If there is tighten the grub screw and try again.



# 18\. Some Layers are Missing

There are gaps in the model because some layers have been skipped (in part or completely).

Cause

The printer failed to provide the amount of plastic required for printing the skipped layers. For infrequent skipped layers, this can be referred to as temporary under-extrusion. There may have been a problem with the filament (e.g. diameter variation), the filament spool, the feeder wheel, or a clogged nozzle. Alternatively, friction has caused the bed to temporarily get stuck. The cause may be that the vertical rods are not perfectly aligned with the linear bearings. It’s also possible that there is a problem with one of the Z-axis rods or bearings. The rod could be distorted, dirty or suffering from excessive oil.



## 1\) MECHANICAL CHECK

It’s good practice to give your 3D Printer the once-over every now and again and the appearance of gaps in your 3D print is always a good sign that now is the time to give your 3D printer some love and attention. Start off by checking the rods and make sure that they’re all seated into either bearings or clips and haven’t popped out, shifted or moved even slightly.



## 2\) ROD ALIGNMENT CHECK

Make sure that all rods are still in perfect alignment and haven’t shifted. You can often tell by switching off the power (or disabling steppers) and then gently moving the print head through the X and Y-axis. If there is any resistance to the movement then something is wrong and it’s usually pretty easy to tell if this is due to misalignment, a slightly bent rod or problem with one of the bearings.



## 3\) WORN BEARING

When bearings go they usually let you know about it by creating an audible din. You should also be able to feel uneven motion in the print head and when printing the machine looks like it’s vibrating slightly. If this is the case unplug the power and move the print head through the X and Y to locate the region of the broken bearing.



## 4\) CHECK FOR OIL

Lubricating the joints is easy to forget, but keeping everything well-oiled is essential to the smooth running of the machine. Sewing machine oil is ideal and can be purchased from almost any haberdashery at a relatively inexpensive price. Before you go applying liberally just check that the rods are clean and free of dirt and printing debris — a quick wipe of the rods before applying a fresh coat of oil is always a good idea. When all rods look clean just dab on a little, but not too much. Then use printer control software such as Printrun to move the head through the X and Y axis to make sure that the rods are evenly covered and moving smoothly. If you add a little too much oil don’t worry just wipe some off with a lint-free cloth.



## 5\) UNDER-EXTRUSION

The final issue could be under-extrusion. Check out our dedicated 3D printing troubleshooting tip for under-extrusion here.



# 19\. Print Leans When it Shouldn't

As the print forms it starts to lean. Instead of being straight and true, vertical edges are printed at an angle, and this angle isn’t consistent throughout the print. The severity could be increasing and decreasing at different stages.

Cause

The cause of the issue is generally very simple; one of the pulleys attached to a stepper motor is slightly loose, or one of the belts is rubbing against something and stopping the full travel of the head. All you need to do to correct the issue is to make sure that none of the pulleys are slipping and the grub screws that hold the pulleys in place are all tightened. Although this should be a quick and straightforward fix, one issue you may experience as you go to tighten the pulleys is that the small grub screws that tighten onto the shaft of the motor aren’t always that easy to access. Firstly diagnosing which pulley is causing the issue and then getting access to that pulley can be tricky and time-consuming.



## 1\) CHECK X- AND Y-AXIS

If your print is leaning to the left or right then you have an X-axis issue. Back to front and you have a Y-axis problem. Once you’ve diagnosed which it is you can then check the belts and pulleys. If you have a printer such as the Prusa i3 then the process is pretty straight forward, as the steppers are directly connected to the main drive belt. For the Ultimaker and other printers, the process can be a little more tricky.



## 2\) CHECK THE BELTS AREN’T RUBBING

Look around each of the belts and ensure that they’re not rubbing against the side of the machine or any other components. Also, check to see that the alignment of the belts is correct. If one is at a slight angle then this can cause issues.



## 3\) TIGHTEN THE STEPPER MOTOR COUPLER GRUB SCREW

Once you diagnose which axis is causing the issue, use an Allen key to tighten the corresponding coupler’s grub screw that attaches to the stepper motor.



## 4\) CHECK ROD PULLEYS

More complex machines such as the Ultimaker 2 have a series of belts and pulleys. The main X and Y rods at the top of the machine feature eight pulleys. Go around each of these on the affected axis and tighten the grub screws for each. It’s unlikely that these will cause any slip but if one is loose then a belt may misalign.



# 20\. Overhangs are Messy

You load your print into your slicing software and everything looks good. Hit print and you find that some parts of the model print absolutely fine, whilst other parts end up as a stringy mess. OK this might seem obvious and the issue of overhangs is often seen as a 3D printing rookie mistake. But it’s surprising just how often even experienced 3D printers are hit with an overhang issue.

Cause

The process of FFF requires that each layer is built upon another. It therefore should be obvious that if your model has a section of the print that has nothing below, then the filament will be extruded into thin air and will just end up as a stringy mess rather than an integral part of the print. Really the slicer software should highlight that this will happen. But most slicer software will just let us go ahead and print without highlighting that the model requires some type of support structure.



## 1\) ADD SUPPORTS

The quickest and simplest solution is to add supports. Most slicing software will enable you to do this quickly. In Simplify3D click Edit Process Settings > Support > Generate support material; you can the adjust the amount, pattern and settings. In Cura just select the desired support type from the Basic settings.



## 2\) CREATE IN-MODEL SUPPORTS

Supports generated by software can sometimes be intrusive and result in support material getting stuck in impossible to remove places. Creating your own in your modeling application is a good alternative. It takes a bit more skill but can enable some fantastic results.



## 3\) CREATE A SUPPORT PLATFORM

When printing a figure, arms and other extrusions are the most common areas that cause problems. Using supports from the print bed can also cause issues as they often have to span quite large vertical distances; for structures that are supposed to be easily removed and fragile, this distance is prime for causing problems. Creating a solid block or wall under arms etc and then creating a smaller support between the arm and block can be a great solution.



## 4\) ANGLE THE WALLS

If you have a shelf style overhang then an easy solution is to slope the wall at 45º so that the wall actually supports itself and removes the need for any other type of support.



## 5\) BREAK THE PART APART

Another way to look at the model is to break it apart into separate prints. With some models this enables you to flip what would be an overhang and instead make it a base. The only issue with this is that you then have to find a way of sticking the two parts back together.



# 21\. Surface Areas Beneath Supports are Rough

You’ve printed a complex model with supports created with your chosen software. But when it comes to removing the structure, small remnants of material are left on the surface. When you try to sand or remove the remaining material, it ruins the overall effect of the model.

Cause

Supports are an essential part of 3D modelling and a subject that can divide opinion. Many models can actually avoid the need for supports completely with a little adjustment of the model to angle verticals, or with the addition of design integral support structures to the model. You may also be surprised by the full capabilities of your printer, with most being able to bridge 50 mm gaps and print angles of 50º without any support at all. Software solutions such as Cura and Simplify3D are capable of producing outstanding support structures, and for the most part these automatically generated supports will far exceed the quality of any home grown solution. But although auto-generated supports do the job, they can be difficult to remove. Applying your own support structures is a neater solution, but you’ll need to delve into the settings of your software to tailor the supports to your models. Depending on your slicing software, enabling supports will require the activation of a checkbox. There are plenty of associated options that enable you to fine tune the support structure, and minimize the effect that the structures will have on the surface of your models. However, as careful as you are with the support settings, the supports themselves will be bonded to your model, so will always leave some sort of trace mark. The issue of surface finish when supports are used is a big one and the severity of the effect will change depending on the material types you use. A more brittle filament such as PLA is often harder to work and finish than a decent ABS.



## 1\) CHECK SUPPORT PLACEMENT

Most slicing software will allow you choose whether your support structure is touching the build plate or “everywhere”. For most models “Touching the Build Plate” is sufficient. Choosing Everywhere will result in supports… well, everywhere. Which then means, in the context of this 3D printing troubleshooting tip, a rough surface finish all over your print.



## 2\) CHECK THE CAPABILITY OF YOUR PRINTER

Quite often people use supports without realizing that their printer can bridge gaps and print relatively steep angles with ease. Most printers are capable of bridging gaps of 50 mm and printing angles of 50º without error. Create or download a test print to familiarize yourself with the true capability of your printer.



## 3\) ADJUST THE SUPPORT PATTERN

Depending on the model type, a change in the support pattern could be all it takes for a better support-model interface; try switching from “Grid” to “Zig Zag”.



## 4\) REDUCE SUPPORT DENSITY

In your slicer software switch the view to “Layers” and take a look through the support structure. Default software will usually apply a dense support structure. If you reduce this density the support will become weaker, but as long as your printer is finely tuned this shouldn’t be an issue. In Cura a support density of 5 can be used successfully and vastly reduces the effect of the structure on the model’s surface.



## 5\) REDUCE PRINT TEMPERATURE

Double-check the filament temperature range and adjust the hot end temperature to the minimum for the material. This may result in a weaker bond between the layers, but will also make it easier to remove the support structure.



## 6\) DUAL EXTRUSION \& SOLUBLE SUPPORT MATERIALS

An expensive solution, but if the majority of your prints use complex support structures then a dual extrusion printer such as the Ultimaker 3 or the Cel RoboxDual is really the only way to go. Water soluble support materials such as PVA have come into their own, and provide a convenient way to achieve complex prints without completely sacrificing surface finish. Best of all, you can add supports to cavities that previously would have been impossible to remove standard print material supports from, meaning more complex prints are also within your grasp.



# 22\. Print is Unusually Weak/Looks Wrong (Non-Manifold Edges)

Parts of your print are missing or the final print is weak and falls apart despite the exterior quality of the print looking fine. Sections of the print look completely different from the print preview or the final print has geometry errors that make no sense.

Cause

Non-manifold edges are a common cause of misshapen or odd prints. Non-manifold edges are the edges of models that can only exist in the 3D space and not the physical world. For example, if you have two cubes in the real world and try to overlap them directly, it’s physically impossible as the solid outer walls prevent the two objects from intersecting. In the 3D world you can simply intersect the two, they still exist as individual objects, but the software we use distinguishes between them regardless of the perceived oneness as we look at them. In order to get the two to print correctly, the objects need to be merged so that any inner walls are removed and an object with a single undivided inner cavity is left. Another common cause is if you have an object such as a cube and delete one of the surfaces. You essentially have an object with a hole, it might look like a shape with five sides, but it only exists in the virtual 3D space, this is geometry with no physical form. Although you can see the outer walls in the software, the walls that meet the hole only have dimensions on two axes. The third dimension which we see as the thickness of the wall is only illustrative and has no real physical dimension. When it comes to slicing the model the software does its best and in many cases will repair the hole. However, in more complex models, the effects can be interesting to say the least.



## 1\) USE LATEST SLICER SOFTWARE

Most of the latest slicer engines all support the automatic fixing of non-manifold edges but it’s still good practice to ensure that your models are correctly formed and print ready.



## 2\) FIX USING STL FILE REPAIR SOFTWARE

If you’re already using the latest slicer software then you might have noticed a notification telling you that your STL file features some non-manifold edges. Some software can fix this for you of course, and if you’re slicer can’t then there’s a good selection of STL file repair software that can be used on both desktop and the web. It’s a simple and easy task, just upload your file to your chosen software, let it identify any broken sections, then follow the instructions. If you didn’t get a notification on your slicer but your prints are coming out as a weird, messy blob this suggests you have some non-manifold edges in there. Try STL file repair software. It might not fix the problem, but it’s certainly something to try.



## 3\) FIX ‘NON-MANIFOLD’ IN SIMPLIFY3D

In edit ‘Process settings’ click the ‘Advanced’ tab and select ‘Heal’ next to ‘Non-manifold segments.



## 4\) USE THE LAYER VIEW

In your slicer software use the layer view to check through the model so you can see where the issues appear. A quick slide through the layers will often highlight an easy to fix problem.



## 5\) USE MODELING SOFTWARE TO FIX ISSUES

One of the easiest ways to fix models with non-manifold edges is to use software; Programs such as Blender and Meshmixer both have features built in that will quickly enable you to highlight problems with your models and fix them prior to slicing.



## 6\) MERGE OBJECTS

Really it’s better to fix your 3D models prior to importing them into your slicing software. To do this, make sure that when you have two objects that do intersect or overlap you choose the appropriate Boolean function to either intersect, merge or subtract.



# 23\. Fine Detail Not Printing Correctly

Your 3D printer is a finely tuned workhorse able to churn out prints one after another without issue. But then when it comes to a print with fine detail, your printer isn’t producing the results you expect. Edges and corners that are supposed to be pin sharp and crisp have a defined curve and softness, and intricate details are far from perfect.

Cause

There are a number of issues that can affect the quality of printing when it comes to fine detail. The most common cause of low detail prints is, of course, the layer height. If you have a low resolution (high layer height) set for your printer then you’re not going to be able to get silky smooth prints, regardless of how good your printer is. Nozzle size is another obvious issue. There’s a very delicate balance between nozzle size and fine print quality. In a production environment, a 0.5mm nozzle is ideal. For general purpose a 0.4mm, and fine detail 0.4mm or smaller. The smaller nozzle will also mean that your machine will need to be finely tuned as any issues will be amplified. Nozzle temperature is all important, as your printer needs to be able to extrude the plastic smoothly. When it comes to detail make sure your nozzle is clean prior to starting, even the slightest build up of filament or a small blockage will highlight in the print. Print speed will also have a huge effect on the detail; for detailed prints go as slow as you dare. You may have to adjust the fan speed to accommodate the increase in extrusion time. Some printers even benefit from the extruder fan being switched to its lowest setting (or even off). Filament brands spend a fortune fine tuning their formulas to create a smooth flowing and setting filament. Although cheaper brands might look the same, the tolerances of diameter chemical composition can vary and this inconsistency will again be highlighted in the final print. Finally check that the print platform is level. Even the slightest error in the level will have repercussions throughout the print when printing at high resolutions. Finding a good calibration print is an easy way of checking just how well your printer is tuned.



## 1\) INCREASE THE RESOLUTION

Increase the resolution — a tighter, lower layer height will give successful prints a smoother finish.



## 2\) NOZZLE DIAMETER

The smaller the nozzle diameter the higher detail you can print. But a small nozzle also means lower tolerances so your machine needs to be highly tuned.



## 3\) MAINTAIN YOUR PRINTER

Any additional friction from slightly misaligned rods or loose belts will be instantly apparent in your print. Ensure everything is tight and aligned.



## 4\) CLEAN YOUR NOZZLE

Before starting a detailed print make sure that your nozzle is clean



## 5\) SLOW IT DOWN

Reduce your print speed — a nice slow extrusion is less prone to error.



## 6\) USE QUALITY FILAMENT

Selecting the right material from a quality filament manufacturer is a key to good quality prints.



## 7\) CHECK PLATFORM LEVEL

Run through your printers calibration procedure to check that the platform is level.



# 24\. Ripples and "Echoes" in Print (Ringing)

The effect of visual waves or rippling on the print surface is one of those minor and annoying problems that many of us simply overlook. It has a habit of coming and going, and there really does seem to be no consistent reason for the issue. The effect is normally very subtle and appears as a wave or ripple through the surface of the print, it’s position and severity can also change. Most people will simply overlook the problem. Other than a slight visual effect on the surface the effect of these ripples has little other effect on the quality of the final 3D print, except of course in the most severe of cases.

Cause

The issue of waves in your 3D prints is usually down to one of two things, and more commonly a combination of the two. Vibrations and speed. 3D print manufacturers do an awful lot to their machines to make sure that the small vibrations created by the motors are kept to an absolute minimum. Lift up a printer like the Ultimaker 3 and you’ll see exactly what we mean, even the small Cel Robox Dual packs in some significant weight. This weight helps to minimize vibrations through the machine but doesn’t completely eliminate it. Those small vibrations can travel through the furniture, floor boards or any surface you’ve seen fit to adorn with your printer. The next time you start your 3D printer up take a look at the surface that it’s on, then as the printer prints check to see if the table is sturdy enough to properly support the machine. Vibrations can also be amplified by poor maintenance and worn linear bearings. Regularly check that your printer is clean, free of fluff, grit and dirt, and remember to keep the rails oiled. When the printer’s off check the quality of the linear bearings and make sure that the movement of the print head is smooth, you can do this by moving the head with your fingers. Make sure everything is cool before you start. As you’re checking the maintenance make sure that all the bolts and bits within the machine are good and tight, especially if you built the machine yourself. Waves will also be an issue if you try to print too fast, the simple solution here is to simply drop the print speed, this will solve the problem in the majority of cases. If you still need to print fast then try increasing the flow and extrusion temperature. Finally, and this is one for the more advanced users, and that’s firmware acceleration. This adjusts the speed of the head as it prints and changes direction, it’s function is to help prevent ringing. Here there are two functions that you should look at and this will change depending on the machine. Look for acceleration and jerk, there are several values listed, start by lowering the jerk and then the acceleration during printing.



## 1\) REDUCE VIBRATIONS

Make sure that the surface you use for your 3D printer is solid and as the printer prints there are no visual vibrations.



## 2\) CHECK THE BEARINGS

Linear bearings wear over time, with the printer off check that all are still running smooth.



## 3\) MAKE SURE EVERYTHING IS TIGHT

It’s amazing how one loose bolt can affect print quality, as part of your maintenance routine make sure everything is bolted and tight.



## 4\) ADD OIL

Check all the rods are clear of dust and dirt and then add a drop of oil to ensure everything is well lubricated.



## 5\) SLOW DOWN THE PRINT

Reduce the print speed.



## 6\) ADJUST THE FIRMWARE ACCELERATION

One for advanced users only, check the printer’s firmware and adjust the values in the code for the acceleration and jerk, you’ll then need to upload the firmware back to your machine.



# 25\. Diagonal Scars on Print

Horizontal lines appear across the top layer of your print, usually diagonally from one side to another.

Cause

A 3D print is created by laying down successive layers, one after the other. As each layer is set the print head moves through the X and Y axis. Once the layer is complete the head lifts through the Z-axis and returns to the start point to set down the next layer. It is at this point that visible lines or scaring can occur. These can be caused by a number of printer settings, but in essence, the problem is due to filament oozing or the nozzle physically scratching the surface. Combing is one of the major offenders. Combing confines the print head to the printed area of the model. If there is any excess filament, it oozes across the rest of the print. Alternatively, the head doesn’t lift high enough and the hot nozzle drags across the surface, leaving a scar. Over extrusion is another less common cause, as the head lifts excess drags across the surface leaving a trace of filament. On larger flat surfaces you may see the diagonal line fade across the surface. Too high a temperature is a less likely cause but with some cheaper or older filaments the residual heat of the nozzle can lead to filament oozing from the nozzle, again leaving a trail as the nozzle shifts.



## 1\) COMBING

Combing keeps the print head over the already printed areas of the model and therefore reduces the need for retractions. Whilst this increases print speeds it can cause the scaring. Switch combing off and in most cases, this will clear the problem but expect longer print times.



## 2\) RETRACTION

If you’ve switched off combing and the issue remains, try increasing the retraction amount. If the problem still persists then take a look at over-extrusion or the nozzle temperature.



## 3\) CHECK THE EXTRUSION

How you adjust the flow rate of the filament will vary depending on your printer. Using Cura and the Ultimaker series you’ll find the flow details on the machine in the material settings for the Ultimaker 2, on the Ultimaker 3 you’ll find them in the Custom settings in the Cura software. Reduce the flow rate by 5% and print a calibration cube to check if the filament is extruding correctly and eliminating the issue.



## 4\) NOZZLE TEMPERATURE

The tolerance of good quality filaments should negate the issue in principle, but if your filament has been sitting around for a while, exposed to moisture or sunlight, you may find that the filament’s tolerances to temperature has reduced. Decrease the hot end temperature by 5 ºC and try again.



## 5\)  Z-LIFT

Filament isn’t the only issue; if the head doesn’t lift high enough from the surface of the print then the nozzle itself can cause the scarring as it travels from one layer to another. On older printers you’ll need to re-calibrate if there are no Z-lift or Z-hop settings, otherwise increase Z-Hop or Z-Lift in 0.25mm increments.



# 26\. Print Looks Stringy and Droopy (Over-Extrusion)

Over-extrusion means that the printer supplies more material than needed. This results in excess material on the outside of the model printed.

Cause

Typically, the Extrusion multiplier or Flow setting in your slicing software is too high.



## 1\) EXTRUSION MULTIPLIER

Open your slicer software and check that you have the correct Extrusion multiplier selected.



## 2\)  FLOW SETTING

If that all looks correct then decrease the Flow setting in your printer’s software.



# 27\. Print Layers Look Uniformly Thin/Weak (Under-Extrusion)

Under-extrusion is the term given to the printer not supplying sufficient material for the print. Under-extrusion has many telltale signs — most significantly thin layers, unwanted gaps and even missing layers entirely.

Cause

There are several possible causes. First, the diameter of the filament used does not match the diameter set in the slicing software. Secondly, the amount of material that is extruded is too low because of faulty slicer software settings. Alternatively, the flow of the material through the extruder is restricted by dirt in the nozzle.



## 1\) CHECK THE FILAMENT DIAMETER

Start with the simplest issue, have you set the correct filament diameter in the slicing software? If you’re unsure about the diameter the value along with the recommended temperature is usually printed on the box.



## 2\) MEASURE THE FILAMENT

If you’re still not getting the results you want and filament flow is the issue, then use a set of calipers to double-check the filament diameter. You should be able to tweak the filament diameter settings accurately in the slicer software settings.



## 3\) CHECK THE HOT END FOR DEBRIS

After printing, most printers will lift the printhead away from the print base. Quickly check that the nozzle is clear from a build-up of filament and dirt.



## 4\) SET THE EXTRUSION MULTIPLIER

If there is no mismatch between actual filament diameter and the software setting, then then the extrusion multiplier (also referred to as the flow rate or flow compensation) may be too low. Each slicer application will handle this slightly differently but the principle is to increase this value in steps of 5% until you see the problem is gone.



# 28\. Print Looks Melted and Deformed

Filament is surprisingly resilient to all types of misconfiguration, including overheating of the hot end. It’s for this reason of resilience that noticing your hot end is too hot isn’t always as easy as you’d think it would be. A sign of this can be the appearance of uneven layers; when you take a closer look you can see that it’s not so much uneven as melted. Again our model shows this subtly on the cabin, and to a far greater effect on the chimney where it starts to look a little like wax running down a melted candle. Overheating filament can also cause huge issues with accuracy, especially when it comes to threaded holes you have printed. Finding that some holes are correct and others are too small is often an initial sign that the temperature could be too high.

Cause

Normally, having too hot a hot end or overheating is an easy fix. There needs to be a fine balance between melting the filament so that it will flow, and enabling the filament to solidify quickly so that the next layer can be applied to a solid surface. Before you go adjust the temperature however, first make sure that you have loaded the correct material settings for your 3D printer (as part of the filament loading process). If you have, then it could be that you need to adjust the temperature just a touch.



## 1\) CHECK THE RECOMMENDED MATERIAL SETTINGS

This might seem obvious, but just double-check that you’ve given the printer the correct details about the material. The latest filament temperatures range from between 180 – 260ºC or thereabout, so it’s surprising how easy it is to get this wrong.



## 2\) DECREASE HOT END TEMPERATURE

In the printer or software settings decrease the hot end temperature. Depending on the severity of the overheating, drop the temperature in 5ºC intervals.



## 3\) INCREASE PRINT SPEED

If the filament isn’t being discolored then you could try speeding up the print speed.



## 4\) ADJUST FANS

Check that the cooling fans are directed at the hot end. Check that they’re in the right position and if possible boost their speed to increase airflow over the cooling filament.



# 29\. Pits and Hollows in Top Layer (Pillowing)

The top surface of the print shows unsightly bumps or even holes.

Cause

The two most common causes are improper cooling of the top layer and that the top surface isn’t thick enough.



## 1\) FILAMENT SIZE

Pillowing is an issue that can affect all 3D printers, however, it’s far more common on those using 1.75 mm filament. If none of the other tips below help, try switching to 2.85mm filament if you can.



## 2\) CHECK THE FAN POSITION

Cooling can be a cause of pillowing. As the print starts your printer’s fans will typically be set to low or off and after the first few layers, they should kick into action. Check that the fans around your hot end start spinning, especially toward the end of the print. If they appear to be functioning fine, then the issue could be that they are not directing sufficient airflow over your print. There are a variety of 3D printable mods to alter your print airflow.



## 3\) SET FAN SPEED IN G-CODE

Another cooling issue happens when each successive top layer of molten plastic is applied. As it covers the inner support structure it needs to be cooled quickly to avoid falling into the holes between the supports. The speed of the fans can be adjusted in the G-Code. A common G-Code for Fan On is M106 and is M107 Fan Off. By those control lines, you just need to set the Fan speed to maximum for those top layers. For example, looking at the G-Code (generated in Cura for printing on a Prusa i3) for a 1cm x 1cm cube printed at 0.1mm layer height, we can see that there are 97 layers. Knowing that we have a ‘Bottom / Top Thickness setting’ of 0.6mm we can look back to ;LAYER:91, then in the subsequent line add M106 S255. M106 sets the fan going and S255 sets it to full blast.



## 4\) INCREASE TOP LAYER THICKNESS

The easiest solution is to increase the top layer thickness. Most applications will enable you to do this in the advanced section, under the ‘Bottom / Top Thickness setting’. You’re aiming for at least 6 layers of material normally and up to 8 for smaller nozzles and filaments. If your layer height is therefore set to 0.1mm then set the ‘Bottom / Top Thickness setting’ to 0.6mm. If the effect of pillowing still exists then bump it up to 0.8mm.



# 30\. Web-like Strings Cover the Print (Stringing)

There are unsightly strings of plastic between parts of the model.

Cause

When the print head moves over an open area (also known as travel move), some filament has dripped from the nozzle.



## 1\) ENABLE RETRACTION

Retraction is an important factor when it comes to quality of finish and can be enabled through most slicing software. Its function is pretty simple and works by retracting the filament back into the nozzle before the head moves. The idea is that it avoids molten filament from trailing behind the head creating thin strings in its wake. Most applications such as Cura offer a one-click activation option. This uses a set of default parameters and is perfectly adequate for the most part, but for fine-tuning there are customizable options that give greater control. Adjusting the minimum travel of the head before retraction is activated, for example.



## 2\) MINIMUM TRAVEL (MM)

Reducing the minimum travel is usually the quickest fix for stringing if the standard retraction isn’t doing the job. Drop the value in 0.5mm increments until the stringing has stopped.



## 3\) JUST CUT THEM OFF

This isn’t the most elegant of solutions but simply taking a scalpel to the strings is quite often the quickest and easiest solution.



# 31\. Print Has Lost Dimensional Accuracy

When you’re designing a product in your CAD application, the dimensions you’ve painstakingly planned need to be perfectly reproduced by your 3D Printer. However, when it comes to bolting your product together, you find that all that accurate measurement and design has gone to pot. Nothing aligns, the holes are the wrong size and nothing fits. Print dimension accuracy is actually one of the few areas of 3D printing where it’s highly likely that your printer is absolutely fine. Before checking the printer for faults, double-check that the dimensions of the 3D model are correct.

Cause

Let’s start with the measurements and the most common problem. First of all, check that you’re working in real-world measurements; cm and mm are probably best, although inches are also a workable unit for 3D printing. Mix the two up between your 3D model and slicing engine, and you’ll quickly spot the error. If all is fine with the unit selection, then double-check the physical measurements of the parts. When it comes to measuring, always measure twice! Now if you have separate prints that need to fit together, such as a male-to-female connector, or screw and hole, then make sure the insert is slightly smaller than the hole you’ve created for it. For example, if you have an M5 screw and you’ve created a 5mm diameter hole for it to go in, then it’s not going to fit (at least not without some muscle and determination). In order to solve this, increase the hole size by 0.1mm for a fine print and possibly 0.2mm for a low quality print. Print and try again. If it still doesn’t fit enlarge it a little more. If the hole looks oval, the issue is not necessarily the hole’s size. If you’ve created a low polygon shape, then the likelihood is that your hole is no longer round and instead has slightly straightened edges. When printing an object with holes, always ensure you keep a moderate polygon count to keep those smooth round holes for things to fit in. The same goes for custom shapes that need to fit together. Reducing the polygon count of one object can cause all sorts of issues if the two sections have rounded edges that need to interconnect. Once you’ve finished checking everything with the model’s dimensions, it’s time to turn your attention to the printer. The first few layers are all important when it comes to print accuracy. Print out a test cube 50mm x 50mm and use digital calipers to check the measurements; make sure you print the cube at the same layer height you’ll be printing your final model. Firstly check the overall height to see if it equals 50mm, if it does then all is fine on the Z-axis. If not, then carefully measure the top 20 layers — these should equal 20mm. If this is correct but the overall height is wrong, then it’s likely that the first few layers are causing the issue. To resolve this, check the height of the nozzle from the print platform and that it’s within the margin of error for your printer in relation to the layer height. If your nozzle height is 1mm from the print platform and your layer height is 2mm, you may find too much filament is being laid down in that first layer and causing the issue. If this is the case, either recalibrate your printer and ensure the nozzle to platform distance is increased or reduce the layer height. Now check the X and Y dimensions. If they’re approximately 1mm smaller than they should be but all proportions look correct, it could be due to filament thermal contraction. This is relatively common with ABS; in order to correct this, work out the percentage of error and increase the scale of the print to compensate. Using high-quality filaments is the best way to avoid this. Back to the hole and have a look inside; if the walls look smooth then everything is ok. If you see the layers protruding slightly then this could be a sign that the nozzle is too hot and the filament is oozing after it’s been laid down. If the hole looks oval, then it could be that one of your belts is loose or there is a slight misalignment of the X- and Y- axes. Check all are tight and everything screwed into place as should be.



## 1\) CHECK WORKING UNIT OF MEASUREMENT

In your 3D printing application make sure you have the correct real-world dimensions selected.



## 2\) DOUBLE-CHECK THE MEASUREMENTS

If you’re designing a part that needs to connect with other objects, double-check your measurements and use a digital caliper.



## 3\) OVER-SCALE SCREW HOLES

If you’re making a screw hole, create a virtual 3D M5 screw with a diameter slightly larger than it should be and use this to extract/create a boolean subtraction from the model you need the hole to appear in.



## 4\) INCREASE POLYGON COUNT

Reducing the polygon count of your models can cause issues with the slightly flattened edges. Make sure you keep polygons within a reasonable count for smoother gradients and better fits.



## 5\) TEST PRINTER ACCURACY WITH TEST CUBE

Use a 3D Print Calibration Cube to check the X, Y, and Z dimensions of your print.



## 6\) CHECK NOZZLE TEMPERATURE

Try reducing your print temperature if there are blobs and other stray extrusions on the inside of your print’s holes.



## 7\) CHECK BELTS AND RAILS

Check over the belt tension and make sure all axes are straight and correctly aligned.



# 32\. Print Offset in Some Places

The lower and top layers shift so that you get a stepping effect through the print. Usually, it’s quite subtle, but the above image shows a print with a more pronounced effect.

Cause

There’s a variety of reasons for shifting layers, and these can be as simple as someone knocking against the printer during the print process. More complex causes can be bent or misaligned rods, or even the nozzle catching on the print and causing a slight shift in platform position



## 1\) CHECK THE PRINTER HAS A STABLE BASE

Place the printer on a stable base and in a location where it will avoid being knocked, poked and generally fiddled with. Even a small nudge of the printer can shift the print base and cause issues.



## 2\) CHECK THE PRINT BED IS SECURE

Many 3D printers use some form of detachable print bed. Although this is handy when it comes to removing prints and avoids damage to the printer, it also means that over time clips and screws can work loose. Make sure that when you reinstall the print platform it’s clipped or bolted tightly in place to avoid any slip or movement.



## 3\) WATCH FOR WARPED UPPER LAYERS

A print’s upper layers can easily warp if cooled too quickly. As the layers warp they rise and can cause an obstruction to the nozzle as it moves. In most cases the print will release from the platform, but if it doesn’t the powerful stepper motors can push the print and platform around. If your prints are suffering from warping in the upper layers try reducing the speed of the fans slightly.



## 4\) REDUCE PRINT SPEED

It is possible to speed up the print times for your machine by increasing temperature and flow. However whilst this may result in the filament flowing in the correct quality the rest of the machine may struggle to keep up. If you hear a clicking during printing this could be a sign that the printer is going to fast. If you do hear a click the first port of call is to check that the filament isn’t slipping, before you take a look at the actual printer speed. You can adjust your printer’s speed easily enough in any good slicing software.



## 5\) CHECK THE BELTS

If layers are still shifting then it’s time to check the belts. A quick check is to just go around all belts and pinch the two together. The tension in each belt should be the same, if not then you’ll need to adjust the belt position to even out the belt tension. Over time the rubber belts will stretch (You can often tell if they do as they’ll start to slip on the drive pulleys), if there is quite a bit of play in the belts then it’s time to replace them with new ones. Over tight belts can also be an issue but this is usually only a problem if you’ve built the machine yourself. Some printers such as the Prusa i3 have belt tensioning screws that enable you to easily adjust the belt tensions.



## 6\) CHECK THE DRIVE COUPLERS

These are usually connected directly to a stepper motor, and one of the main rods that drives the print head. If you carefully rotate the coupler you’ll see a small grub screw. Hold onto the rod and taking hold of the attached belt and then tug the belt and try to force the pulley to turn. You should find that there is no slip between the coupler and stepper or rod. If there is, tighten the grub screw and try again.



## 7\) CLEAN AND OIL THE RODS

Over time debris can build up on the rods which means that at some points along their length they encounter an increase in friction. This can affect the free movement of the head and cause layer shifting. A quick wipe and re-oil of the rods usually solves the issue.



## 8\) CHECK FOR DEFORMED RODS

If you see the print head falter at certain points then it could be that one of the rods has become slightly bent. You can usually tell by switching off the machine so there’s no power going through the steppers and then move the print head through the X- and Y- axes. If you feel resistance then you know something is amiss. Start by seeing if the rods are aligned, if they are then remove the rods and roll them on a flat surface. If any are bent then it will be quite obvious.



# 33\. Bridges are Messy

Bridges are essentially a stretch of plastic that is extruded between two raised points. If you have two columns with a 5 cm gap, then the beam that sits on top between those two points with nothing below is the bridge. Most filament is surprisingly resilient to bridging, and with a finely tuned printer the distance achievable when bridging can be surprising. However, you know something isn’t quite right when your printer starts to fail to bridge even the smallest gap. The most obvious sign is when the printer fails to successfully bridge gaps between 1 and 3 cm. The extrusion may be too thin, filament sags, or simply flows down the height of the bridge rather than across.

Cause

Getting to the bottom of bridging issues is usually pretty easy and much of the diagnosis comes through the look of the failed bridge. It’s also worth noting that the way that different slicer applications handle bridging is very different, with applications such as Simplify3D having a special Bridge option that will adjust extrusion and cooling for the best results. The most common related issue is that the gap you’re trying to bridge is just too big, this distance will vary with each printer and material. You can usually tell if the gap is too great as the filament will start to sag in the middle or collapse. Cooling is another major issue, the filament needs to be cooled quickly in order for it to be able to support itself between the two columns. Extrusion speed is equally important, if the print head moves too quickly then the speed and vibrations will inevitably cause instability before the filament has set. Too high extrusion temperature will often result in bridging, again showing sagging of the filament. If the extruded filament is of different thicknesses then you know this is the issue.



## 1\) CHECK THE BRIDGING CAPABILITIES

You can make a test print with columns and bridges of different distances to check how far your printer will go, start with a 5cm gap and then increase, anything between 5 and 10 is good, 15 would be exceptional.



## 2\) ADD SUPPORTS

A quick and easy fix is to simply add supports below the structure



## 3\) INCREASE FAN SPEEDS

Boost the extrusion fan speed to ensure that the filament cools quickly, the faster the filament sets the larger the bridge it will be able to create.



## 4\) DECREASE EXTRUSION SPEED

Fast extrusion is an absolute no when it comes to bridging, you need slow and steady as the filament needs to have time to set as the distance is bridged.



## 5\) USE SIMPLIFY3D

This dedicated 3D print software features a bridging option and will automatically recognize any areas of your print that require greater cooling and slower extrusion speeds.



# 34\. Print is Stuck to Print Bed

Prints seemingly welded to the print platform are as common as prints not sticking at all. Annoyingly quite often you’ll experience both issues in one day, and usually by solving one you create the other. The main fix to this 3D print issue is balance. Spotting the problem is simple. Once the print has finished it just won’t budge. In fact, it’s welded so firmly you could possibly lift the weight of the printer by the print.

Cause

When the filament is warm it’s designed to be tacky so that as each layer is extruded it will stick together. As the print base is warm the filament that makes contact will remain slightly tacky until completely cool. A print with a large surface area that’s in direct contact with the base can be just plain stubborn to remove. It really does just bond with a suction-like effect. Old print platforms can become overly textured with layers of glue or small pits in the glass acting as anchors to the print. Over time this texture can create an almost unbreakable bond. Some print platforms are perforated by design, and typically they give the most difficult to remove prints. Cheap filament can also be the culprit for a ridiculous print bed bond. Although the filament melts fine, it doesn’t always solidify completely.



## 1\) HAVE A LITTLE PATIENCE

You’ve waited hours for the print, so waiting a little longer for the print to cool down completely isn’t going to hurt. After some cooling time, it may release of its own accord. As the filament cools it solidifies, losing the tackiness that is needed for the layers to bond.



## 2\) USE A PALETTE KNIFE

Many 3D printers come with them, but you can likely find one at any decent hardware store. If you’ve left it for an hour and the print is still stuck firm, release the build plate from the machine and place it onto a desk with something to support the print base from behind. Ideally a wall. Then carefully use the knife to work around the edge and prize the print free.



## 3\) GIVE THE PRINT PLATFORM A CLEAN

It may not help with the present print, but if your print platform is clogged with glue then it’s probably time to give it a clean. Future prints may not exhibit the same unbreakable bond. If the print is still attached run it under hot (not boiling) water and gently use a palette knife to scrape off any surface glue. Leaving it to soak in hot water will generally release the print as well, but take care to only apply this tip to removable print bed surfaces. After the print releases, make sure the platform is cleaned and inspected for any pits in the glass. If there are then flip the glass over and use the smooth side. If both sides show signs of pitting buy a new one.



## 4\) STICK IT IN THE OVEN

There are times when hot water just won’t budge a print, if you have a glass or other heat-resistant platform with no plastic or electronics attached and it’s possible to remove it from the printer, pop it in the oven. Set the temperature to 100º and then use a pallet knife to see if you can move the print. If not increase to 120º and leave for five minutes and try again. Increase the temperature until you have removed the print or the print has melted and can be scraped away (ensure you wear heat-proof gloves). The latter extreme will most likely be at the expense of sacrificing your print.



## 5\) DON’T USE CHEAP FILAMENT

On so many levels cheap filament is a false economy. It can bond to your print platform in ways that no other material known to man can, and is perfectly suited to welding printheads and extruders together once cooled. The only real way to avoid the issue is to completely avoid cheap filaments.



## 6\) MAKE SOME HOLES

This requires a little foresight, but by creating a few holes in the design of the print base you can avoid some sticking caused by too much surface contact and suction.



# 35\. Resin too Cold

Much like some FDM 3D printing filaments, ambient temperature can play a big part in whether a photopolymer resin will set during the SLA printing process. If your resin is too cold, it’s unlikely to set and, if it does, will set inconsistently, resulting in partial prints and poor plate adhesion.

Cause

Beats us. We think it’d take a chatty materials scientist to explain this because there’s nary a whisper online about why this is the case. It is, because it is. Perhaps someone in the comments can explain it for us, but all we do know is that a common cause of resin prints failing is the resin and ambient temperature surrounding the printing being too cool. Temperatures as high as 25-30 degree Celsius can be necessary for some resins.



## 1\) MOVE PRINTER TO A WARMER ROOM

Easier said than done if you happen to live in a generally colder climate. Something as simple as moving the printer to a warmer room close to a source of heat could be enough to hit that sweet spot and solidify your resin prints into their “green” state (solidified, but not hardened/cured).



## 2\) INVEST IN A CHAMBER HEATING SOLUTION

There’s very little out there in terms of dedicated resin 3D printer heating, but some industrious makers have turned to the fledgling (ha) community around home incubators for the solution. It’s possible to pick up an incubator heating kit that includes heater, fan, thermostat, and power supply for around $50, though we’re sure homebrew solutions are out there for less. This serves as a good starting point though.



# 36\. Printing too Fast

In SLA 3D printing, a UV light source, typically a laser, hardens photopolymer resin. Much like photographic film requires a significant amount of exposure to light for the image to be captured, so too must the resin be exposed to the appropriate amount of UV light before it hardens.

Cause

Underexposure, be it from the laser moving too fast or an underpowered laser (which we cover below), will result in nothing printing at all, or weak prints that are not rigid enough to withstand the peel force of your machine.



## 1\) DECREASE PRINT SPEED

Depending on the SLA printer you are using, it may be possible to slow the print speed in your slicing settings. Doing so could fix the issue of weak prints or no print, although we would advise checking the temperature of your resin first. The frequency of problems people encounter being fixed by warming things up makes that the likely culprit for such an issue.



# 37\. Underpowered Laser

Much like printing too fast can underexpose the resin, so too can using an underpowered laser.

Cause

Your laser power is too low. In order to polymerize the resin, there needs to be sufficient energy from the laser. And much like a laser tracing the model too fast will not transfer enough to the resin, neither will an underpowered laser.



## 1\) INCREASE LASER POWER

If your printer’s settings allow for it (like on the Peopoly Moai), increasing the laser power by tiny amounts at a time can help you find the sweet spot for exposure using your current resin and print speed.



# 38\. Prints Not Adhering to Print Plate

Your support base isn’t sticking to the print plate. Either it’s partially peeling away, or separated completely and is left floating around the resin tank.

Cause

There are a number of reasons this can happen. Firstly, it’s possible the way your SLA 3D printer repositions to the next printing layer generates more peel force than how you are printing can handle. With bottom-down SLA 3D printers, peel force is the suction effect exerted on prints every time the print plate and bottom of the resin vat separate to reposition. Depending on the mechanism by which your printer does this action, there are a few tricks you can do to minimize, or at least mitigate this pull. Another factor that can affect a print’s adhesion is whether the print plate is sufficiently prepared. Bottom-up SLA printers printing onto a flat metal plate stick well when the plate is finely textured, or rough even. Conversely, perhaps your interfacing layer in the resin vat has some ghosting which is hindering the laser in setting the resin. Alternatively, it could be the classic culprit of the resin simply not being warm enough. You may be on the verge of acceptability, but as the print progresses and the resin level lowers, a slight temperature fluctuation could cause the resin to stop setting.



## 1\) REPOSITION YOUR PRINT

If your printer utilizes a tilting resin vat as part of its mechanism (itself a design choice to help relieve peel force), this creates a gradient across the print plate where said force goes from very strong, to weak. Positioning your print in an area of the print plate that is under less peel force can go some way to helping your print get a good bond with your print plate, in addition to reducing the stress on taller parts that will be free-standing or reliant upon supports.



## 2\) LEVEL VAT

Depending on your 3D Printer, it may be possible to auto- or manually re-level your vat or bed. A mainstay of 3D print troubleshooting for FDM 3D printers, it also applies to SLA 3D printers, too. If you are finding that only part of your print is sticking to the print plate, then it could well be that said part of the print plate is not set tightly against your interface layer in the vat when the laser fires. Another telltale sign of this is a flat disc of hardened resin stuck to your interface layer inside the vat after you’ve finished or canceled the print.



## 3\) CHECK TEMPERATURE

It’s possible your print setup is on the verge of printing successfully, but the resin hardening is just not quite there. If the resin is too cold, it could be that the resin is not setting well enough, and therefore does not adhere well to the print plate. Try heating the resin and print chamber in some way (repositioning the printer in a warmer room could do the trick).



## 4\) CHECK RESIN VAT INTERFACE LAYER

Many SLA 3D printers utilize a thin layer of gel-like material (PDMS is a common one) on the bottom of the acrylic resin vat to serve as an interfacing layer. On bottom-up resin printers — the common method in “cheaper” machines — the print plate pushes up on the interfacing layer to trap a thin film of resin for each layer’s setting. It is inevitable that, over time, ghosting and general wear and tear could lead to poor printing, making some areas of the print plate no longer viable to print on. The solution is to either: replace the interfacing layer with your own (Solaris Silicone is one oft-repeated option), buy a new interfacing layer if available, or, if not, a new vat. That, or continue to reposition your prints on non-damaged areas of your vat.



## 5\) FILTER YOUR RESIN

Several prints in, you may find small set pieces of resin floating about inside your vat. These rogue rascals can get in the way and interfere with the laser curing fresh resin. It’s good practice to comb through your vat after each print not only to catch these particles and remove them, but to dislodge any set resin stuck to the bottom of your tank.



## 6\) REMIX YOUR RESIN

If you’ve followed the above step and filtered your resin for print disrupting particles, but then left the machine alone for some days, there is a chance the resin has settled, with the heavier pigment from colored resins settling into their own layer that will print inconsistently as the print proceeds.



## 7\) REMIX YOUR RESIN

If you’ve followed the above step and filtered your resin for print disrupting particles, but then left the machine alone for some days, there is a chance the resin has settled, with the heavier pigment from colored resins settling into their own layer that will print inconsistently as the print proceeds.



# 39\. A Section of the Print/Supports Detached or Moved

At some point during the print, a chunk of the hardened resin has shifted, either separating completely or moving enough to interfere with and mess up the other parts of the print.

Cause

As is often the case for disfigured SLA prints, the forces at play in the vat itself are likely the culprit. It could be that what you are printing is incorrectly oriented to withstand the peel forces, resulting in distorting movements that cause parts or the supports to separate. Such movement in the part will cause subsequent layers to be formed on the vat interface, rather than the print itself, so you end up with two issues from the one failure. Alternatively, maybe your print is correctly positioned, but your support structures just aren’t strong enough. Or it could be that everything would print fine, except that you have a print with a large cross-section that is messing things up with excessive peel force or, if hollowed out, insufficient drainage to mitigate explosions.



## 1\) HOLLOW LARGE PRINTS

For models that feature a large surface area at any point of their printing, you should strongly consider hollowing them (and adding drainage holes) where possible. This means that rather than forcing a large flat surface to pull away from the bottom of the resin vat with every layer change, you are instead having a thinner outline of the model detach each time. This requires much less force and is less likely to pull your print apart — though this works best providing you add drainage holes using your modeling/slicing software. Without holes added to the solid masses of your print, you will be trapping a reservoir of unset resin inside — an expensive waste and something that will defeat the point of hollowing in the first place.



## 2\) STRONGER SUPPORTS

If your model looks good to print, but you suspect the peel force is still accountable for failed prints, the next step we would suggest is strengthening your supports. Bump up the width of the tips where the support meets the printed part by a fraction of a millimeter and add struts between them if you haven’t already.



## 3\) CHECK/SECURE PRINT PLATFORM

It’s possible that your printing platform is not properly secured. As the printer goes about its business stepping the platform layer by layer, slight variances in position from the platform jostling could cause layers to misalign and become separate



## 4\) REORIENT YOUR PRINT

Oftentimes an SLA print issue can be resolved with better orientation of your model. Not only can this improve the quality of your prints, but it can reduce the stresses in the vat and increase the chance of model printing successfully.



## 4-1) Consideration

(1) Positioning

Many, if not all bottom-up SLA 3D printers feature some form of peel mechanism to separate the print plate from the bottom of the resin vat when repositioning on the Z-axis for the next layer. Depending on the method in which your printer does this, it’s possible the strength of this peel force changes across the area of your print plate. If so and this is known for your printer, you can increase the likelihood of the print surviving the forces by positioning it in an area subjected to weaker peel force.

(2) Support overhangs

As with FDM 3D printing, severe overhangs need to have some form of support to print successfully. With some 3D models, you can mitigate the need for some by angling your model, decreasing the overhang angles in the process, and making them viable for printing without support.

(3) Minimum Points (or Minima)

As with overhangs in need of supports, minimum points are isolated parts of your print that are not directly connected to the body of a print. Think of a person with their arms by their side printing the right way up — the fingertips would be considered minima, since they begin printing separate from the body, with the arms materializing on top and connecting at the shoulders. Such minima require supports, otherwise they are highly likely to break away and float free in your vat of resin. Alternatively, you can eliminate the need to support minima with tactical model orientation (flipping the person to print head first removes minima, as the body tapers out to the arms and, finally, feet).

(4) Cupping

The model you’re planning to print may feature voids facing into the print vat — especially so if it’s a large model that you have hollowed. Such a feature can cause a huge problem in excessive peel force for the print to overcome (in all likelihood messing the print up in the process). If the “cup” is shallow, angling your print could be enough to minimize the cupping effect to non-print-destroying proportions. The alternative solution is to add drainage holes to the model in your preferred modeling software, which would allow the resin to flow through with each layer change.



# 40\. Layers Have Separated (Delamination)

There are areas of the print that have become somewhat frayed, like the print is pulling apart from the layers and not bonding well/at all.

Cause

When the layers of an SLA print don’t bond well (known as delamination), there can be a couple of causes. Firstly, it’s possible that you haven’t oriented your print well enough to avoid minima. These parts print in isolation from what it fixed to your print platform and as such detach, print sloppily layer by layer and generally just mess up prints. Don’t try them. Make sure all severe angles and points that are not directly connected to the main print at their highest point are supported. Besides shifting unsupported parts, debris, poorly mixed resin and ghosting on the vat itself can be a cause of delamination. These are all easy to address. Additionally, delamination could come after a successful print during the post-processing stage. If your material has particularly weak layer bonding, leaving the part in IPA for washing for too long could weaker the layers further and cause the part to break apart.



## 1\) SUPPORTS

Minima in your prints will mess up an SLA print when not supported. Make sure you generate supports for all severe angles and points that are not directly connected to the main print at their highest point. Oftentimes you can get creative with how you orient your print on the print plate in your support generation software to minimize the amount you need.



## 2\) CHECK THE LASER’S PATH IS CLEAR

We’re lumping a few points into one here since they’re all suggested for the same reason — allowing the laser to hit the resin unobstructed. This means checking the resin you’re printing in is “clean” and debris-free (take a resin comb to it or pour it through a filter to sift out the tiny shards of green resin that may be left floating from previous prints). Now you know your resin is clear and well mixed, the next culprit is likely to be at the bottom of your vat — the interfacing layer. If this isn’t the first print in your current vat, then check for ghosting on the interfacing layer in your resin vat. Faint markings from previous prints are no doubt visible, and over time these can become enough of an obstruction for the laser to cause weaker, or even failed prints. If this is the case, time for a new layer in your vat (or, depending on your machine, a new vat altogether).



## 3\) DON’T BATHE PARTS IN IPA FOR TOO LONG

What the header says. If you suspect your part of having weak layers bonding, washing it for too long in IPA can weaken it further. Keep your IPA wash cycle to a minimum, quickly and gently agitating the unset resin off before rinsing in water.



# 41\. Small Fins and Disks Attached to Print (Ragging)

Flakes of set resin have incorporated into your print, giving an ugly surface finish with offshoots that are not part of the model.

Cause

The likely cause of these unwanted flakes in your prints is an unclear optical path. Sometimes the laser can become diffused, “leaking” to the resin outside of spot it is supposed to be setting.

Settled resin, resin clouded with large set particles from prior prints or smudged or dirty planes between the laser and resin can also contribute to the problem.



## 1\) FILTER YOUR RESIN

Eliminate any particles of set resin from past prints by passing it through a filter. Readily available from 3D printing stores, these paper and mesh filters capture large particles that might otherwise cloud your resin during the printing process.



## 2\) MIX YOUR RESIN

If your resin has been standing for some days without action, it might have settled, with the pigments settling in a thicker layer than the photopolymer. Give the resin a mix, ensuring the pigment and photopolymer are evenly distributed. You can usually tell when this is done by the lack of streaks as you mix.



## 3\) CHECK/CLEAN OPTICAL PATH

Depending on your machine, you may be able to access the transparent internal barrier protecting the laser/galvanometers. If you can, check that this is clear from dust, fingerprints, and other contaminants that may prevent the laser from passing clean through.



# 42\. Fine Details of the Print are Lost

Small features of the printed model are not as dimensionally accurate as in the digital file. One of two things happened. Either they “miniaturized”, sometimes disappearing completely, or became fuzzy, losing their crispness and looking washed out.

Cause

First of all, it is important to point out that every 3D printer has a fixed detail resolution beyond which they simply can’t accurately print intricate details. On modern resin printers, this resolution is very high, nevertheless, make sure that you are not trying to print something your machine simply can’t handle before reading on. Under- and overexposure can affect a model even if it prints successfully. Even though exposure time can be long enough for the model to stick to the build plate and print, if the light source does not have enough time to fully cure the desired geometry, small details like pins may get lost or are too weak to withstand the subsequent IPA wash. Conversely, if the layer exposure time is too high, overexposure will happen where the light source cures more resin than desired and washes out sharp edges or closes small holes and channels. Semi-cured resin residue on prints after the IPA wash is also an indicator of overexposure and can be adjusted by adjusting layer exposure time either in the software or on the machine itself, depending on the model. Both over- and underexposure will result in dimensional inaccuracies and loss of fine detail, making it worthwhile to find optimum layer exposure time for the most accurate prints possible.



## 1\) CALIBRATION

There is a wide range of calibration files offered by resin and printer manufacturers as well as private enthusiasts that make layer exposure time calibration simple and straightforward. Doing a calibration set-up is generally good practice when breaking in a new 3D printer and any time a new resin is used. Colorants like pigments and other contaminants can also affect exposure values.

