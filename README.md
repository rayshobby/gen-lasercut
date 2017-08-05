# gen-lasercut
This folder contains an EagleCAD script (.ulp) for generating laser-cut acrylic enclosures for circuit boards. 
For details, please refer to: http://rayshobby.net/eaglecad-script-for-laser-cut-enclosures

## How does it work? 
The script finds the bounding box dimensions of your PCB outline and use it with the following parameters to create the six panels of a box-shaped enclosure.

## Explanations of parameters:
All length-related parameters are of unit millimeter (mm).

* **PCB-enc margin**: the margin from PCB border to enclosure interior border.
* **Slot-edge margin**: the margin from the slot boundary to enclosure edge.
* **Acrylic thickness**: the common acrylic material I’ve used are either 2mm thick or 3mm thick. You may have to adjust this slightly to account for your material's thickness error.
* **PCB thickness**: standard PCB thickness is 1.6mm.
* **Height above/below PCB**: this defines how much space there is above and below the PCB (NOT including acrylic).
* **Top/Bot X/Y slots**: define the number of slots on the top/bottom panel and in the x/y directions. The number of slots depend on the length in x or y: longer edges probably need more slots. Also I generally make the number of slots on the top and bottom panels different, to make it easy to identify the orientation of the side panels.
* **Slot rounding**: this will round the slot size to the nearest (ceiling) multiple of the slot rounding number. The slot size is automatically computed based on the number of slots. If you want the slot size to be rounded to the nearest multiple of 10, for example, you can set slot rounding to 10.
* **Mount wing/hole size**: if you need the back panel to be wall-mountable (which is generally the case for my boards),
you can define the width of the wing and mount hole size (diameter).
* **Round corner r**: radius of the rounded corners.
* **Slot-plug margin**: this will shrink the plug size slightly to make it easy to insert into the slot.
* **TB hole size**: top-bottom hole size. This is set according to the size of screws/pillars you need. For example, if you plan to use M3 screws, set this to be slightly larger than 3.0; if you plan to use M4 screws, make it slightly larger than 4.0 and so on.
* **Eagle layer**: defines which Eagle layer it uses to draw the enclosure. By default it uses layer 104.

## Running the script:
Upon running the script, it will hide all layers except the Acrylic layer (104 by default) and the dimension layer. If you re-run the script, it will remove the existing content on the Acrylic layer, and re-create the outlines. So be careful re-running the script — if there is anything you want to preserve (such as custom cutouts), you want to create them in a different layers so that they don’t get wiped out when running the script again.

