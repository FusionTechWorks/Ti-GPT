# Ti-GPT by FusionTechWorks <img width="42" alt="Screenshot 2025-03-27 at 5 01 29 PM" src="https://github.com/user-attachments/assets/e601bfaa-11de-4ee2-ac2a-95db41efcc50" />

**This Repository is a how-to guide associated with a YouTube video project to enable a Ti-Nspire CX (or CX II) with Chat-GPT utilizing an ESP32C3 and native .LUA app.**
LINK

## TI-Nspire CX Modification Guide

### Preparation and Disassembly:

#### Determine Calculator Model
-There are two generations of the CX the first of which I was not able to get the drivers working. The model with the most space is the 2nd generation CX although the CX II does work. They are easily distinguishable, take a look at my video for more info. THe CX gen 1 has a larger battery cover than the CX gen 2. The CX gen 2 and CX II have obvious different lables. Same logic follows through for the CAS variants of all these.
<img width="762" alt="Screenshot 2025-03-28 at 9 26 06 AM" src="https://github.com/user-attachments/assets/fd3b9a37-63cf-49bd-a516-ea53ebb3c1ad" />
<img width="269" alt="Screenshot 2025-03-28 at 9 30 49 AM" src="https://github.com/user-attachments/assets/2c23bc80-d546-41c3-9b8f-1d1c22197ea7" />


#### Open the Battery Housing:
- Use a small Phillips screwdriver to remove the battery housing cover.
- Take out the panel and the battery to expose hidden safety screws.
<img width="538" alt="Screenshot 2025-03-27 at 4 37 32 PM" src="https://github.com/user-attachments/assets/d7f32721-48a1-4765-b94e-82c22668a43f" />


#### Remove Hidden Screws:
- With a one-millimeter flathead screwdriver, remove the safety screws hidden under the battery cover.
- Check under the top rubber feet for additional hidden screws. Ignore the lower feet, as there are no screws there.
<img width="289" alt="Screenshot 2025-03-27 at 4 43 18 PM" src="https://github.com/user-attachments/assets/e1fcf943-82b6-475a-b17e-463cdc8429da" />
<img width="335" alt="Screenshot 2025-03-27 at 4 38 57 PM" src="https://github.com/user-attachments/assets/722ee76c-1327-44f4-a63b-e05dea1c0b29" />


#### Remove Torx Screws:
- At the bottom of the calculator, remove the Torx T-6 screws.
- Keep all small parts in a safe place. Note that the CAS, CX II, and CX II CAS models have extra screws under the front fascia.
<img width="243" alt="Screenshot 2025-03-27 at 4 39 34 PM" src="https://github.com/user-attachments/assets/e481bb73-95d8-4546-8a15-f7afb344643f" />

#### Wedge Off the Rear Housing:
- Use guitar picks or similar pry tools to gently separate the rear housing from the body, working your way around the sides until the back pops off.
<img width="423" alt="Screenshot 2025-03-27 at 4 40 15 PM" src="https://github.com/user-attachments/assets/8f25f642-39d9-4aa7-8a43-59c65f6647bb" />

#### Prepare the Motherboard:
- Cover the lower motherboard face with vinyl or electrical tape to prevent any interference with the piggyback.
<img width="522" alt="Screenshot 2025-03-27 at 4 40 53 PM" src="https://github.com/user-attachments/assets/a0dd5692-d11a-464b-9b5f-627da6b24cdd" />

### Micro USB Port and Wiring:

#### Address Micro USB Port:
- Note that Texas Instruments reversed the pinout on the CX II; the labels are upside down. Be very careful when soldering to these pins.
<img width="434" alt="Screenshot 2025-03-27 at 4 44 14 PM" src="https://github.com/user-attachments/assets/aa482438-99f0-4fe7-90e1-2dcdc5a427e5" />
<img width="214" alt="Screenshot 2025-03-27 at 4 44 27 PM" src="https://github.com/user-attachments/assets/ba037720-3170-453b-94d1-d6da575a069f" />

#### Solder and Install Piggyback, Switches, and Connector:
- Refer to the provided wiring diagram to install two switches—one for grounding the ID pin to enable host mode and the other as the main power switch for the piggyback.
- Add optional a magnetic connector to facilitate easy assembly and disassembly.
- Note pinout lables are reversed for the CX II
- Note between ESP32 and CP2102 RX -> TXD, TX -> RXD in UART communication protocol but between Ti-nspire motherboard and CP2102 D+ -> D+, and D- -> D- in USB communication protocol.
<img width="1427" alt="Screenshot 2025-03-27 at 11 05 36 PM" src="https://github.com/user-attachments/assets/a837bfc3-31a8-47c1-bb90-9fe1b2f05daa" />

#### Adjust Internal Space:
- Use necessary tools to free up internal space as needed of the calculator to accommodate the piggyback and switches. Optionally add USB access to the ESP for debugging purposes while it's still in the case. Heres an example of mine.

### Software Installation and Configuration:

#### Download and Install Software:
- Download the TI-nspire CAS student software free trial and install it. Use this software to upload the .LUA file from the provided GitHub link to your calculator.
https://education.ti.com/fr/software/details/en/B4F6E4EE05B94D75AAB4DFE24B2720AE/ti-nspirecxcas_pc_trial

#### Setup API and Arduino:
- Follow the guide by Anders Jensen to create your ChatGPT API secret key. (GUIDE LINK)
- Download and install the Arduino IDE and the necessary drivers for your ESP model.
- Edit the .INO file from this repository to include your API secret key and Hotspot or Wi-Fi details. Note for iphones enable "Maximise Compatibility" to allow your esp to connect in hotspot settings.
<img width="381" alt="Screenshot 2025-03-27 at 4 56 32 PM" src="https://github.com/user-attachments/assets/761720f0-852a-4033-849f-2fa0f557dcdb" />

### Final Assembly and Testing:

#### Assemble and Check Clearances:
- Once all components are installed, close up the calculator by pressing firmly on the sides. Ensure there is enough clearance for all components.

#### Power Up and Configure:
- Boot up the calculator, go to the Home Screen, enable Host mode via the first switch, and then power the piggyback bia the second switch.

#### Open and Run Ti-GPT File:
- Open the Ti-GPT file in the calculator's document folder. Ensure the ESP has successfully connected to your hotspot.

#### Testing and Usage:
- Type into the textbox and hit enter. For short responses, they should appear immediately. For longer responses, you may need to hit enter again after a few seconds.

#### Troubleshooting:
- If you encounter errors, hit CTRL + W to quit the program. Try power cycling your piggyback and checking your wiring for any issues. ALWAYS disconnect power and host/ID pin when not in use. Esp can get pretty hot in there under load or if on/idle too long. Please watch the step by step on Youtube and leave a comment if you are facing issues and I will do my best to respond.

### Disclaimer:
I want to make it clear that this project is created for educational purposes and technological demonstration only. I do not condone academic dishonesty or the use of this project for cheating in any form. The tools and methods demonstrated in this project should be used responsibly and ethically. Misuse of this technology for bypassing academic regulations or dishonest practices is strictly against the principles this project upholds. Please use this technology to enhance learning and understanding, not to undermine it.

Additionally, I do not endorse or support the use of my project by others for financial gain by others. This project is open-sourced to foster innovation and learning within the community, not for commercial exploitation. Any reproduction or use of the project's content for profit without explicit permission is strictly prohibited. Please respect the spirit of collaboration and learning that this project is built upon.

### Refrences: 
- ChromaLock YouTube, GitHub - Inspired by his innovative integration of ChatGPT into a TI-84.
https://www.youtube.com/@ChromaLock
- ProfessorBoots YouTube, GitHub- Contributed code for ESP32 API communication.
https://github.com/ProfBoots/ChatGPT-On-Arduino
- CVSoft Cemetech, GitHub- Cracked the Nspire RXTX communication using a CP2102, vital for my setup.
https://github.com/CVSoft/nspire-usb-uart-shenanigans
- AndersJensen YouTube - I used his guide to create a ChatGPT API secret key, key to my software configuration.
https://www.youtube.com/watch?v=OB99E7Y1cMA&ab_channel=AndersJensen
- ti-nspire YouTube - Blog served as a reference and inspiration for my work. (videos and blog went unlisted :/ )
https://www.youtube.com/@ti-nspire301
- CSab6482 Reddit - Provided crucial details about the reversed pinout on the Texas Instruments CX II.
https://www.reddit.com/r/UsbCHardware/comments/y2dbkf/tinspire_cx_ii_cas_usbc_mod_v2/
### Thank You:
Thank you so much for engaging with my project! With your support, I have exciting plans to further enhance this project. I aim to upgrade the LUA app to display WiFi settings and connectivity, introduce dynamic scrolling for chat responses, and fully integrate all the hardware onto a single PCB to make it more DIY-friendly and user-oriented. Additionally, I plan to implement some cosmetic upgrades to the calculator itself as well as more from your feedback on youtube!

If you're interested in seeing these updates come to life and would like to help make them possible, please consider subscribing to my channel and liking and sharing the video. If you're feeling generous, your financial support would be greatly appreciated as the costs of development have been significant. This is my first project here, and I'm grateful for your patience and support throughout this journey. Thank you for being part of this adventure!
