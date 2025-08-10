
# Summer Internship Program on Analog IC Design

*Student Experience \& Resource Repository*

---

## Introduction

Welcome to my repository for the **Summer Internship Program on Analog Integrated Circuit (IC) Design**. I’m an Electrical and Electronics Engineering student who just completed this program, and I’m excited to share my experience, the knowledge I gained, and some resources you’ll need if you’re interested in Analog IC Design.

---

## Why I Took This Program

I joined this internship because I wanted to bridge the gap between theory and real-world circuit design, especially using **CMOS technology** and **open-source EDA tools**. The course promised hands-on projects, exposure to industry-standard tools, and a chance to work on a real analog front-end for a USB-MIDI microphone—and it delivered!

---

## What I Learned

### Core Concepts

- **CMOS Device Physics:** From pn junctions to MOSFET operation, I now understand how transistors work at the fundamental level.
- **Analog Building Blocks:** Designed current mirrors, differential pairs, and cascode amplifiers from scratch.
- **Circuit Simulation \& Layout:** Used open-source tools like **ngspice**, **xschem**, and **siliwiz** and **magic** for schematic capture, simulation, and layout.
- **System Design:** Got to see how analog blocks fit into a real application (USB-MIDI microphone front-end).


### Tools Mastered

- **ngspice:** For simulating analog circuits.
- **xschem:** For drawing schematics.
- **siliwiz and magic:** For IC layout.

---

## Program Structure

- **Duration:** 3 weeks (100 hours)
- **Format:** Lectures (theory) and project for hands-on experience
- **Batch Size:** Around 50 students (great for interaction and personalized guidance)


### Week-by-Week Breakdown

| Week | Focus Areas |
| :-- | :-- |
| 1 | Linear circuits, passive devices, intro to MOSFETs, basic simulations |
| 2 | MOS device physics, analog building blocks, advanced simulation |
| 3 | Full analog IC design (Skywater 130nm), layout, PCB design, testing |


---

## My Project

I worked on designing and simulating the **analog front-end for a USB-MIDI microphone**. This involved:

- Creating the schematic in xschem
- Running simulations in ngspice
- Laying out the design in siliwiz and magic
- Preparing for fabrication using the TinyTapeout platform

- <img width="1350" height="1080" alt="20250810_160330_0000" src="https://github.com/user-attachments/assets/e9aba8d1-fa16-455a-a06a-8fc74a610912" />

**USB Microphone Teardown:**
<img width="1280" height="557" alt="Fig-d1-2-micTeardown" src="https://github.com/user-attachments/assets/93e2e6d6-2d24-4b65-b7be-b6b270541691" />

**USB Microphone System:**
<img width="1280" height="666" alt="Fig-d1-1-USBmic" src="https://github.com/user-attachments/assets/2f372266-b600-4022-9476-7dc06cb2f1eb" />

- [Video](https://youtu.be/iuqNuaLUez4): Introduction to Xschem


**THEVENIN MODEL of MICROPHONE**

**Key specs** from the microphone [datasheet](https://cdn.sparkfun.com/assets/0/5/8/b/1/SPH8878LR5H-1_Lovato_DS.pdf) and research:
- Sensitivty: -44 dBV/Pa
- Condition: 94 dB SPL at 1 kHz which is sound pressure of 1 Pa
- Normal voice conversation is typically 60 dB SPL
- **Vth Calculation**
  - Voice (Pa) = $10^{(60-94)/20} = 19.9\times 10^{-3} Pa$
  - Output (Vpk) = $\sqrt{2}\times V_{rms} = \sqrt{2}\times 19.9\times 10^{-3} Pa \times 10^{-44/20} = 178 \mu Vpk$
  - **$V_{out-pk} = 0.178~ mV$**
- **Rth** (from datasheet) = 380 ohms


- [link to Sparkfun Schematic of the breakout board](https://cdn.sparkfun.com/assets/7/5/6/e/d/SparkFun_Analog_MEMS_Microphone_Breakout_SPH8878LR5H-1.pdf)
- From Sparkfun schematic: Rin=5k, Rfb=300k, therefore Gain = 60
- So output of the amplfier will be 60x0.178 mVpk = **10.68 mVpk**
- Sparkfun site states **100 mVpk** probaby assuming 10 times higher input signal i.e. Voice is **80 dB SPL**
- Input high-pass frequency = $1/2\pi RC = 1/2\pi 5k 4.7uF = 6.77 Hz$
- Feedback Low-pass filter frequency = $1/2\pi RC = 1/2\pi 300k 27pF = 19.6kHz $
- Input common-mode filter = $1/2\pi 10k 1uF = 15.9 Hz$


**Single-Pole Model of OPA 344**

- Specs from the [OP344 Datasheet](https://www.ti.com/lit/ds/symlink/opa344.pdf?ts=1747822666491&ref_url=https%253A%252F%252Fwww.google.com%252F):
  - Open Loop DC Gain: **120 dB** (From p-5 graph)
  - Unity Gain Frequency: **1 MHz**
- Pole = $1 MHz/10^6 = 1~Hz$

**Microphone AFE Analysis**

<img width="2159" height="2289" alt="Fig-d2-1-mic-analysis" src="https://github.com/user-attachments/assets/8269c37d-1345-43a9-9134-58b7110029ef" />



You’ll find my project files in the `/projects` folder, including simulation data and my final report.
Also, you'll find some important documents in the `/resources` folder.

---


## Highlights \& Takeaways

- **Hands-on Learning:** Every concept was backed by a lab or project.
- **Open-Source Tools:** No expensive licenses—everything is accessible.
- **Industry Insight:** Sessions with experts from Synopsys and academia.
- **Collaboration:** Worked closely with peers and mentors.

- <img width="1080" height="1350" alt="20250810_160330_0001" src="https://github.com/user-attachments/assets/6f5bb59d-a4a9-4101-b488-900a587fbca3" />



---


## Acknowledgements

Big thanks to **Dr. Saroj Rout**, **Mr. Prasant Swain**, and **Mr. Mrinal Das** for their mentorship and guidance.

---

## License

All materials are for educational use. Please credit the original authors and contributors if you use or share them.

---

**Happy designing and learning!**
*Feel free to fork this repo, raise issues, or contribute your own projects and notes!*

