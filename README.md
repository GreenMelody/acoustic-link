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

## Notes

- The default mode uses 16-FSK across 3.2-18.2 kHz.
- The lower quiet preset uses 16-FSK across 14.0-17.75 kHz for devices that cannot receive 16 kHz and above reliably.
- The quiet preset uses 16-FSK across 16.0-19.75 kHz as a balance between audibility and reliability.
- The near-inaudible preset uses 16-FSK across 18.0-20.1 kHz. It is quieter but less reliable on many phones.
- Packets contain a preamble, length, UTF-8 payload, and CRC16.
- The receiver uses browser microphone input and FFT analysis.
- HTTPS is required for microphone access on phones, so GitHub Pages is a good hosting target.
