# RGB AddOn 
So, this is a back case model,for phones which have built or can also have attach a MagSafe ring at the back of the phone .
It features a 12 x 16 RGBLED matrix which can be used to present anything from notifications ,alerts ,incoming calls ,animations or even some cool games.
The help us to control the over-usage of phone and it also helps to limit our Screen Time , by providing all the important notifications at the back of the phone.

# Components 
SK9822-EC20:-
 It's a 2x2mm package SPI interface GRB (yeah its green red and blue not the regular RGB idk why) with a max       current rating of 20mA and operating voltage of 3.7V ~ 5.5V range .
 It's good and efficient for this project . I will be using 216 of these i.e 12 row x 18 column configuration      with 5mm pitch , overall the module size would be 65mm × 95mm!

![20230121_OPSCO-Optoelectronics-SK9822-EC20_C2909059_front](https://github.com/user-attachments/assets/3353b747-cbe1-4a27-9cdb-293154e60a7c)

XIAO ESP32-C3:-
 It has the best specs for this project .
 it features both wifi & bluetooth and has a inbuilt limo charging system and supports SPI and many 
<img width="500" height="636" alt="board-pic" src="https://github.com/user-attachments/assets/d75fac40-f43c-42e7-9197-f2a3ddb37fb6" />

MT3608:-
  It's a setup converter from 3.7v (bat) to 5v to power the RGB Led's
  ![2310](https://github.com/user-attachments/assets/8aa9f7b9-04f3-46b5-9a07-d850ddea43c4)

LiPo:-
  I will be using two of these 3.7v 400mah  1S lipo cell's of dimensions 30x40x3mm to Power the whole              contraption. 

# Schematics
It has two sheets:-
1) Matrix:
 The pinout of SK9822-EC20 is simple just 6 pin which are SDI AND CKL for data in and SDO and CKO for data out    and a vcc & gnd .
 <img width="769" height="383" alt="Screenshot 2026-03-03 at 3 29 32 AM" src="https://github.com/user-attachments/assets/8cbbb67a-e916-431b-997b-8d49326877bd" />
 The first led has a 330ohm resister between the MCU and led to protects MCU from signal reflection , then rest   off the led are connected as followed SDO->SDI , CKO->CKI in a series and the power lines are parallel with a    100nf capacitor in each row .
<img width="859" height="363" alt="Screenshot 2026-03-03 at 4 00 48 AM" src="https://github.com/user-attachments/assets/eff0fe6e-5676-4d0b-bb92-fdd3e147cac8" />


2) MCU:
XIAO ESP32-C3 and a boost converter MT3608 connections 
->MCU
  SDI->D10
  CKI->D8
  EN->D6 (MT3608 turn on off switch )
  BAT+->VBAT
  BAT-->AGND

->MT3608
  IN->VBAT
  GND->AGND
  SW->+5V
  rest according to the datasheet
  <img width="568" height="207" alt="Screenshot 2026-03-03 at 4 00 57 AM" src="https://github.com/user-attachments/assets/8522cde0-db02-4158-8629-b5959eaadc8c" />

# PCB
 It's a 2 layer 0.8 MM pcb 
  The top layer
   <img width="326" height="454" alt="Screenshot 2026-03-03 at 4 05 48 PM" src="https://github.com/user-attachments/assets/23f90b16-6e14-4939-a502-cb990f2093cc" />

  The bottom layer
  <img width="297" height="425" alt="Screenshot 2026-03-03 at 4 06 15 PM" src="https://github.com/user-attachments/assets/02554776-36b9-4d8d-a997-a5cadf0f56de" />

  The rendering 
  <img width="729" height="677" alt="Screenshot 2026-03-03 at 4 07 37 PM" src="https://github.com/user-attachments/assets/ec9d34fc-aa7f-4662-80ae-64b07e3077ba" />

  
<img width="741" height="660" alt="Screenshot 2026-03-03 at 4 07 51 PM" src="https://github.com/user-attachments/assets/9afc0d16-a176-45d7-aad1-bfcf18ac9a25" />

 Both the top and bottom layers have gnd as copper filled region and battery pad at the bottom layer 

# CAD
 I've used fusion 360 to create a very simple minimalistic housing for the PCB and batteries and also some clamps to hold the PCB to the case. The top part of the case will be a frost, a frosty acylric sheet of 1MM 
 Glued on top using epoxy.
<img width="2880" height="1226" alt="Untitled_2026-Mar-03_09-14-38AM-000_CustomizedView27208638340_png" src="https://github.com/user-attachments/assets/d4709cb8-644b-4f3a-a0eb-2e4322888b47" />
<img width="2880" height="1226" alt="Untitled_2026-Mar-03_09-15-18AM-000_CustomizedView28997941230_png" src="https://github.com/user-attachments/assets/a2067b0f-1c24-41f4-88ee-828088ba3404" />


# Assembly
 <img width="803" height="387" alt="Screenshot 2026-03-03 at 3 33 47 PM" src="https://github.com/user-attachments/assets/5409f0fc-d62c-48e4-b3f1-621191cde5a7" />

 It's very simple to assemble just place the battery first, and then the PCB goes in its socket and then clamp it down to lock its position at that place and then the acrylic sheet is glued on top.
 Also, we need to attach a magsafe ring at the back.


  


 
