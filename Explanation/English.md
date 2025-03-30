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
- [Variable name restrictions](#variable-name-restrictions)
    
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

>Literal values ​​of float16, float32, and float64 are recognized internally as the respective numeric types and are converted to the specified type at runtime before use.  
  
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
>The following shows things used as type name here.(However, these cannot be used as types of var.)
>|Name|Description|Syntax|
>|:--:|:--:|:--:|
>|name|Name for var, const, etc.|name|
>|type|Type name|uint8|
>|all|All type in [Var Type](#var-type)|-|
>|exe|Executable Block|-|
>|num|All type of number|0|
>|num|All type of integer|0|
>|enum|Block-unique enumeration|-|
    
  
### Menu
- [Execute]](#execute)
- [Comment](#comment)
- [Value](#value)
- [Function](#function)
- [Method](#method)
- [Compute](#compute)
- [Timer](#timer)
- [Time](#time)
- [File](#file)
- [Output](#output)
- [Canvas]](#canvas)

---
  
### Execute

---
  
  
---
  
## Output
 This cannot be written to except during runtime.  
 Click the "clear" button at the bottom right to reset it.  
   
---
  
## Canvas
 This cannot be written to except during runtime.  
 This is initialized when the parogram run. Its initial value is #FFFFFFFF.
 The Canvas size is 1280 * 720.
   
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
   
---
  
## Variable name restrictions
 In the current version, overlapping or spaces in variable names, constant names, and stopwatch names are not allowed. Spaces are not allowed in timer names or function names. This may change in the future.
