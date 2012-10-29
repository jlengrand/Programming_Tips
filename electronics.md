# Electronics

Some basic tipe for new embedded Eletronics programmers

## Use of DDx, PORT and PIN registers:

- **DDx**: Choice of pins state: Inputs or Outputs
- **PORT**: Set the outputs state, rules the outputs (ex : set Pin to 0)
- **PIN**: Reads the inputs states, or toggle values. (ex: Toogle Pin)


## Easily set a bit to 0 in a register:

PPR=PPR & 0b01111111

## Easily set a bit to 1 in a register:

PPR=PPR & 0b01111111

## Debug hardware errors after optimization:

In case your C code does not work any more after Optimization (-O2 -O3)

- Check if global variables are used in interruptions
- Try to set them as volatile

## Hazardous hardware resets:

**Check if your interruptions are initialized in your code !**

Otherwise, the C code will automatically jump to a non-existing address, causing the reset.

## I/O problems:

In case of I/O problems in your code, **check your Hardware and especially your resistors**

Try to unsolder them and run the code.

## Embedded electronics main architecture code:

Generally, embedded architecture software is divided into 3 main layers :

- **Drivers:** Whose job is to interact with Hardware at a low level (Ex : Read spi data)
- **Services/Components:** Intermediate layer, interface between drivers and Applications
- **Application:** Higher layer, which aims at achieving the main purpose of the project (Ex: Calculate movement using an accelerometer)
Here is a simple drawing to get the idea:

![Embedded Architecture Drawing](https://dl.dropbox.com/u/4286043/01_Git/Embedded_architecture.png)

__**NOTE:**__ The main idea behind that when you code is the reuse! The application may not be reusable, but drivers and components must !

If you did good, you should be able to use **the same application** in two architectures, **changing only components and drivers**.

