# Pipelined-Floating-Point-Dot-Product-Multiplier

This is contains a Verilog Implementation of a pipelined FPDPM

# Content

1.	IEEE 754 Floating-Point Representation Standard.
2.	Floating Point Dot Product Multiplication
3.	Pipelined FPDPM Architecture
4.	Verilog Implementation of the Pipelined FPDPM
5.	Testbench of the design
6.	Simulation Results


# 1.  IEEE 754 Floating-Point Representation Standard.
   * Single Precison Representation
   ![image](https://user-images.githubusercontent.com/72949261/213870648-d3ae3b32-8c55-4791-8792-f9df2311f097.png)
  
  * Double Precision Representation
  ![image](https://user-images.githubusercontent.com/72949261/213870632-600b394f-35a3-418a-9588-0227a3cce890.png)

  * For Example:
  ![image](https://user-images.githubusercontent.com/72949261/213870607-26bb36f9-0b22-4fbd-bc9e-d423a68e358e.png)


# 2.  Floating Point Dot Product Multiplication
Floating point multiplication is comparatively easy than the floating-point addition algorithm but off course consumes more hardware than fixed point multiplier circuit. Major hardware block is the multiplier which is same as fixed point multiplier. This multiplier is used to multiply the mantissas of the two numbers. A floating-point multiplication between two numbers a and b can be expressed as

![image](https://user-images.githubusercontent.com/72949261/213870734-98a468cb-387a-451d-8bf7-e896239aef5e.png)


Thus, it can be said that in a floating-point multiplication, mantissas are multiplied, and exponents are added. The major steps for a floating-point division are:
	
  1.  Extract the sign of the result from the two sign bits.
	2.  Add the two exponents ( E ). Subtract the bias component from the summation.
	3.  Multiply mantissa of b ( M_b ) by mantissa of a ( M_a ) considering the hidden bits.
	4.  If the MSB of the product is  1  then shift the result to the right by 1-bit.
	5.  Due to this, the exponent is to be incremented according to the one-bit right shift.
Floating point multiplication can be clearer with an example. Let’s discuss a multiplication operation between two numbers b = 6.5 and a = 3 . The result of the multiplication operation is _19.5_ .

