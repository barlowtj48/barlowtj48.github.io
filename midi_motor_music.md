# MIDI Stepper Motor Music

An open-source project that turns stepper motors into musical instruments using MIDI. Import any MIDI file into the DAW of your choice, output it to an Arduino, and use attached stepper motors as frequency generators to play music.

**[See it in action on TikTok](https://www.tiktok.com/@bar_low/playlist/Motor%20Music-7299252254878583598)**

**How It Works**

A Python script bridges a virtual MIDI port (loopMIDI on Windows, IAC Driver on Mac) to an Arduino running a custom sketch. Each stepper motor is assigned to a MIDI channel — when notes are sent on that channel, the corresponding motor spins at the right frequency to produce the note. The Arduino CNC Shield with A4988 stepper drivers makes the hardware setup straightforward.

**What You Need**

- Arduino Duo + CNC Shield (comes with A4988 drivers)
- NEMA 17 Stepper Motors
- 12V Power Supply
- A DAW capable of MIDI output (FL Studio, etc.)
- Python + the Arduino IDE

The project supports up to 5 motors and includes detailed instructions for wiring, polarity testing, software setup, and troubleshooting.

**Check out the full project and tutorial on GitHub:** [MIDI-Stepper-Motor-Music](https://github.com/barlowtj48/MIDI-Stepper-Motor-Music)
