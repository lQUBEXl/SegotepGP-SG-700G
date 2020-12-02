# Table of Contents
1. [Listing](#listing)
2. [Packaging](#packaging)
3. [Exterior](#exterior)
4. [Interior](#interior)
5. [First Impressions](#first-impressions)
6. [Simplified Component List](#simplified-component-list)

## Segotep GP600G (as listed, but should be SX-700G product line)
600w continuously rated, Gold efficiency, Non-modular unit from Segotep that is listed for both $50 USD on both [Amazon](https://www.amazon.com/dp/B0832KN3RV/ref=twister_B08G1G6MLF?_encoding=UTF8&th=1) and [Newegg](https://www.newegg.com/segotep-gp-series-600w-non-modular/p/1HU-00Z0-00008). The listing shows GP600G while the product label shows SX-700G, of which we will see down below.

## Packaging
The packaging isn't anything spectacular, but it does seem to be well presented.   
![The packaging isn't anything spectacular, but it does seem to be well present.](https://i.imgur.com/fT7dhd6.jpg)
![The packaging isn't anything spectacular, but it does seem to be well present.](https://i.imgur.com/2qK8oeF.jpg)
![The packaging isn't anything spectacular, but it does seem to be well present.](https://i.imgur.com/6t4ELTl.jpg)
![The packaging isn't anything spectacular, but it does seem to be well present.](https://i.imgur.com/Wf0lfl5.jpg)
![The packaging isn't anything spectacular, but it does seem to be well present.](https://i.imgur.com/BmiWzhh.jpg)
![The packaging isn't anything spectacular, but it does seem to be well present.](https://i.imgur.com/3ezyU6F.jpg)
![The packaging isn't anything spectacular, but it does seem to be well present.](https://i.imgur.com/p1aJ9BA.jpg)
![The packaging isn't anything spectacular, but it does seem to be well present.](https://i.imgur.com/j4FvsMY.jpg)
And it comes with some zipties...Nice!

## Exterior
So now we will actually touch the unit and check out what it feels like.
![So now we will actual touch the unit and check out what it feels like](https://i.imgur.com/aZcxsz1.jpg)
![So now we will actual touch the unit and check out what it feels like](https://i.imgur.com/cX0FfqT.jpg)
![So now we will actual touch the unit and check out what it feels like](https://i.imgur.com/QmQVILP.jpg)
![So now we will actual touch the unit and check out what it feels like](https://i.imgur.com/FFRXQCr.jpg)
![So now we will actual touch the unit and check out what it feels like](https://i.imgur.com/ixy8JGx.jpg)
![So now we will actual touch the unit and check out what it feels like](https://i.imgur.com/V4yfSuT.jpg)
![So now we will actual touch the unit and check out what it feels like](https://i.imgur.com/ZVR9jDO.jpg)

## Interior 
Now the fun begins...We open the unit up to find it is Half-Bridge (LLC Resonant) topology with synchronous rectification (SR) & DC-DC converters (regulation)--nice.
![](https://i.imgur.com/8iMVvgp.jpg)
![](https://i.imgur.com/8CCMvuo.jpg)
Strange piece of somewhat "dried" plastic was in the unit...Interesting.
![](https://i.imgur.com/Td9uub4.jpg)
![](https://i.imgur.com/qMq45k7.jpg)
![](https://i.imgur.com/m4q578r.jpg)
![](https://i.imgur.com/4jYJg2M.jpg)
![](https://i.imgur.com/34tJzQv.jpg)
The backside PCB is different than that of the Enermax Platimax 600w. While the Supervisor IC and 12v MOSFETs on the secondary side are soldered onto the back, on this Segotep unit, they are soldered on the front side with the Supervisor IC being oddly placed.
![](https://i.imgur.com/oT0qB0m.jpg)
The supervisor IC (Infinno ST9S313-SAG) is placed right under the AC plug in the filtering stage
![](https://i.imgur.com/jcTDXrg.jpg)
There are four 12v rail MOSFETs between the filtering capacitors and heatsinks we see here
![](https://i.imgur.com/VoW90Cb.jpg)
The LLC resonant controller (CM6901X) is also placed on the front
![](https://i.imgur.com/XdB55tq.jpg)
Here we see the minor rail MOSFETs (NCE3080K) and PWM controllers (Anpec APW7073A) that control them
![](https://i.imgur.com/tODsNEF.jpg)
![](https://i.imgur.com/isia49J.jpg)
Disassembly of fan
![](https://i.imgur.com/lm8dyQM.jpg)
The fan bearing is confirmed to be rifle

# First Impressions
Secondary side capacitors are sometimes different from the product listing and sometimes different from the reviews online. The thermal pads on DC to DC converter coils are haphazardly placed on, and so is the soldering on the PCB backside (The supervisor IC is on the front). We have an off the shelf easy-to-insert ferrite choke on the filtering stage. Rather than two X ceramic capacitors before our inductors, we have a single large, black, ceramic capacitor before the bridge rectifier. A nice note is that the bulk capacitor primarily known for increasing hold-up time has been improved from the reviews to one from CapXon.

# Simplified Component List
  | Primary Side            |:-:|
  | :-:                     |:-:|
  | Transient Filter        | 3x Y ceramic caps, 3x X ceramic caps, 2 CM choke, 1 MOV |
  | Inrush Protection       | NTC Thermistor & Diode (16A, 250VAC) |
  | Bridge Rectifier        | TBD |
  | APFC MOSFETs            | 1x Great Power [GP28S50X-TO247](https://alltransistors.com/pdfdatasheet_champion/gp28s50.pdf) (28A, [15A @ 0.125Ω], 400 V) |
  | APFC Boost Diode        | 1x Champion Microelectronic [PFCD86G](https://datasheet4u.com/datasheet-pdf/ChampionMicroelectronic/CMPFCD86/pdf.php?id=938654) (8A, 600 V) |
  | Hold-up Cap             | 1x CapXon (390μF, 420 V, 2000h @ 105 C) |
  | Main Switchers          | 2x IPS InPower Semiconductor Co. TA20N50A |
  | Topology                |  Primary Side: Half-Bridge & LLC Resonant Controller & Secondary Side: Synchronous Rectification & DC-DC converters |


  | Secondary Side          | :-: |
  | :-:                     | :-: |
  | Filtering Capacitors    | CapXon (4x 2200μF, 6V)/(2x 3300μF, 16V)/(2x 2000μF, 10V)  |
  | Supervisor IC           | Infinno ST9S313-SAG IC (OVP/UVP/SCP/PG--No OTP) |
  | Minor Rail PWM Controllers         | 2x Anpec APW7073A PWM controllers |
  | Minor Rail MOSFETs (controlled by PWM) | 4x [NCE3080K](https://datasheet.lcsc.com/szlcsc/Wuxi-NCE-Power-Semiconductor-NCE3080K_C108901.pdf)
  | 12v Rail MOSFET | (Unknown) SG40N01LQ 2003005 (40V, 100A) |
  | LLC Resonant Controller | CM6901X |
  | Fan Model               | EFS-12E12H (120mm, 12 V, 0.5A,  rifle bearing) |
