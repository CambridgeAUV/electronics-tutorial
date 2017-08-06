# CAUV Electronics Tutorial

## Overview 

This repository serves as a guide to get you started with CAUV electronics. In this series of tutorials, you will first learn how to design useful real-life circuits with ICs (Integrated Circuits) and sensors. You will also learn how to use KiCad to design circuit schematics, PCBs(Printed Circuit Boards) and generate Gerbers for manufacturing the PCBs. This series will also provide guidance on how to navigate through the sometimes incomprehensible datasheets of the components that you will be using. 

If you are an absolute beginner in electronics, ie. you only know fundamental theories like Ohm's law, then you can read the following [The Basics](#the-basics) section. Otherwise, feel free to skip to the next section on [KiCad](#kicad). However, you can, by all means, still read The Basics section to refresh your memory of the very basics of circuit design. 

In this tutorial, you will build a prototype of a pressure sensor board from scratch. This board is used for testing purposes,  but is actually ready to be installed into the actual vehicle. This board contains a pressure sensor, as the name implies, a micro-controller and a differential signal converter. More technical details are given further into this tutorial.  The final design is available at the `cauv-electronics/pressure_sensor` folder in the https://github.com/CambridgeAUV/cauv_electronics repository. It is also available in this repository, together with the KiCad project at each of the steps below. 


## The Basics

Micro-controllers are used in circuits to communicate with sensors and other circuit components, such as other micro-controllers. Micro-controllers need to be programmed in order to function. Micro-controllers come in different packages. The most commonly used are surface mount packages which include closely packed pins and small package sizes. *Pins* on IC packages serve as connections between the silicon wafer within the package and the outside world, ie. other circuit components. All circuit componenets have a certain number of pins that must be connected to some other circuit components. Common ones include *power pins*, *GPIO pins* (General Purpose Input Ouput, which basically means the micro-controller can programmatically control the state of this pin), *reset pins*, etc. Even simple components like resistors have pins. 

During the circuit design process, you will need to first design (or in most cases, look for them on the internet) *schematic symbols* for the components that you are using. *Schematic symbols* are schematic representations of the components on a 2D sheet of paper. While most of the time you will be able to find the *schematic symbols* of the componenets that you are using, it is **important** that you know how to create a new one entirely from scratch as from time to time, you will be working with legacy or niche components, especially since at CAUV, we might be using very niche parts. It is recomended that you try to create a simple and common component from scratch so that you can compare your result with the standard symbol. In the following section, you will find very helpful tutorials on how to do so. 

After you have all the *schematic symbols*, or most of them as you can create them along the way, you will need to draw the *schematic* of the circuit. After that, you will need to look for *footprints* of each of the components that you have used. *Component footprints* are the drawings of how your component will look like and how it will be soldered onto the PCB. They should include things like *pins*, labels, component names, and etc. Again, it is vital that you know how to create a *footprint* from scratch and this is even more important as you will definitely come across components that have weird *foorprints* which cannot be found online. This is even more important than understanding how to draw *schematic symbols* because poorly drawn *footprints* will make it impossible to assemble your circuit because it is guaranteed that your component will not fit into the poorly drawn footprint. Again, the following section will direct you to good articles teaching how to learn it well. 

Finally, after you have the *footprints*, you will need to associate each of the footprints with the components that you have used and import them onto the PCB. After that, you will need to properly arrange the components (represented as their footprints) and *route* the connections. PCB *routing* should be done by hand as the auto-router will sometimes create problems, especially when the circuit is very sensitive to interferance and signal distortion. 

If you need to send the PCB to manufacturers, you will need to generate *gerber files*, which are basically instructions to tell manufacturers how to manufacture your PCB. 

The link https://hackaday.com/2016/09/21/creating-a-pcb-in-everything-introduction/ has more details on the basics of PCB design and you should read it if you have the time. 



## KiCad

### Great KiCad Tutorials
* http://docs.kicad-pcb.org/stable/en/getting_started_in_kicad.pdf
* https://hackaday.com/2016/11/17/creating-a-pcb-in-everything-kicad-part-1/
* https://hackaday.com/2016/12/09/creating-a-pcb-in-everything-kicad-part-2/
* https://hackaday.com/2016/12/23/creating-a-pcb-in-everything-kicad-part-3/
