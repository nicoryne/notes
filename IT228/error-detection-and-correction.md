# Error Detection and Correction

[Third-party source](https://lecturenotes-classroom-assignment-and-submission.s3.ap-south-1.amazonaws.com/3-52a80cdafd-error-detection-and-correction12.pdf)

[Quiz](https://highered.mheducation.com/sites/844815617x/student_view0/chapter10/multiple_choice_quiz.html)
> Data received must be the same as data transmitted

Data can be corrupted during transmission.

Some applications require that errors be detected and corrected.

`
Error Detection and Correction are implemented either at the data link layer or the transport layer of the OSI model
`




## Types of Errors

*Distortion*
: Changing the shape of signal.

### Single-bit error
> Only 1 bit in the data unit has changed.

*Single-bit errors are the least likely type of error to occur in a serial data transmission.*

For a single-bit error to occur, the noise duration must only be for 1 microsecond.

### Burst error
> 2 or more data in the unit has changed.

 Errors occur in consecutive bits.

 Length of burst error is measured from the first corrupted bit to the last corrupted bit.

Burst errors are more likely to occur because the noise duration is usually longer than a single bit.




## Data Redundancy

> To detect or correct errors, we need to send extra (redundant) bits with data.




## Detection versus Correction

### Error Detection

*As long as we detect the error, the type of said error doesn't matter*

Detection Methods
- Parity Check
    - A party bit is added to every data unit so that the total number of 1s (including the parity bit) becomes even for even-parity check, or odd for odd-parity check.

    - If receiver finds variety in the number of 1s for each character (odd and even), it will discard and ask for retransmission.

- Cyclic redundancy check
- Checksum

### Error Correction

*In contrast to error detection, we need to know the location and the size of bits during error correction*

The receiver clock is 0.1% faster than the sender clock.

1Kbps (1,000 bits/second): 1 extra bit

1Mbps (1,000,000 bits/second): 1000 extra bits


## Forward Error Correction versus Retransmission

When using Forward Error Correction in data transmissions, the receiver can detect and correct a limited number of errors. If there are too many errors, the sender must retransmit the packets that contain the errors.

`
The key idea of FEC is to transmit enough redundant data to allow receiver to recover from errors all by itself.
`

[What is Forward Error Correction? (FEC)](https://www.techtarget.com/searchmobilecomputing/definition/forward-error-correction#:~:text=Forward%20error%20correction%20(FEC)%20is,that%20contains%20no%20apparent%20errors.)




## Coding

### The structure of encoder and decoder
    Encoder
    - Sender send message
    - Generator adds parity (redundant) bits
    - Encoded message with parity bits pass through unreliable transmission

    Receiver
    - Encoded message is received
    - Checker corrects or discards the encoded message
    - If correct, it is accepted to the receiver

### Block Coding

- Block coding divides messages into blocks, each of *k* bits called **data words**.
    - **Dataword:** *= k*

- *r* redundant bits are added to each block to make the length *n = k + r*.

- The resulting *n-bit* blocks are called **codeword**
    - **Codeword:** *n = k + r*

- Represented by *C(n, k)*



#### Linear Block Codes

- Information is divided into blocks of length k

- *r* parity bits or check bits are added to each block (total length *n = k + r*)

- Code rate *R = k / n*

- C (*n, k*) block code is said to be linear if the vector sum of two codewords is a codeword


#### 4B/5B Block Coding

**Example**
> In this coding scheme, k = 4 and n = 5.

- 2^k^ = 16 *datawords*

- 2^n^ = 32 *codewords*

- 16 out of 32 *codewords* are used for message transfer and the rest are either used for other purposes or unused.

#### Code for error detection

| Datawords | Codewords |
|:---:      |:----:     |
| 00        | 000       |
| 01        | 011       |
| 10        | 101       |
| 11        | 110       |

> An error-detecting code only detect the types of errors for which it is designed; other types of errors may remain undetected

#### Cyclic codes

- A subclass of Linear Block code

- These are special linear block codes with one extra property. In a cyclic code, if a codeword is cyclically shifted (rotated), the result is another codeword.

**A CRC code with C(7,4)**
*note: n = k + r*

| Dataword (k)  | Codeword (n)  | Dataword (k)  | Codeword (n) |
|:----:     |:----:      | :----:    | :----:   |
| 0000      | 0000000    | 1000      | 1000101  |
| 0001      | 0001011    | 1001      | 1001110  |
| 0010      | 0010110    | 1010      | 1010011  |
| 0011      | 0011101    | 1011      | 1011000  |
| 0100      | 0100111    | 1100      | 1100010  |
| 0101      | 0101100    | 1101      | 1101001  |
| 0110      | 0110001    | 1110      | 1110100  |
| 0111      | 0111010    | 1111      | 1111111  |

*r = 3*

#### Hamming Distance

> It is the number of differences between corresponding bits.

**Example**

- The Hamming distance d(000, 011) is 2 because 000 + 011 is 011 (two 1s)

- The Hamming distance d(10101, 11110) is 3 because 10101 + 11110 is 01011 (three 1s)

`
  The minimum Hamming distance is the smallest hamming distance between all possible pairs in a set of words.
`

**Error Detection**

- In order to detect errors up to s errors in all cases, the minimum Hamming distance in a block code must be *d~min~ = s + 1*

    - The minimum d~min~ required to detect atleast 1 error is 2 (2 = s + 1) where s = 1

- However, to gurantee the correction of up to *t* errors in all cases, the minimum Hamming distance in a block code must be *d~min~ = 2t + 1*

    - The minimum d~min~ required to correct atleast 1 error is 2 (3 = 2t + 1) where t = 1
