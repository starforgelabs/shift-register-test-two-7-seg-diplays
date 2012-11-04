shift-register-test-two-7-seg-diplays
=====================================

This is a trivial demo of two cascaded 4094 shift registers. 
Each drive a single 7-segment display.

Circuit Construction
--------------------

SR1 = shift register attached to Arduino.
SR2 = shift register cascaded from SR1

The first shift register is connected thus:

* Arduino D2 to SR1 strobe (STR).
* Arduino D3 to SR1 data (D).
* Arduino D4 to SR1 clock (CP).

Tie SR1 output enable (OE) high.

Connect the 7-segment display thus: 

* QP0 to segment A.
* QP1 to segment B.
* QP2 to segment C.
* QP3 to segment D.
* QP4 to segment E.
* QP5 to segment F.
* QP6 to segment G.

This demo does not use the decimal point, but QP7 can be used.
If you wish to use the decimal point, control it in the Arduino using the most significant bit (MSB) in the bit pattern.

The second shift register is connected thus:

* SR1 strobe (STR) to SR2 strobe (STR). 
* SR1 cascade output (QS) to SR2 data (D).
* SR1 clock (CP) to SR2 clock (CP).

Tie SR2 output enable (OE) high.

Connect the 7-segment display to SR2 identically as was done with SR1:

* QP0 to segment A.
* QP1 to segment B.
* QP2 to segment C.
* QP3 to segment D.
* QP4 to segment E.
* QP5 to segment F.
* QP6 to segment G.

