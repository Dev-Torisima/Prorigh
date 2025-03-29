# Explanation
  
This is very long, so we recommend using Menu.
  
## Menu
- [Var Types](#var-types)
- [Add Blocks](#about-blocks)
- [Output](#output)
- [Canvas](#canvas)
- [Log](#log)
- [Load or Save Program](#load-or-save-program)
- [About PTD File](#about-ptd-file)
- [About Thread](#about-thread)
    
---
  
## Var Types
|Name|Explanation|Syntax1|Syntax2|
|:--:|:--:|:--:|:--:|
|int8|signed 8bit integer|0|-|
|int16|signed 16bit integer|0|-|
|int32|signed 32bit integer|0|-|
|int64|signed 64bit integer|0|-|
|uint8|unsigned 8bit integer|0|-|
|uint16|unsigned 16bit integer|0|-|
|uint32|unsigned 32bit integer|0|-|
|uint64|unsigned 64bit integer|0|-|
|float16|16bit floating point number|0|0h|
|float32|32bit floating point number|0|0f|
|float64|64bit floating point number|0|0d|
|bool|boolean|true|false|
|char|character|'c'|-|
|string|character string|"str"|""|
|color|ARGB or RGB color|#FFFFFFFF|#FFFFFF|

>Literal values ​​of float16, float32, and float64 are converted to the respective numeric types internally for processing, so they are converted to the specified type at run time for use.  
  
>Integers are represented by the 0b prefix for binary, the 0o prefix for octal, no prefix for decimal, and the 0x prefix for hexadecimal.  
  
>The exponential representation of a floating-point number is a mantissa,  followed by e or E, followed by a exponent.

  
The following shows max and min value of each type.
  
|Name|Max Value|Min Value|
|:--:|:--:|:--:|
|int8|127|-128|
|uint8|255|0|
|int16|32767|-32768|
|uint16|65535|0|
|int32|2147483647|-2147483648|
|uint32|4294967295|0|
|int64|9223372036854775807|-9223372036854775808|
|uint64|18446744073709551616|0|
|float16|65504|-65504|
|float32|3.40282347e+38|-3.40282347e+38|
|float64|1.7976931348623157e+308|-1.7976931348623157e+308|
  
    
---
  
## About Blocks
  
---
  
## Output
 This cannot be written to except during runtime.  
 Click the "clear" button at the bottom right to reset it.  
   
---
  
## Canvas
 This cannot be written to except during runtime.  
   
---
  
## Log
 If an operation fails, the cause will be written. If an error or exception occurs during execution, a separate message will be written for each.  
 Click the "clear" button at the bottom right to reset.
   
---
  
## Load or Save Program
 Pressing the "Load" button at the bottom left will reset the board and load the selected file.  
 Click the "Save" button at the bottom left and the board will be saved to the selected file.  
 Press the "Clear" button at the bottom left to reset the board.
   
>The board includes Blocks, Output, Canvas and Log.
  
---
  
## About PTD File
 The file has a .ptd extension and is in binary format.  
   
---
  
## About Thread
 A maximum of 256 Threads are allowed. Note that the main program that begins with Start Block also has Thread (0). Therefore, the number of Threads that can be used within a program is 255.  
All Threads except Thread (0) will terminate (close) when execution within the Thread ends. If the number of Threads exceeds 256, the behavior is undefined.  
 Variables (including constants and other named values) can be used regardless of Thread.  
