# CGA-RGBI-to-Analog-RGB

This project is a blatant steal from [Chris Osborn](http://www.insentricity.com/a.cl/219/cgargbi-to-analog-for-the-commodore-128) who has taken the circuit from someone else.
The ideas is to make it possible to connect a TTL RGBI signal output to a GBS 8200 scan converter and thereby connect old C128 or IBM PC with CGA card to a modern flat screen VGA monitor. The GBS 8200 or similar can be bought cheap from aliexpress or dealextreme or similar sources.

Since I really liked a proper circuit board and and as cheap as possible I had to keep the board real-estate as low as possible. Thereby using SMD mount instead of through-hole.
To make the layout a bit simpler some modification has been done. The A0 and A1 inputs for the 74HC138 are grounded rather than pulled high which means that output O4 has to be used instead of O7.
To simplify the boardlayout the 74HCT244 is used slightly different. 

I put the [resulting dsign at OSHpark](https://oshpark.com/shared_projects/xC5EGJzc) in case someone wants to order it from them directly.

![Top side](http://i.imgur.com/mRA4rBz.png)

This time I happen to buy from Mouser which is why include those partnumber, but anyone can of course choose their favourite supplier.

|Designator|Component|Mouser partno|
|----------|---------|-------------|
|   U1     | 74HC138 |[595-SN74HC138DR](http://www.mouser.se/Search/ProductDetail.aspx?R=SN74HC138DRvirtualkey59500000virtualkey595-SN74HC138DR)|
|   U2     | 74HCT86 |[863-MC74HCT86ADR2G](http://www.mouser.se/Search/ProductDetail.aspx?R=MC74HCT86ADR2Gvirtualkey58410000virtualkey863-MC74HCT86ADR2G)|
|   U3     | 74HCT244|[771-74HCT244D-Q100](http://www.mouser.se/Search/ProductDetail.aspx?R=74HCT244D-Q100%2c118virtualkey66800000virtualkey771-74HCT244D-Q100)|
|C1 C2 C3| 0.1uF 0805|[81-GRM40Y104Z25D](http://www.mouser.se/search/ProductDetail.aspx?R=0virtualkey0virtualkeyGRM216F51E104ZA01D)|
|R3 R5 R6| 470ohm 0805 | [603-RC0805JR-07470RL](http://www.mouser.se/Search/ProductDetail.aspx?R=RC0805JR-07470RLvirtualkey57620000virtualkey603-RC0805JR-07470RL)|
|R2 R7 R4| 1.5kohm 0805| [667-ERJ-6GEYJ152V](http://www.mouser.se/Search/ProductDetail.aspx?R=ERJ-6GEYJ152Vvirtualkey66720000virtualkey667-ERJ-6GEYJ152V)|
| R8     | 1kohm 0805|[No:	603-RC0805JR-071KL](http://www.mouser.se/Search/ProductDetail.aspx?R=RC0805JR-071KLvirtualkey57620000virtualkey603-RC0805JR-071KL)|
| R1     | 2kohm 0805| [603-RC0805JR-072KL](http://www.mouser.se/Search/ProductDetail.aspx?R=RC0805JR-072KLvirtualkey57620000virtualkey603-RC0805JR-072KL)|


![Bottom side](http://i.imgur.com/JASlqK1.png)

![Connecting to the GBS8200](http://i.imgur.com/AG3x1OQ.jpg)

![Output](http://i.imgur.com/q9WrcyZ.jpg)

```
10 PRINT CHR$(147);
20 FOR I=1 TO 16
30 READ C$
40 COLOR 5,I
50 PRINT CHR$(18)+"   C O L O R   "+CHR$(146)+" COLOR ";
60 COLOR 5,4
70 PRINT C$
80 NEXT
1000 DATA BLACK,WHITE,DARK RED,LIGHT CYAN
1010 DATA LIGHT PURPLE,DARK GREEN,DARK BLUE,LIGHT YELLOW
1020 DATA DARK PURPLE,BROWN,LIGHT RED,DARK CYAN
1030 DATA MEDIUM GRAY,LIGHT GREEN,LIGHT BLUE,LIGHT GRAY
```




The code for generating the above display was taken from a post by [Frank Buss](http://www.frank-buss.de/c128/vdc/index.html).
