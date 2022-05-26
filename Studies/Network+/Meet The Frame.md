# Frame / Packets
A frame is a container for a single network packet
- A single frame *payload* can be up to 1_500 bytes long
    - 8 bits to a byte, around 10_000 1's and 0's
- Frames are created and destroyed inside a network card (NIC)
    - Data comes from whatever application into the network card itself, creates
      the frame and sends it into the network
    - Frames also come into the network card, data pulled away and sent to an
      application/software
    - Frames have a discreet beginning and discreet end

Ethernet has a minimum frame size of 64 bytes, comprising an 18-byte header and
a payload of 46 bytes.
- It has a maximum frame size of 1518 bytes, in which case the payload is 1500
  bytes
- If the message to be send leads to a frame size that is less than the 64-byte
  minimum, then additional bytes are padded.
