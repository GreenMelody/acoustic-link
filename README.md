# Acoustic Link

Acoustic Link is a browser-only experiment for sending short text packets through sound.

It has two pages:

- `sender.html`: type text and press **Send** to play a 16-FSK audio packet.
- `receiver.html`: allow microphone access and keep listening for packets.

## How to test

1. Open `receiver.html` on the receiving phone or computer.
2. Press **Start Listening** and allow microphone access.
3. Open `sender.html` on the sending device.
4. Choose the same band preset on both pages.
5. Type a short message and press **Send**.

For the first tests, keep the sender speaker or headphone close to the receiver microphone and start with moderate volume.

## Frequency test

Use this before choosing a quiet band:

1. Open `receiver.html`, choose a band preset, and press **Frequency Test**.
2. Open `sender.html`, choose the same band preset, and press **Frequency Test**.
3. Check the receiver's frequency test table. Frequencies marked `OK` had at least one detection above the current score and confidence thresholds.

Start with `Lower quiet` or `Quiet` to avoid audible tones. If too few rows are marked `OK`, try `Mid quiet` or `High` before falling back to the audible diagnostic preset.

## Notes

- The default mode uses the lower quiet 16-FSK band across 14.0-17.75 kHz.
- The audible diagnostic preset uses 16-FSK across 2.0-5.75 kHz to verify that the speaker-to-microphone path works.
- The mid quiet preset uses 16-FSK across 12.0-15.75 kHz for debugging quiet high-frequency reception.
- The lower quiet preset uses 16-FSK across 14.0-17.75 kHz for devices that cannot receive 16 kHz and above reliably.
- The quiet preset uses 16-FSK across 16.0-19.75 kHz as a balance between audibility and reliability.
- The near-inaudible preset uses 16-FSK across 18.0-20.1 kHz. It is quieter but less reliable on many phones.
- Packets contain a preamble, length, UTF-8 payload, and CRC16.
- The receiver uses browser microphone input and FFT analysis.
- Shorter symbols are possible. Start with 55 ms tone + 20 ms gap, then try 30 ms tone + 10 ms gap with a 40 ms receiver interval.
- HTTPS is required for microphone access on phones, so GitHub Pages is a good hosting target.
