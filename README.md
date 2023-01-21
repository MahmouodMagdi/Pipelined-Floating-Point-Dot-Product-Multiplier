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
   ![image](https://user-images.githubusercontent.com/72949261/213871537-4b67640e-978e-40a1-837a-771ed56a020d.png)

  
  
  * Double Precision Representation
  ![image](https://user-images.githubusercontent.com/72949261/213871604-a3c2bfbd-aee2-4eb6-99e3-f70d22b149c6.png)

  
  
  * For Example:
  ![image](https://user-images.githubusercontent.com/72949261/213871617-f5b6ffad-2d95-42a1-8cd6-be3ee6892d16.png)



# 2.  Floating Point Dot Product Multiplication
Floating point multiplication is comparatively easy than the floating-point addition algorithm but off course consumes more hardware than fixed point multiplier circuit. Major hardware block is the multiplier which is same as fixed point multiplier. This multiplier is used to multiply the mantissas of the two numbers. A floating-point multiplication between two numbers a and b can be expressed as

![image](https://user-images.githubusercontent.com/72949261/213870734-98a468cb-387a-451d-8bf7-e896239aef5e.png)


Thus, it can be said that in a floating-point multiplication, mantissas are multiplied, and exponents are added. The major steps for a floating-point division are:
  	1.  Extract the sign of the result from the two sign bits.
	2.  Add the two exponents ( E ). Subtract the bias component from the summation.
	3.  Multiply mantissa of b ( M_b ) by mantissa of a ( M_a ) considering the hidden bits.
	4.  If the MSB of the product is  1  then shift the result to the right by 1-bit.
	5.  Due to this, the exponent is to be incremented according to the one-bit right shift.
Floating point multiplication can be clearer with an example. Let’s discuss a multiplication operation between two numbers _b = 6.5_ and _a = 3_ . The result of the multiplication operation is _19.5_ .


Example: Floating Point Multiplication
	* Representation: The input operands are represented as a = 0_1001_10100000000 and b = 0_1000_10000000000.

	* Sign extraction: As both the numbers are positive then sign of the output will be positive. Thus S = 0.

	* Exponent addition: The value of E_a = 1001 and E_b= 1000 . Thus, result of the addition is E = 10001 . The bias is subtracted from this value. Thus, new               value of E is 1010.

	* Mantissa multiplication: Multiply the mantissas by any multiplicative algorithms used in the fixed-point arithmetic. The width of the product is 24-bit, but           the final output is truncated to 11-bits. The 13-bits of the product starting from the MSB is 1001110000000.


Generally, the 11-bits from the LSB are the required result but here the MSB is 1 this indicate that the result is greater than 1 . Thus, this value is shifted right by 1-bit and the new result is 0100111000000. The final value of the mantissa (M ) is 00111000000 excluding the hidden bit.

This normalization step must reflect on exponent correction. The value of the exponent is corrected by an increment corresponding to a right shift. The new value of the exponent ( E ) is 1011.

The final result is 0_1011_00111000000 which is equivalent to 19.5 in decimal.


