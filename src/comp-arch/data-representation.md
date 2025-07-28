# Data Representation

## Number Systems

### Decimal System

**Decimal** is a number system that uses base 10, characterized by two fundamental properties:

- Each digit position can hold one of 10 unique values (0 through 9). Values greater than 9 require carrying to an additional digit position to the left.
- Each digit's position determines its contribution to the overall value through positional notation. Digits are labeled from right to left as \\(d_0, d_1, d_2, \dots, d_{N - 1}\\) where each successive position represents ten times the value of the position to its right.

More formally, any \\(N\\)-digit decimal number can be expressed using positional notation as:

\\((d_{N-1} \cdot 10^{N-1}) + (d_{N-2} \cdot 10^{N-2}) + \dots + (d_2 \cdot 10^2) + (d_1 \cdot 10^1) + (d_0 \cdot 10^0)\\)

Decimal numbers are typically written without prefixes, though they may be denoted as \\(N_{10}\\) when clarification is needed.

### Binary System

**Binary** is a number system that uses base 2, characterized by:

- Each digit position (called a **bit**) can hold one of two unique values: 0 or 1. Values greater than 1 require carrying to an additional bit position to the left.
- Each bit's position determines its contribution through powers of 2: \\(2^{N-1}, \dots, 2^1, 2^0\\).

Binary numbers are typically prefixed with `0b`.

#### Binary Terminology and Groupings

Since individual bits represent limited information, they are commonly grouped:

- **Byte**: 8 bits (the smallest addressable unit of memory)
- **Nibble**: 4 bits (half a byte)
- **Word**: The natural data width of a CPU (typically 32 or 64 bits)

In any binary sequence, we identify:
- **Most Significant Bit (MSB)**: The leftmost bit
- **Least Significant Bit (LSB)**: The rightmost bit

### Hexadecimal System

**Hexadecimal** uses base 16, characterized by:

- Each digit position can hold one of 16 unique values. Since we only have 10 decimal digits (0 to 9), letters A to F represent values 10 to 15 respectively.
- Each digit's position determines its contribution through powers of 16: \\(16^{N-1}, \dots, 16^1, 16^0\\).

Hexadecimal numbers are prefixed with `0x`.

#### Hexadecimal-Binary-Decimal Conversion Table

| Hex | Binary | Decimal |
|-----|--------|---------|
| 0   | 0000   | 0       |
| 1   | 0001   | 1       |
| 2   | 0010   | 2       |
| 3   | 0011   | 3       |
| 4   | 0100   | 4       |
| 5   | 0101   | 5       |
| 6   | 0110   | 6       |
| 7   | 0111   | 7       |
| 8   | 1000   | 8       |
| 9   | 1001   | 9       |
| A   | 1010   | 10      |
| B   | 1011   | 11      |
| C   | 1100   | 12      |
| D   | 1101   | 13      |
| E   | 1110   | 14      |
| F   | 1111   | 15      |

## Converting Between Number Systems

### Decimal to Any Base (Division method)

1. Repeatedly divide the decimal number by the target base
2. Record the remainder at each step
3. Continue until the quotient becomes 0
4. Read the remainders from bottom to top to get the result

### Any Base to Decimal (Addition of Positional Notation)

For a number with digits \\(d_{N-1}, d_{N-2}, \dots, d_1, d_0\\) in base \\(B\\), the converted number to base \\(C\\) is calculated using the following formula:

\\((d_{N-1} \cdot B^{N-1}) + (d_{N-2} × B^{N-2}) + \dots + (d_1 × B^11) + (d_0 × B^0)\\)

### Binary to Hexadecimal

1. Group binary digits into sets of 4 bits from right to left
2. Pad the leftmost group with leading zeros if necessary
3. Convert each 4-bit group to its hexadecimal equivalent

### Hexadecimal to Binary

1. Convert each hexadecimal digit to its 4-bit binary equivalent
2. Concatenate all binary groups

## Computer Data Units

### Memory and Storage Capacities

| Unit | Value |
|------|-------|
| 1 KB (Kilobyte) | \\(2^{10}\\) bytes (1,024 bytes) |
| 1 MB (Megabyte) | \\(2^{20}\\) bytes (1,048,576 bytes) |
| 1 GB (Gigabyte) | \\(2^{30}\\) bytes (1,073,741,824 bytes) |
| 1 TB (Terabyte) | \\(2^{40}\\) bytes (1,099,511,627,776 bytes) |
| 1 PB (Petabyte) | \\(2^{50}\\) bytes (1,125,899,906,842,624 bytes) |
| 1 EB (Exabyte) | \\(2^{60}\\) bytes (1,152,921,504,606,846,976 bytes) |

### Data Transfer Units

| Unit | Value |
|------|-------|
| 1 Kilobit (Kb) | 1,000 bits |
| 1 Megabit (Mb) | 1,000,000 bits |
| 1 Gigabit (Gb) | 1,000,000,000 bits |
| 1 Terabit (Tb) | 1,000,000,000,000 bits |

## Character Representation

### ASCII

**ASCII** is a character encoding standard which uses 8 bits per character, where 7 bits encode the actual character and the eighth bit serves as a parity bit for error detection, where the added bit ensures either an even number of 1 (even parity) or an odd number of 1 (odd parity) in the complete byte.

#### Types of ASCII Characters

- Non-printable characters
  - Control characters, from `0x00` to `0x1F` (i.e. \\(0_{10}\\) to \\(31_{10}\\))
  - Delete character, `0x7F` (i.e. \\(127_{10}\\))
- Printable characters, from `0x20` to `0x7E` (\\(32_{10}\\) to \\(126_{10}\\)).

#### ASCII Table

| Hex | Char | Description |
|-----|------|-------------|
| 00  | NUL  | Null character |
| 01  | SOH  | Start of Heading |
| 02  | STX  | Start of Text |
| 03  | ETX  | End of Text |
| 04  | EOT  | End of Transmission |
| 05  | ENQ  | Enquiry |
| 06  | ACK  | Acknowledge |
| 07  | BEL  | Bell |
| 08  | BS   | Backspace |
| 09  | HT   | Horizontal Tab |
| 0A  | LF   | Line Feed |
| 0B  | VT   | Vertical Tab |
| 0C  | FF   | Form Feed |
| 0D  | CR   | Carriage Return |
| 0E  | SO   | Shift Out |
| 0F  | SI   | Shift In |
| 10  | DLE  | Data Link Escape |
| 11  | DC1  | Device Control 1 (XON) |
| 12  | DC2  | Device Control 2 |
| 13  | DC3  | Device Control 3 (XOFF) |
| 14  | DC4  | Device Control 4 |
| 15  | NAK  | Negative Acknowledge |
| 16  | SYN  | Synchronous Idle |
| 17  | ETB  | End of Transmission Block |
| 18  | CAN  | Cancel |
| 19  | EM   | End of Medium |
| 1A  | SUB  | Substitute |
| 1B  | ESC  | Escape |
| 1C  | FS   | File Separator |
| 1D  | GS   | Group Separator |
| 1E  | RS   | Record Separator |
| 1F  | US   | Unit Separator |
| 20  | SP   | Space |
| 21  | !    | Exclamation mark |
| 22  | "    | Double quote |
| 23  | #    | Number sign |
| 24  | $    | Dollar sign |
| 25  | %    | Percent sign |
| 26  | &    | Ampersand |
| 27  | '    | Apostrophe |
| 28  | (    | Left parenthesis |
| 29  | )    | Right parenthesis |
| 2A  | *    | Asterisk |
| 2B  | +    | Plus sign |
| 2C  | ,    | Comma |
| 2D  | -    | Hyphen-minus |
| 2E  | .    | Period |
| 2F  | /    | Slash |
| 30  | 0    | Digit 0 |
| 31  | 1    | Digit 1 |
| 32  | 2    | Digit 2 |
| 33  | 3    | Digit 3 |
| 34  | 4    | Digit 4 |
| 35  | 5    | Digit 5 |
| 36  | 6    | Digit 6 |
| 37  | 7    | Digit 7 |
| 38  | 8    | Digit 8 |
| 39  | 9    | Digit 9 |
| 3A  | :    | Colon |
| 3B  | ;    | Semicolon |
| 3C  | <    | Less than |
| 3D  | =    | Equal sign |
| 3E  | >    | Greater than |
| 3F  | ?    | Question mark |
| 40  | @    | At sign |
| 41  | A    | Uppercase A |
| 42  | B    | Uppercase B |
| 43  | C    | Uppercase C |
| 44  | D    | Uppercase D |
| 45  | E    | Uppercase E |
| 46  | F    | Uppercase F |
| 47  | G    | Uppercase G |
| 48  | H    | Uppercase H |
| 49  | I    | Uppercase I |
| 4A  | J    | Uppercase J |
| 4B  | K    | Uppercase K |
| 4C  | L    | Uppercase L |
| 4D  | M    | Uppercase M |
| 4E  | N    | Uppercase N |
| 4F  | O    | Uppercase O |
| 50  | P    | Uppercase P |
| 51  | Q    | Uppercase Q |
| 52  | R    | Uppercase R |
| 53  | S    | Uppercase S |
| 54  | T    | Uppercase T |
| 55  | U    | Uppercase U |
| 56  | V    | Uppercase V |
| 57  | W    | Uppercase W |
| 58  | X    | Uppercase X |
| 59  | Y    | Uppercase Y |
| 5A  | Z    | Uppercase Z |
| 5B  | [    | Left square bracket |
| 5C  | \    | Backslash |
| 5D  | ]    | Right square bracket |
| 5E  | ^    | Caret |
| 5F  | _    | Underscore |
| 60  | `    | Grave accent |
| 61  | a    | Lowercase a |
| 62  | b    | Lowercase b |
| 63  | c    | Lowercase c |
| 64  | d    | Lowercase d |
| 65  | e    | Lowercase e |
| 66  | f    | Lowercase f |
| 67  | g    | Lowercase g |
| 68  | h    | Lowercase h |
| 69  | i    | Lowercase i |
| 6A  | j    | Lowercase j |
| 6B  | k    | Lowercase k |
| 6C  | l    | Lowercase l |
| 6D  | m    | Lowercase m |
| 6E  | n    | Lowercase n |
| 6F  | o    | Lowercase o |
| 70  | p    | Lowercase p |
| 71  | q    | Lowercase q |
| 72  | r    | Lowercase r |
| 73  | s    | Lowercase s |
| 74  | t    | Lowercase t |
| 75  | u    | Lowercase u |
| 76  | v    | Lowercase v |
| 77  | w    | Lowercase w |
| 78  | x    | Lowercase x |
| 79  | y    | Lowercase y |
| 7A  | z    | Lowercase z |
| 7B  | {    | Left curly brace |
| 7C  | \|   | Vertical bar |
| 7D  | }    | Right curly brace |
| 7E  | ~    | Tilde |
| 7F  | DEL  | Delete |

### Unicode

**Unicode** is a character set standard that assigns a unique hexadecimal identifier, called a **code point**, to every character across all writing systems. These code points follow the format `U+<....>`.

#### Code Point Categories

- **Surrogate code points**: Code points in the range `U+D800` to `U+DFFF`, which are reserved for use in UTF-16 encoding
- **Scalar values**: All other Unicode code points (excluding surrogate code points)

#### Character Encoding Standards

Unicode defines three primary character encoding standards for converting code points into bytes for storage and transmission. These standards use **code units** as their basic storage elements to represent characters.


- UTF-8
  - **Code unit size**: 8 bits (1 byte)
  - **Character representation**: 1 to 4 code units per character
  - **Encoding type**: Variable-length encoding
- UTF-16
  - **Code unit size**: 16 bits (2 bytes)
  - **Character representation**: 1 code unit, or 2 code units for surrogate code points, and we call these 2 code units a **surrogate pair**
- UTF-32
  - **Code unit size**: 32 bits (4 bytes)
  - **Character representation**: Exactly 1 code unit per character

### Grapheme clusters

A **grapheme cluster** represents what users typically think of as a "character", that is, the smallest unit of written language that has semantic meaning.

#### Example

The grapheme clusters in the Hindi word `"क्षत्रिय"` are `["क्ष", "त्रि", "य"]`, where each cluster can comprise multiple Unicode code points. While `"य"` is a single code point, `"क्ष"` is a conjunct consonant formed from three code points: the base character `"क"` (`U+0915`), the virama `"्"` (`U+094D`), and `"ष"` (`U+0937`), which combine to create one visual unit. The cluster `"त्रि"` is even more complex, consisting of four code points: `"त"` (`U+0924`), `"्"` (`U+094D`), `"र"` (`U+0930`), and the vowel sign `"ि"` (`U+093F`), where the vowel mark appears visually before the consonant cluster despite following it in the Unicode sequence.

The example above demonstrates why simply counting Unicode code points doesn't always correspond to what users perceive as individual characters, making grapheme cluster boundaries crucial for correct string processing.

## Integer Representation

### Unsigned Integer Representation

**Unsigned integers** use all available bits to represent positive values (including zero). No bit is reserved for a sign, allowing for a larger range of positive values compared to signed integers of the same bit width.

An \\(N\\)-bit unsigned integer can take up values from \\(0\\) to \\(2^N - 1\\).

### Signed Integer Representation

**Signed integers** reserve one bit (typically the MSB) to indicate sign, reducing the range of representable positive values but enabling representation of negative numbers.

#### Two's Complement

**Two's complement** is the most common encoding system to represent signed integers. It treats the MSB exclusively as a sign bit:
- MSB = 0: positive number (or zero)
- MSB = 1: negative number

An \\(N\\)-bit unsigned integer using two's complement can take up values from \\(-2^{N-1}\\) to \\(2^{N-1} - 1\\).

To represent a number using two's complement:
1. Start with the binary representation of the positive number
2. Toggle all the bits
3. Add 1 to the result

> **Note**\
> When converting from binary to decimal, if the MSB is a 1, treat it as a -1, then proceed as discussed in the "Any Base to Decimal" section.

## Floating-Point Representation

### IEEE 754 Structure

#### Single Precision (32-bit)

```
| Sign | Biased Exponent | Normalized Mantissa |
|  1   |       8         |        23           |
```

#### Double Precision (64-bit)

```
| Sign | Biased Exponent | Normalized Mantissa |
|  1   |       11        |        52           |
```

### Fields

- **Sign**: Represents the sign of the floating-point number using signed magnitude encoding (0 = positive, 1 = negative)
- **Normalized Mantissa (Significand)**: Represents the significant digits of the number. The mantissa is **normalized**, meaning we move the decimal point so it falls in the range \\([1.0, 2.0)\\), but we implicitly store the 1, and explicitly store the digits after the decimal point (i.e., the fractional part).
- **Biased Exponent**: Determines the power of 2 by which to scale the mantissa. The exponent is **biased**, meaning we substract a constant bias to the actual exponent. For single precision, the bias is \\(127_{10}\\); for double precision, the bias is \\(1023_{10}\\)

> **Note**\
> The mantissa is actually 24 bits total in single precision, if we count the implicit number before the decimal point, and 53 bits total in double precision due to the implicit leading number.

## Converting Decimal to IEEE 754

To convert \\(12.375_{10}\\) to single precision IEEE 754:

**Step 1: Convert to binary**

\\(12.375_{10} = 1100.011_2\\)

**Step 2: Determine the sign**

Since it's a positive number, the sign bit is 0.

**Step 3: Normalize the mantissa**

\\(1100.011_2 = 1.100011_2 \times 2^3\\)

The normalized mantissa (fractional part only), padded to 23 bits, is: \\(10001100000000000000000_2\\)

**Step 4: Calculate the biased exponent**

Biased exponent = actual exponent + bias = \\(3 + 127 = 130 = 10000010_2\\)

**Step 5: Combine all fields**

```
| Sign | Exponent | Mantissa                |
|  0   | 10000010 | 10001100000000000000000 |
```

Final result: \\(01000001010001100000000000000000_2\\)

### Special Numbers

#### Denormalized Numbers

When calculations produce results that are too small for normal representation (i.e., below \\(1.0 \times 2^{1 - 127}\\) for single-precision and \\(1.0 \times 2^{1 -1023}\\) for double-precision) but are non-zero, we use denormalized representation. This is achieved by:

1. Setting the exponent field to all zeros (which corresponds to using the fixed exponent \\(1 -127\\) for single-precision or \\(1 - 1023\\) for double-precision)
2. Using an implicit leading 0 instead of 1 before the decimal point in the mantissa
3. Calculating the mantissa such that \\(0.\text{mantissa} \times 2^{1 -127}\\) (or \\(2^{1 - 1023}\\) for double-precision) equals the initial number's binary scientific notation.

#### Infinity

When calculations exceed the representable range (overflow) or a non-zero value divided by zero, the result is infinity. The exponent field becomes all ones and the mantissa is all zeros. The sign bit determines positive or negative infinity.

This allows programs to continue running with meaningful results rather than crashing on overflow.

#### NaN (Not a Number)

Represents mathematically undefined results. Like infinity, the exponent is all ones, but now the mantissa is non-zero. Any operation with NaN produces NaN, and
NaN is never equal to anything, including itself. It also has two types:
- Quiet NaN: Silently propagates through calculations
- Signaling NaN: Triggers an exception/error when encountered in operations

## Integer Overflow

Integer overflow occurs when you try to store a number that exceeds the maximum value that can be represented with the available number of bits, causing the result to wrap around to an unexpected value.

The overflowed result can be found as follows:
- Unsigned integer: \\(\text{(expected value)} \bmod 2^n\\)
- Signed Integer:
  - Positive overflow (i.e., \\(\text{expected value} > 2^{N-1} - 1\\)): \\(\text{expected value} - 2^n\\)
  - Negative overflow (i.e., \\(\text{expected value} < -2^{N-1}\\)): \\(\text{expected value} + 2^n\\)

## Integer Byte Order

**Byte order**, also known as **endianness** of a system defines how multi-byte values are assign to memory addresses.
- **Big endian Byte Order**: The most significant byte is stored at the lowest memory address.
- **Little endian Byte Order**: The least significant byte is stored at the lowest memory address.