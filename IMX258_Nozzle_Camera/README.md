# Sony IMX258 as Nozzle Camera for the Voron Stealthburner 
This is my take of a Nozzle Camera based on the readily available and off-the-shelf Sony IMX258 Camera Sensor.

In the spirit of open source and Do-It-Yourself, I decided to also jump in on the hype and have my own take on this, especially as I am not satisfied with the current offerings out there. On top of that, I want to provide the community with more options as to where they can source their parts, hopefully for cheaper and better tailored for our printers.

The center-piece of this mod is the off-the-shelf Sony IMX258, it is capable of 4K30fps or 1080p60fps, however do take note that while the datasheet for the IMX258 shows these specs, many sellers may not have configured their driver board correctly as they focus on it's 4K capability instead of the higher frame rate that we are more focused on. These sensors come in a variety of different lense options from Auto Focus to Fixed Focus, from narrow to wide angles.

As a cheaper alternative, there is also the OMNIVISION OV5693 which is an iteration of the OV5648 but with better low light performance, it has the exact same form factor and therefore compatible with this mod. However this sensor is only capable of 1080p30fps.

As a Nozzle Camera, what we want is a Fixed Focus camera of around 75 to 90 degrees Field of View, 80 degrees seems to be a good option, however the more commonly found 75 degrees will work just fine, again, do take notice of the FPS configured, as higher FPS means less motion blur, our printers do have a habbit of going pretty fast.

I have found a seller on AliExpress who was willing to change the lens for me to 80 degrees as well as having a correctly configured driver board. I will have a link to it in the BOM table below.

## Table of Content
- [Showroom](#showroom)
- [BOM](#bom)
- [Instructions](#instructions)
- [Questions](#questions)
- [Remix / Derivative Work Notice](#remix--derivative-work-notice)
- [Acknowledgements](#acknowledgements)
- [Changelog](#changelog)

## Showroom
<img src="./Showroom/Front_View.png" width=800>
<img src="./Showroom/Cable_Chain_View.png" width=800>
<img src="./Showroom/CANBUS_View.png" width=800>
<img src="./Showroom/Nozzle_View.png" width=800>
<img src="./Showroom/IMX258%2BADXL345_Mount.png" width=800>
<img alt="video" src="./Showroom/snapshot.jpg" width="800" />
Video: https://www.instagram.com/reel/CogMm3sAScI/


## BOM
Pick ONE camera sensor from below, you WILL need to buy it with the driver board. You CAN definitely buy them from elsewhere or use other sensors, these are just the ones I used and are known to work. If you opt to buy the same sensor from elsewhere, please take note of it's specs, like I mentioned previously, they could be accidentally handicapped. 

Hardware | Quantity | Link | Note
------------ | ------------- | ------------- | -------------
Sony IMX258 with Driver | Pick | AliExpress: [80°](https://www.aliexpress.com/item/1005005178412080.html)<br> Taobao: [80°](https://m.tb.cn/h.UNFOrxw?tk=EI69dhWxV7V) | 12MP 4K30fps 1080p60fps
OMNIVISION OV5693 with Driver | Pick | AliExpress: [80°](https://www.aliexpress.com/item/1005005203882395.html)^ <br> Taobao: [80°](https://m.tb.cn/h.UMNivgA?tk=silWdhWDLWl) | 5MP 1080p30fps (improved low light performance over OV5648)
M2x10 Self Tapping Screw | 2 | | For ADXL345
M2x8 SHCS | 3 | | For Camera Driver (can use M2x10 Self Tapping)
M3x8 SHCS | 1 | | Replacing the CW2 Cable Anchor with a shorter one
M3 Heatset Insert	| 2 or 3 | | (For Cable Chain Anchor Only)

^Ask the seller for 80 degrees Manual Focus lens if not already configured that way.<br>
If you find these sensors for a good price elsewhere (such as Amazon), please let me know and I will add it to this list.


## Instructions
While installation is fairly self explainatory, detailed Picture Guide will be coming soon.
### FPC Cable
The ribbon cable can be routed via the gap between the CW2 and Print Head, which will then meet up with the Toolhead PCB/Cable Compartment.<br>
<img src="./Showroom/cable_routing.gif"><br>
My camera module comes with a 160mm (175mm including camera and connector) FPC cable, and it is just enough for the above routing. If you purchased your camera module elsewhere and it's too short, you will have to route it to the cable anchor directly on the left.

### USB Cable
All of these methods requires you to cannibalize the provided USB cable, or if you are fancy, crimp a new cable.<br>
Personally, I am using a motion rated shield twisted pair cable, other cables may or may not work, so as with everything DIY, do so at your own risk and your mileage may vary.

#### Umbilical
I am in progress of switching to CANBUS, therefore I will be using an 8-core shielded twisted pair motion rated cable for [my umbilical mod](https://github.com/exiom-xyz/Voron-Mods/tree/main/CW2_CANBUS_PG9_Umbilical).<br>
I am using this cable found on AliExpress, if you plan to replicate.
Hardware | Link | Note
------------ | ------------- | -------------
Twisted Pair<br>Shielded Cable | [AliExpress](https://s.click.aliexpress.com/e/_DEWPhSD)<br>[Taobao](https://m.tb.cn/h.UM0h7yf?tk=sxi4dhndARF) | 8-core 22AWG (0.3mm²) as it has the outer diameter of 8.2mm and will fit through a PG9 Cable Gland

For non-CANBUS umbilical users, you can opt to run the USB cable provided as bending is considerably less than inside a drag chain, however I have not extensively tested this and it may eventually fail. Alternatively, you can also adapt the instructions for drag chain users by replacing the cable with a motion rated one.

#### Standard Cable Chain
If you are using a cable chain, you can also buy a similar cable using the same link as above or locally sourced.<br>
You will only need a much smaller cable, as the camera draws very little power, so something like a 4-core 24/26AWG (0.2/0.15mm²) is sufficient, you can even opt to tap 5V from the Toolhead PCB/Neopixels/Voron Tap, and will only need to run 2-core wire.

## Questions
#### Does this mod work with the 3DO nozzle camera?
Yes absolutely! as it has the identical camera sensor and driver.

#### I bought the camera module you suggested but I prefer a front mounted solution.
Your camera your choice! Please find the front mounted solution over at [3DO's Github repository](https://github.com/3DO-EU/nozzle-camera).

## Remix / Derivative Work Notice
My modifications are published under the same GPL-3.0 license of the original Voron Design projects my work also derives from. <br>
Feel free to remix and redistribute your derivative work, however it would be much appreciated if you provide credits and link back to this repository. <br>
You can also submit a pull request or send me your remix/related work to be included as part of this repository.


## Acknowledgements
https://github.com/VoronDesign - Thank you to the VORON Design team for the printer which this mod derives.<br>
https://github.com/3DO-EU/nozzle-camera - Thanks for the camera sensor retention model

## Changelog
7th Feb 2023 - Initial Commit
