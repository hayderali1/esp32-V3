# Fingerprint indoor tracking system
Refer to volume 2 for further understanding of the used fingerprint technique methodology  https://github.com/hayderali1/esp32-v2

![Figure_2](https://github.com/user-attachments/assets/e20e6196-611b-40c9-b506-10d16b7b0a07)

fingerprintDatabase 
= [
  { x: 302, y: 140, rssi: -61 }, // A
  
  { x: 302, y: 70, rssi: -56 },  // B

  { x: 226.5, y: 140, rssi: -55 }, // C 
  
  { x: 226.5, y: 70, rssi: -61 },  // D
  
  { x: 226.5, y: 0, rssi: -48 },   // E
  
  { x: 151, y: 140, rssi: -69 },   // F
  
  { x: 151, y: 70, rssi: -73 },    // G
  
  { x: 151, y: 0, rssi: -59 },     // H
  
  { x: 75.5, y: 140, rssi: -65 },  // I
  
  { x: 75.5, y: 70, rssi: -76 },   // J
  
  { x: 75.5, y: 0, rssi: -55 },    // K
  
  { x: 0, y: 140, rssi: -67 },     // L
  
  { x: 0, y: 70, rssi: -81 },      // M
  
  { x: 0, y: 0, rssi: -62 },       // N
];




Example
Given errors: [50.41, 32.36, 28.85, 40.00]

Sort Errors: [28.85, 32.36, 40.00, 50.41]

Compute CDF:

For 
𝑥
=
28.85
x=28.85: 
𝐹
(
𝑥
)
=
1
4
=
0.25
F(x)= 
4
1
​
 =0.25
For 
𝑥
=
32.36
x=32.36: 
𝐹
(
𝑥
)
=
2
4
=
0.50
F(x)= 
4
2
​
 =0.50
For 
𝑥
=
40.00
x=40.00: 
𝐹
(
𝑥
)
=
3
4
=
0.75
F(x)= 
4
3
​
 =0.75
For 
𝑥
=
50.41
x=50.41: 
𝐹
(
𝑥
)
=
4
4
=
1.00
F(x)= 
4
4
​
 =1.00
Plot Points: 
(
28.85
,
0.25
)
,
(
32.36
,
0.50
)
,
(
40.00
,
0.75
)
,
(
50.41
,
1.00
)
(28.85,0.25),(32.36,0.50),(40.00,0.75),(50.41,1.00).
