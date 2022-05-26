# MAC Address

MAC Address
: Media Access Control Address

Also known as the *Physical Address*

MAC Addresses are a 48-bit address; hexidecimal
Phsyical Address/MAC Address example:

```
40-8D-5C-1C-5A-50
```
- Each hexidecimal character represents 4 binary characters
    -  4 x 12 = 48
- First 3 pairs are known as OEM numbers
- Last 3 pairs are Unique ID, which are  burned into each card at the factory

For frames to know how to get to a specific computer, there needs to be a
specific identifier

- The payload of the frame does not identify the destination
- Frames have a destination and source MAC Address
- A sample of a frame gets sent to every computer connected to a network
    - NICs use MAC Addresses to decide whether or not to process a frame
