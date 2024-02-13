# Error Detection and Correction

> Data received must be the same as data transmitted

Data can be corrupted during transmission.

Some applications require that errors be detected and corrected.

## Types of Errors

Distortion
: Changing the shape of signal

### Single-bit error
> Only 1 bit in the data unit has changed.

*Single-bit errors are the least likely type of error to occur in a serial data transmission*
For a single-bit error to occur, the noise duration must only be for 1 microsecond.

### Burst error
> 2 or more data in the unit has changed.
> Errors occur in consecutive bits.
> Length of burst error is measured from the first corrupted bit to the last corrupted bit.

