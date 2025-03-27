# Ti-GPT by FusionTechWorks
**This Repository is a how-to guide associated with a YouTube video project to enable a Ti-Nspire CX or CX II with Chat-GPT utilizing an ESP32C3.**
LINK

## TI-Nspire CX Modification Guide

### Preparation and Disassembly:

#### Open the Battery Housing:
- Use a small Phillips screwdriver to remove the battery housing cover.
- Take out the panel and the battery to expose hidden safety screws.

#### Remove Hidden Screws:
- With a one-millimeter flathead screwdriver, remove the safety screws hidden under the battery cover.
- Check under the top rubber feet for additional hidden screws. Ignore the lower feet, as there are no screws there.

#### Remove Torx Screws:
- At the bottom of the calculator, remove the Torx T-6 screws.
- Keep all small parts in a safe place. Note that the CAS, CX II, and CX II CAS models have extra screws under the fascia.

#### Wedge Off the Rear Housing:
- Use guitar picks or similar pry tools to gently separate the rear housing from the body, working your way around the sides until the back pops off.

#### Prepare the Motherboard:
- Cover the lower motherboard face with vinyl or electrical tape to prevent any interference with the piggyback.

### Micro USB Port and Wiring:

#### Address Micro USB Port:
- Note that Texas Instruments reversed the pinout on the CX II; the labels are upside down. Be very careful when soldering to these pins.

#### Install Switches and Connector:
- Refer to the provided wiring diagram to install two switches—one for grounding the ID pin to enable host mode and the other as the main power switch for the piggyback.
- Add optional a magnetic connector to facilitate easy assembly and disassembly.

#### Adjust Internal Space:
- Use necessary tools to free up internal space as needed of the calculator to accommodate the piggyback and switches. Optionally add USB access to the ESP for debugging purposes while it's still in the case. Heres an example of mine.

### Software Installation and Configuration:

#### Download and Install Software:
- Download the TI-nspire CAS student software free trial and install it. Use this software to upload the .LUA file from the provided GitHub link to your calculator.

#### Setup API and Arduino:
- Follow the guide by Anders Jensen to create your ChatGPT API secret key. (GUIDE LINK)
- Download and install the Arduino IDE and the necessary drivers for your ESP model.
- Edit the .INO file from the GitHub repository to include your API secret key and Hotspot or Wi-Fi details. Note you for iphones enable "Maximise Compatibility" to allow your esp to connect in hotspot settings.

### Final Assembly and Testing:

#### Assemble and Check Clearances:
- Once all components are installed, close up the calculator by pressing firmly on the sides. Ensure there is enough clearance for all components.

#### Power Up and Configure:
- Boot up the calculator, go to the Home Screen, enable Host mode, and power the piggyback.

#### Open and Run Ti-GPT File:
- Open the Ti-GPT file in the calculator's document folder. Ensure the ESP has successfully connected to your hotspot.

#### Testing and Usage:
- Type into the textbox and hit enter. For short responses, they should appear immediately. For longer responses, you may need to hit enter again after a few seconds.

#### Troubleshooting:
- If you encounter errors, hit CTRL + W to quit the program. Try power cycling your piggyback and checking your wiring for any issues.

### Disclaimer:
I want to make it clear that this project is created for educational purposes and technological demonstration only. I do not condone academic dishonesty or the use of this project for cheating in any form. The tools and methods demonstrated in this project should be used responsibly and ethically. Misuse of this technology for bypassing academic regulations or dishonest practices is strictly against the principles this project upholds. Please use this technology to enhance learning and understanding, not to undermine it.

Additionally, I do not endorse or support the use of my project by others for financial gain by others. This project is open-sourced to foster innovation and learning within the community, not for commercial exploitation. Any reproduction or use of the project's content for profit without explicit permission is strictly prohibited. Please respect the spirit of collaboration and learning that this project is built upon.

### Refrences: 
ChromaLock YouTube, GitHub - Inspired by his innovative integration of ChatGPT into a TI-84.

ProfessorBoots YouTube, GitHub- Contributed code for ESP32 API communication.

CVSoft Cemetech, GitHub- Cracked the Nspire RXTX communication using a CP2102, vital for my setup.

AndersJensen YouTube - I used his guide to create a ChatGPT API secret key, key to my software configuration.

ti-nspire YouTube - Blog served as a reference and inspiration for my work.

CSab6482 Reddit - Provided crucial details about the reversed pinout on the Texas Instruments CX II.

### Thank You:
Thank you so much for watching and engaging with my project! With your support, I have exciting plans to further enhance this project. I aim to upgrade the LUA app to display WiFi settings and connectivity, introduce dynamic scrolling for chat responses, and fully integrate all the hardware onto a single PCB to make it more DIY-friendly and user-oriented. Additionally, I plan to implement some cosmetic upgrades to the calculator itself.

If you're interested in seeing these updates come to life and would like to help make them possible, please consider subscribing to my channel and liking and sharing the video. If you're feeling generous, your financial support would be greatly appreciated as the costs of development have been significant. This is my first project here, and I'm grateful for your patience and support throughout this journey. Thank you for being part of this adventure!
