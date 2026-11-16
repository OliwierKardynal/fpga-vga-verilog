---
layout: home
title: FPGA VGA Driver Project
tags: fpga vga verilog
categories: demo
---
Welcome to my FPGA VGA project! This Verilog design runs on the Basys3 board and outputs a 640×480 @ 60 Hz picture.
It uses a sync generator for the timing, a colour stripe module for the pattern, and a top module that ties it together.

## **Template VGA Design**
<img src="https://github.com/OliwierKardynal/fpga-vga-verilog/blob/main/docs/assets/images/1000022117.png?raw=true">

## **Project Set-Up**
The project was created in Vivado for the Basys3 board (Artix-7 xc7a35tcpg236-1) with VGATop as the top module.
The design sources are VGATop.v, VGASync.v (horizontal and vertical counters that generate hSync, vSync and the vid_on visible-area flag) and VGAColourStripes.v (eight 80-pixel-wide colour bars chosen from the column count). A Clocking Wizard IP (clk_wiz_0) converts the board’s 100 MHz clock to the 25 MHz pixel clock. Basys3_Master.xdc was added as the constraints file to assign the clock, reset switch and VGA pins and set LVCMOS33 I/O standards. The testbench was run in simulation to check the sync timing. 
The design then went through synthesis, implementation and bitstream generation, and the resulting .bit file was programmed onto the board through Hardware Manager.
 This produced eight vertical colour stripes at 640×480 on the monitor.

<img src="https://raw.githubusercontent.com/melgineer/fpga-vga-verilog/main/docs/assets/images/VGAPrjSum.png">
### **Template Code**
Outline the structure and design of the Verilog code templates you were given. What do they do? Include reference to how a VGA interface works. Guideline: 2/3 short paragraphs, consider including screenshot(s).
### **Simulation**
Explain the simulation process. Reference any important details, include a well-selected screenshot of the simulation. Guideline: 1/2 short paragraphs.
### **Synthesis**
Describe the synthesis and implementation processes. Consider including 1/2 useful screenshot(s). Guideline: 1/2 short paragraphs.
### **Demonstration**
Perhaps add a picture of your demo. Guideline: 1/2 sentences.

## **My VGA Design Edit**
Introduce your own design idea. Consider how complex/achievabble this might be or otherwise. Reference any research you do online (use hyperlinks).
### **Code Adaptation**
Briefly show how you changed the template code to display a different image. Demonstrate your understanding. Guideline: 1-2 short paragraphs.
### **Simulation**
Show how you simulated your own design. Are there any things to note? Demonstrate your understanding. Add a screenshot. Guideline: 1-2 short paragraphs.
### **Synthesis**
Describe the synthesis & implementation outputs for your design, are there any differences to that of the original design? Guideline 1-2 short paragraphs.
### **Demonstration**
If you get your own design working on the Basys3 board, take a picture! Guideline: 1-2 sentences.

## **More Markdown Basics**
This is a paragraph. Add an empty line to start a new paragraph.

Font can be emphasised as *Italic* or **Bold**.

Code can be highlighted by using `backticks`.

Hyperlinks look like this: [GitHub Help](https://help.github.com/).

A bullet list can be rendered as follows:
- vectors
- algorithms
- iterators

Images can be added by uploading them to the repository in a /docs/assets/images folder, and then rendering using HTML via githubusercontent.com as shown in the example below.

<img src="https://raw.githubusercontent.com/melgineer/fpga-vga-verilog/main/docs/assets/images/VGAPrjSrcs.png">
