# Bit-wise operators in C

### What are bitwise operators?
Carefully looking at the term, you will notice the term “bit”. Bit is the smallest unit of data in computing (0s and 1s). This means the operators that work on the smallest unit of data in 
computing are known as bitwise operators. These operators manipulate one bit at a time rather than working on the whole number. They allow precise manipulation of bits, giving you control 
over hardware operations.

Following table displays the 6 bitwise operators used in C language:
| Sr. No. | Operator | Symbol <br/> Used     | Description    | Example                                 |
| :------:| :-------------: | :-------------: | :--------------------------------------------------------:| :---------:|
| 1.      | OR | &               | Sets the resulting bit to 1 only if both the bits are 1. <br/> Otherwise, sets the resulting bit to 0. | 0100 & 0101 = 0100 |
| 2.      | AND |   \|            | Sets the resulting bit to 0 only if both the bits are 0. <br/> Otherwise, sets the resulting bit to 1.  | 0100 \| 0101 = 0101 |
| 3.      | XOR |   ^            |If both the bits are the same, the resulting bit is 0. <br/> If both the bits are the opposite, the resulting bit is 1.  | 0100 ^ 0101 = 0001 |
| 4.      | NOT |  ~            | Inverts all the bits. | ~ 0100 = 1011 |
| 5.      | Left Shift |  <<            |Shifts the bits to left, adding 0s to the right.  | 0010 << 1 = 0100 <br/> 0010 << 2 = 1000 |
| 6.      | Right Shift |  >>           |Shifts the bits to right, adding 0s or 1s to the left.  | 0100 >> 1 = 0010 <br/> 0100 >> 2 = 0001 |


## Bitwise AND ('&') operator
The operator takes two operands, performs the operation (AND) on individual bit of the numbers. The result of AND operation is 1 if both the bits are one, otherwise the result is 0. 
The truth table of AND operator is as below:

| X | Y | X & Y |
|:---:|:---:|:---:|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

**Let’s take an example to understand this operator:**<br/>
int main() <br/>
{ <br/>
    int a = 4; (binary equivalent in 8-bits = 0000 0100) <br/>
    int b = 5; (binary equivalent in 8-bits = 0000 0101) <br/>
    int result = a & b; <br/>
    printf("The result is: %d", result);           // The result is 4 <br/>
    return 0; <br/>
} <br/>
<ins>Explanation:</ins> <br/>
<pre><code></code>Please note; For easy understanding, only first 8-bits of int are considered. <br/>
a=4    Binary equivalent =  0000 0100 <br/>
			    &&&& &&&&  (‘&’ operation performed on individual bit) <br/>
b=5    Binary equivalent = <ins> 0000 0101 </ins>   <br/>
                            0000 0100 <br/>  </code></pre>


## Bitwise OR ('|') operator
The operator takes two operands,performs the operation (OR) on individual bit of the numbers. The result of OR operation is 0 if both the bits are one, otherwise the result is 1. 
The truth table of OR operator is as below:

| X | Y | X \| Y |
|:---:|:---:|:---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

**Let’s take an example to understand this operator:**<br/>
int main() <br/>
{ <br/>
    int a = 4; (binary equivalent in 8-bits = 0000 0100) <br/>
    int b = 5; (binary equivalent in 8-bits = 0000 0101) <br/>
    int result = a | b; <br/>
    printf("The result is: %d", result);           // The result is 5 <br/>
    return 0; <br/>
} <br/>
<ins>Explanation:</ins> <br/>
<pre><code></code>Please note; For easy understanding, only first 8-bits of int are considered. <br/>
a=4    Binary equivalent =  0000 0100 <br/>
			    |||| ||||  (‘|’ operation performed on individual bit) <br/>
b=5    Binary equivalent = <ins> 0000 0101 </ins>   <br/>
                            0000 0101 <br/>  </code></pre>


## Bitwise XOR ('^') operator
The operator takes two operands, performs the operation (XOR) on individual bit of the numbers. The result of XOR operation is 0 when both the bits are same, the result is 1 when both the bits are opposite. 
The truth table of XOR operator is as below:

| X | Y | X ^ Y |
|:---:|:---:|:---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

**Let’s take an example to understand this operator:**<br/>
int main() <br/>
{ <br/>
    int a = 4; (binary equivalent in 8-bits = 0000 0100) <br/>
    int b = 5; (binary equivalent in 8-bits = 0000 0101) <br/>
    int result = a | b; <br/>
    printf("The result is: %d", result);           // The result is 1 <br/>
    return 0; <br/>
} <br/>
<ins>Explanation:</ins> <br/>
<pre><code></code>Please note; For easy understanding, only first 8-bits of int are considered. <br/>
a=4    Binary equivalent =  0000 0100 <br/>
			    ^^^^ ^^^^  (‘^’ operation performed on individual bit) <br/>
b=5    Binary equivalent = <ins> 0000 0101 </ins>   <br/>
                            0000 0001 <br/>  </code></pre>


## Bitwise NOT (~) operator
The operator takes one operand and inverts (0 is converted to 1 and vice-versa) all the bits of the number.
<pre> <code>
<b>Example 1</b>
int main()
{
    unsigned int a = 4; (binary equivalent in 8-bits = 0000 0100)
    unsigned int result = ~ a;
    printf ("The result is: %u ", result);         // The result is 4294967291
    return 0;
} </code></pre>

<pre><code>
<b>Example 2</b>
int main()
{
    int a = 4; (binary equivalent in 8-bits = 0000 0100)
    int result = ~ a;
    printf ("The result is: %d ", result);         // The result is -5
    return 0;
} </code></pre>

<ins>Explanation:</ins> </br>
Please note; For easy understanding, only first 8-bits of int are considered. </br>
<pre><code>
<b>Example 1</b>
a = 4   binary equivalent = 0000 0100
                      ~ a = ~~~~ ~~~~
                            1111 1011
For unsigned number, the decimal equivalent of the above number is 4294967291.
</code></pre>
<pre><code>
<b>Example 2</b>
a = 4   binary equivalent = 0000 0100
                     ~ a =  ~~~~ ~~~~
                            1111 1011
For signed number, the result above will be considered as 2’s complement of certain negative number (as negative numbers are
stored in the memory in 2’s complement form). Therefore, its decimal equivalent is -5. This can be confirmed by reversing the
process of 2’s complement on the result.
			1111 1011
				1              (Subtract 1)
                   <ins>	1111 1010 </ins>       (Take the one’s compliment)
		   	0000 0101
The result of the NOT operation on a signed number can be calculated with the formula –(a+1). Hence, -(4+1) gives us the result
as -5 in this example.
  </code></pre>

