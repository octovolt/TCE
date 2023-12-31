TCE: Two Comparator Effect
===

This is a Eurorack version of the [two_comparator_effect](https://github.com/cyberboy666/two_comparator_effect) originally designed by [Rob Schafer](https://www.youtube.com/c/schaferob) and later improved by [cyberboy666](https://github.com/cyberboy666). I communicated with cyberboy666 before publishing this module and received his blessing for doing so.

The circuit compares the voltage of a composite video signal to two different threshold voltages to produce two binary signals. That is, if the video signal is brighter than the threshold, the output is "high" or white. If the video signal is darker than the threshold, the output is "low" or black. One of the binary signals is actually sent out at a lower voltage level than the other, so the mixed output of both signals looks like white, gray and black.

A [demo video](https://youtu.be/mtZ2dQ727Hc) is available if you would like to see the module in action. The video shows a version that used tall trimmer pots instead of the more robust Alpha 9mm pots in the BOM, but it is otherwise identical. 

The LM339 Comparator
--------------------

It's worth noting that this circuit uses an LM339 comparator, which is not quite fast enough for video. The LM339 has a response time of about 1.3 microseconds, and we really need a response time below 83 nanoseconds for video. As a result, the resulting video image is slightly shifted to the right. This is not an issue unless your are mixing the output with the original signal in some way. Even then, the offset sort of looks interesting. I will say this for the LM339: it's very cheap, easy to find, and it comes in a quad through-hole package. Unfortunately, with the way through-hole components are going extinct, there aren't a lot of other great options in a quad package.

Build Guide
-----------

```
+--------------------------------+
|       !!! IMPORTANT !!!        |
| You must solder R9 before R8!  |
+--------------------------------+
```

When soldering, please also see the [interactive BOM](https://octovolt.github.io/TCE).

Steps:

1. Solder all resistors and ferrite beads on the back side of the circuit board (the side with the open source hardware logo).
2. Solder the R8 resistor on the front side of the circuit board. Do not solder it on the front before soldering the resistors on the back. R8 must overlap the solder joint for R9 on the back, so solder R9 first! I know this is weird, but this demonstrates the limits of my PCB design skillz. If you can come up with a better design that maintains the strength of the front panel, is just as cheap to manufacture at JCLPCB, and does not use a second circuit board, please open a pull request on the Github repository. I would love to get a fresh perspective on this.
3. Solder the diodes on the front side of the board. D1 says 1N914 on the BOM but this can be replaced by a 1N4148 or 1N5819. I use a 1N4148 in all of my builds. D2 and D3 are the standard Eurorack reverse polarity protection diodes. I use 1N4004, but you can use any diode in the 1N400x series. Make sure to get the polarity correct when you place the diodes! The line on the circuit board should match the stripe on the diode.
3. Solder the socket for the IC, if you want to one. People say it introduces extra capacitance, but it's probably no big deal in this circuit.
4. Solder the ceramic capacitors on the back side of the board.
5. Solder the transistors.
6. Solder the power headers.
7. Solder the electrolytic capacitors. Mind the polarity! The white side on the circuit board is negative.
8. Solder the one ceramic capacitor on the front side of the board.
9. Place but do not solder the jacks, knobs and switch on the front side of circuit board.
10. Place the front panel over the jacks, knobs and switch, and then use their nuts to attach them to the front panel.
11. Solder the jacks, knobs and switch.
12. If you used an IC socket, put the IC in the socket. If you did not use a socket, solder the IC now. Mind the polarity! The small semi-circle on the board should match the notch on the IC.
13. Test and enjoy!



