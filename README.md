## 555ADSR - 555-based ADSR module, revision 2

An updated version of the old 5HP ADSR module - functionally the same as its predecessor, albeit with a couple of changes. First, the range switch is now fitted to the mainboard itself rather than the front of the module, and second there's now an LED. It fits inside 4HP too ... so that's three things.

This is an updated envelope generator which uses a 555 timer configured as a Schmitt trigger (see: [https://www.nutsvolts.com/magazine/article/555-monostable-circuits](https://www.nutsvolts.com/magazine/article/555-monostable-circuits) - figure 15 in particular) from which the envelope is generated. The net result is something that not only triggers at around 1V but also has far fewer parts.

I'm going to call that a win, and it isn't dissimilar to the design that Doepfer use in their EG modules, albeit without the bells and whistles.

In addition, I've 'borrowed' a couple of features from a Rene Schmitz design, specifically: the resistor R13 is optional, but adding it will give the input a bit of hysteresis (the degree of which is governed by the values of R13 - 1MΩ is what I use) which is handy if you're using a slowly changing waveform as a trigger.

Secondly, there's a buffer between the sustain and decay pots which removes any interdependence between the two. It also uses up an otherwise uncommitted op-amp. There's a range switch on the mainboard too - envelope values are governed by the control pots and the values of the two capacitors.

### Build notes

* The board has 3 surface mount transistors (MMBT3904 - Q1-Q3) which have been pre-soldered.
* For best results, use a CMOS-based 555 - I usually use the Renesas 7555 or TI's SA555.
* The two decay/release capacitors are C3 and C6 - for pre-built modules I usually spec these as 330nF and 2.2uF, respectively, assuming the use of 1M pots for attack, decay and release.
* I strongly recommend the use of audio-taper 1M pots for the attack, decay and release. You can use any linear pot for the sustain control - 50k or 100k are good choices. You can get a good idea of decay/release times based on the RC time constant - in most cases, the envelope will have decayed to 0V (near as makes not odds) after 5 time constants.
* The range switch mounts on the board itself - this is a result of feedback from various folks who had an older module with the switch broken out; once they set it, they very rarely changed it - there's nothing to stop you breaking the switch out though.