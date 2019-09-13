# DUART-MC68681-Assembler-Program-
Simplified assembler program that filters images (represented as a matrix) and changes the values of the pixels. the model is the DUART MC68681.

Internal buffers store the characters that they receive asynchronously through the series port. At the same time, 
thoe buffers are needed to store the pending characters to be transmitted through the ports. There's one interrupt service routine, ISR,
of the ports which would be in charge of transfering the information from or to said buffers.

The program is an implementation of the ISR and the following subroutines that form the interface:
- INIT: initializes the I/O devices, prepares the series ports (A and B) to transmit and receive characters and
notifies the events through interruption requests.

- SCAN: Reading of the device. It returns a string of characters that has been received previously through the port, A or B.

- PRINT: Writing in a device. It requests the writing of the string of characters through the respective port, A or B.

To assist those subroutines and to test the manipulation of the internal buffers of the previously mentioned subroutines,
the following auxiliary subroutines have been implemented:

LEECAR: reads a character from an internal buffer.

ESCCAR: stores a character in an internal buffer.

LINEA: searches for a complete string of characters in the internal buffer.

For more detailed specifications refer to page 57 of the "manual.pdf" file provided (WARNING: It's in Spanish)

NOTE: PROJECT DEVELOPED DURING MY COMPUTER ENGINEERING BACHELOR'S DEGREE AT UNIVERSIDAD POLITECNICA DE MADRID ON 2016-2017

THE PURPOSE OF THE PROJECT IS TO LEARN HOW THE ASSEMBLER DUART MC 68681 TREATS ASYNCHRONOUS CALLS FROM I/O THROUGH INTERRUPTIONS.
THE BASE OF THE PROGRAM WAS PROVIDED BY THE TEACHER BUT THE COMPLETE IMPLEMENTATION OF THE CODE WAS DEVELOPED BY ME. SOME ASPECTS
OF THE CODE DON'T WORK AS OPTIMIZED AS THE DEPTHNESS OF THE FIELD AT HAND WAS NOT TAUGHT IN THE COURSE.
