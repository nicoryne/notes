# Error Detection and Correction
TODO:   Continue block coding
[Third-party source](https://lecturenotes-classroom-assignment-and-submission.s3.ap-south-1.amazonaws.com/3-52a80cdafd-error-detection-and-correction12.pdf)

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

1Mbps: 1 extra bit

1Mbps: 1000 extra bits


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

- *r* redundant bits are added to each block to make the length *n = k + r*.

- The resulting *n-bit* blocks are called **codeword**

- Represented by *C(n, k)*


### Convolution Codes