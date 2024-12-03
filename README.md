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


-in this part our target ıs evaluate the Cdf graph 

Step-by-Step CDF Calculation

Input Data:
Errors are extracted from the dataset.

Sort the Errors:
Arrange the error values in ascending order.

Compute CDF Values:
For each sorted error Ei, calculate:

CDF(Ei) = Rank of Ei / Total Number of Errors

where the rank is the 1-based index of Ei in the sorted list.

Example for the Provided Data:

Errors from Dataset:

50.41, 32.36, 28.85, 32.74, 36.00, 50.41, 28.85, 40.00, 58.85

Sort the Errors:

Sorted Errors: [28.85, 28.85, 32.36, 32.74, 36.00, 40.00, 50.41, 50.41, 58.85]

Compute CDF Values:

For 28.85 (1st and 2nd occurrences):

CDF = 1/9 = 0.11 and CDF = 2/9 = 0.22

For 32.36 (3rd):

CDF = 3/9 = 0.33

For 32.74 (4th):

CDF = 4/9 = 0.44

And so on...

Results:

| Error | CDF  |
|-------|------|
| 28.85 | 0.11 |
| 28.85 | 0.22 |
| 32.36 | 0.33 |
| 32.74 | 0.44 |
| 36.00 | 0.56 |
| 40.00 | 0.67 |
| 50.41 | 0.78 |
| 50.41 | 0.89 |
| 58.85 | 1.00 |


Explanation of Results:

Error Values: Each unique error value represents a position error in he system.

CDF: Indicates the proportion of errors that are less than or equal to the corresponding error.

For example:

CDF(32.36) = 0.33 means 33% of the errors are ≤ 32.36.

CDF(50.41) = 0.89 means 89% of the errors are ≤ 50.41.


