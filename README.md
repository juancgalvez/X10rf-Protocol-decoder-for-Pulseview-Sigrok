# X10rf-Protocol-decoder-for-Pulseview \(Sigrok\)
X10 Radio Frequency Protocol decoder for Pulseview \(Sigrok\)

## Some comments:

In X10 RF protocol there is a preamble comprising a ~9 ms UP time and a ~4.5 ms DOWN time. A Zero is a total time between rising edges of ~1.2 ms and a One is a
total time between rising edges of ~2.4 ms.

X10 RF bits for each byte are transmitted low significant bit first (from bit0 to bit7). Bit reversing is necessary.

Once the 32 bits are reversed, from left to right, byte 4 is house code, byte 3 is house code inverted, byte 2 is unit code and byte 1 is unit code reversed.

Inside the code, to evaluate unit and command, byte 1 becomes **byte1** and byte 3 becomes **byte2**.

Only ON, OFF, DIM, BRIGHT, ALL ON and ALL OFF commands are recognized. No extended codes are recognized.
