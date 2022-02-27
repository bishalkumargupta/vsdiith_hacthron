# Design of CMOS based cascaded Phase Frequency Detector with Charge Pump and LPF.

## Table of Contents

- [Introduction](https://github.com/SoumitroV/Design-and-Simulation-of-a-Gilbert-Cell-based-Mixer-on-CMOS-28nm-Technology/edit/main/README.md#introduction)
- [Device Characterization](https://github.com/SoumitroV/Design-and-Simulation-of-a-Gilbert-Cell-based-Mixer-on-CMOS-28nm-Technology/edit/main/README.md#device-characterization)
- [Circuit Design](https://github.com/SoumitroV/Design-and-Simulation-of-a-Gilbert-Cell-based-Mixer-on-CMOS-28nm-Technology/edit/main/README.md#circuit-design)
- [Simulation Results](https://github.com/SoumitroV/Design-and-Simulation-of-a-Gilbert-Cell-based-Mixer-on-CMOS-28nm-Technology/edit/main/README.md#simulation-results)
- [Performance Comparison](https://github.com/SoumitroV/Design-and-Simulation-of-a-Gilbert-Cell-based-Mixer-on-CMOS-28nm-Technology/edit/main/README.md#performance-comparison)
- [Conclusion](https://github.com/SoumitroV/Design-and-Simulation-of-a-Gilbert-Cell-based-Mixer-on-CMOS-28nm-Technology/edit/main/README.md#conclusion)
- [Author](https://github.com/SoumitroV/Design-and-Simulation-of-a-Gilbert-Cell-based-Mixer-on-CMOS-28nm-Technology/edit/main/README.md#author) 
- [Acknowledgements](https://github.com/SoumitroV/Design-and-Simulation-of-a-Gilbert-Cell-based-Mixer-on-CMOS-28nm-Technology/edit/main/README.md#acknowledgements)
- [References](https://github.com/SoumitroV/Design-and-Simulation-of-a-Gilbert-Cell-based-Mixer-on-CMOS-28nm-Technology/edit/main/README.md#references)

## Abstract
CMOS based Phase Frequency Detector and charge
pump is being Simulated and recorded on 28nm technology. LPF
is also being cascaded and being studied. Phase frequency
Detector plays a most important role in a PLL. PFD decides the
performance and accuracy of a PLL. Charge pump is also a major
block for a PLL which translate frequency and phase into voltages
used to tune VCO. PLL act as clock generator and is a non-linear
feedback system that tracks the phase of the input signal and
minimise the phase error at the local oscillator. PLL has a wide
range of application in modern and conventional electronics and
communication technologies, such as frequency synthesizers, FM
and AM coherent demodulation analysis and more.

## Introduction

  Phase Lock Loop (PLL)  is the most important block of any clocking system of circuit design and comprise essential applications which includes synchronization of cock in communication system, RF applications , wireless devices, day to day modern electronic equipments. PLLs consists of many blocks where the major ones are Phase Frequency Detector(PFD), Charge Pump(CP), Low Pass Filter(LPF), Voltage Controled Oscillator(VCO) and Frequency Divider. PFD is the major block of a frequency synthesiser.</br> A PFD compares the two input signals, i.e. reference input and feedback input as shown in Fig. 1. Depending upon the phase difference, PFD generates either UP signal or DOWN signal. This signal drives CP which produces a current pulse with corresponding duty ratio.
  </br>CP circuit consists of a Pull up and Pull-Down network. Charge pump maintain constant output with a varying voltage which later is used to tune the VCO. In Fig. (3) Inputs “UP” and “Down” control the Switches S1and S2 respectively. A pulse of width dT Up turns S1on for dT sec, availing I1 to charge C1. Vout goes up by dT*I1/C1. With same phenomena, Down pulse gives a drop in Vout. If Up and Down are provided simultaneously, I1flows through S1and S2 as I2, resulting into Vout unchanged.


<p align="center">
<img src="https://user-images.githubusercontent.com/86653033/155875626-d3c9baf2-c100-4356-9b3e-5915b943f3ab.png">
</p>
<p align="center">
Fig 1. (a) Cascaded PFD/CP/LPF circuit diagram (b) Transmission gate based DFlipFlop
</p>

## Expected waveform
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155875851-5accd622-1326-48ef-a9a8-ed6f0b9c7db1.png">
  </p>
  <p align="center">
  Waveform of cascaded PFD and CP
  </p>

## Circuit implementation of PFD block.
This is the CMOS circuit implementation of AND Gate(Fig. (a) and NOR Gate( Fig. (b))
<p align="center">
 

<img src ="https://user-images.githubusercontent.com/86653033/155877048-11139395-caa8-4afc-9cb7-968f24b1d0d1.png">
  </p>
This the D latch(modified) implementation where NOT gate is instantiated after symbolising the design in Synopsys tool</br>
<br/>
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155876934-b2091c79-58f7-4a90-a96c-a6028b1dbbe7.png">
  </p>
This the PFD block which is implemented using D Latch and And Gate for providing Reset (R) control and the UP output is denoted by "QA" and DOWN is represented by "QB". ans is further symbolized using the tool.</br> CLKA represents the Reference clock</br> CLKB represens the Feedback signal </br>

 <p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155877443-36e258a4-d65e-4ce1-8f64-b23a9a946abd.png">
</p>

</br>This is the circuit implementation of Charge Pump whis is further connected to LPF block</br>
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155877668-0f029bb0-786a-4fd6-a104-38a2dcd56c71.png">
</p>

</br>This is the cascaded implementation of the PFD/CP/LPF combined</br>
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155877912-5ed679a1-8697-4ca4-8e7f-2ed804bb54b8.png">
</p></br>


  
 
 


## Simulation Results
Case1:- When Reference clock(CLKA) leads Feedback Clock(CLKB)</br>
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155878058-63e6187c-8019-433f-af11-beed874268b8.png">
</p></br>
 Case2:- When CLKA lags CLKB</br>
 <p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155878125-98fee578-135e-400f-a002-093a4ce1d658.png">
</p></br>
Considering Case1 , when CP and LPF is being cascaded with the PFD block the simulation result is being pfovided</br>
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155879176-d372f11a-0f8d-4b15-855b-d848a26013f6.png">
</p></br>


## Performance Comparison

|               |      [1]      |      [2]      |   This work   |
|     :---:     |     :---:     |     :---:     |     :---:     |
|     Vdd (V)   |      5.0      |      1.2      |      1.8      |
|Frequency (GHz)|     0.433     |      4.0      |     0.45      |
|Technology (nm)|      700      |      180      |      28       |
|     Gain      |      3.35     |      1.3      |     1.015     |
|  Power (mW)   |       3       |      7.1      |      0.54     |
|Chip Size (mm sq)|       -       |      0.82      |      -     |

The table presents performance comparison with previously done work in literature. A clear trade off between gain and power can be observed here. The chip area can be determined with post layout measurements and is expected to be smaller than higher technology nodes.

## Conclusion

The repository presents the design and simulation of CMOS based 28nm Technoogy for CP block being cased with PFD and LPF Blocks. 

## Author

Bishal Kumar Gupta, M.tech at Defence INstitute of Adanced Technology-DRDO with specialization in VLSI and Embedded Systems.

## Acknowledgements

- [Kunal Ghosh, Co-founder, VSD Corp. Pvt Ltd.](https://www.linkedin.com/in/kunal-ghosh-vlsisystemdesign-com-28084836?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3B0xcWjpLDThSEo6S9UPO9Tw%3D%3D)
- Chinmay Panda, IIT Hyderabad
- [Synopsis Team/Company](synopsys.com/company/contact-synopsys/office-locations/india/about-synopsys-india.html)
- [IIT Hyderabad](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)
- Active and vibrant hackathon community

## References

[1] I. Galton, B. Razavi, J. Cowles and P. Kinget, "CMOS phase-locked
loops for frequency synthesis," 2010 IEEE International Solid-State
Circuits Conference - (ISSCC), 2010, pp. 521-521, doi:
10.1109/ISSCC.2010.5433853.</br>
[2] H. Dadhich, V. Maurya, K. Verma and S. Jaiswal, "Design and analysis
of different type of charge pump using CMOS technology," 2016
International Conference on Advances in Computing, Communications
and Informatics (ICACCI), 2016, pp. 294-298, doi:
10.1109/ICACCI.2016.7732062.</br>
[3] RF Microelectronics Textbook written by Behzad Razavi.</br>
[4] Won-Hyo Lee, Jun-Dong Cho and Sung-Dae Lee, "A high speed and
low power phase-frequency detector and charge-pump," Proceedings of
the ASP-DAC '99 Asia and South Pacific Design Automation
Conference 1999 (Cat. No.99EX198), 1999, pp. 269-272 vol.1, doi:
10.1109/ASPDAC.1999.760011.</br>

