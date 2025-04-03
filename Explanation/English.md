# Explanation
  
This is very long, so we recommend using Menu.
The explanation of the new version is currently being updated.
  
## Menu
- [Var Types](#var-types)
- [Add Blocks](#about-blocks)
- [Output](#about-output)
- [Canvas](#about-canvas)
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
- [Execute](#execute)
- [Comment](#comment)
- [Value](#value)
- [Function](#function)
- [Method](#method)
- [Compute](#compute)
- [Timer](#timer)
- [Time](#time)
- [File](#file)
- [Output](#output)
- [Canvas](#canvas)

---
  
### Execute

---
   
#### Start Block
・The program starts from this Block.  
・We highly recommend this Block to exist only one in the program.  
・If more than 1, the program start from only one of the Blocks.  
  
---
  
#### Finish Block
・This program finishes by this Block.  
・This Block often have to exist in the program.  
・There can be some Blocks in the program.  
  
---
---
  
### Comment
  
---
  
#### Comment Block  
・This Block provides a comment function.    

---
---
  
### Value  
  
---
  
#### Literal Block  
・This Block is for using a literal value.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Type|Type name|type|none|
|Arg|Value|Value|all|none|
|Output|Output|Output|all|-|
    
---
  
#### Const(Dec) Block
・This Block declares a const.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|
|Arg|Type|Type name|type|none|
|Arg|Value|Value|all|none|
    
---
  
#### Const(Use) Block
・This Block is for using a const value.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|
|Output|Output|Output|all|-|
    
---
  
#### Var(Dec) Block
・This Block declares a variable.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|
|Arg|Type|Type name|type|none|
    
---
  
#### Var(Sub) Block
・This Block substitutes a value to variable. 
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|
|Arg|Value|Value|all|one|
    
---
  
#### Var(Use) Block
・This Block is for using a variable value.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|
|Output|Output|Output|all|-|
    
---
---
  
### Function
    
---
  
#### Action(Dec) Block
・This Block declares a function with no return value that consolidates the execution of multiple blocks.  
・Enter the name of the variable to which the value received as an argument in the function will be assigned for each argument.  
・If each variable is not declared before the function starts, it will be declared when the function starts, and if the variable is not declared before the function starts, it will be discarded when the function finishes executing.  
・If it is declared before the function starts, it must be a variable.  
・If no input is made within an argument or it is blank, the corresponding variable will not be declared. Therefore, no input is required when using the function.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Function name|name|none|
|Arg|Type1|Type of a function 1th argument|type|none|
|Arg|Arge1|Name of variable to substitute a function 1th argument|name|none|
|Arg|Type2|Type of a function 2th argument|type|none|
|Arg|Arge2|Name of variable to substitute a function 2th argument|name|none|
|Arg|Type3|Type of a function 3th argument|type|none|
|Arg|Arge3|Name of variable to substitute a function 3th argument|name|none|
|Arg|Type4|Type of a function 4th argument|type|none|
|Arg|Arge4|Name of variable to substitute a function 4th argument|name|none|
  
---
  
#### Action(Use) Block
・This Block executes the declared function.  
・If the specified function name represents a function that has a return value, the output will be unavailable.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Function name|name|none|
|Arg|Arge1|Value of function first argument|all|only|
|Arg|Arge2|Value of function second argument|all|only|
|Arg|Arge3|Value of function third argument|all|only|
|Arg|Arge4|Value of function fourth argument|all|only|
  
---
  
#### Func(Dec) Block
・This Block declares a function with a return value that consolidates the execution of multiple Blocks.  
・Return Value can be set in [Func(Return) Block](#funcreturn-block).   
・Return Value must be set.  
・This is like [Action(Dec) Block](#actiondec-block)  
  
---
  
#### Func(Use) Block
・This Block executes the declared function.  
・If the specified function name represents a function that does not return a value, the output value will be invalid, so do not use it.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Function name|name|none|
|Arg|Arge1|Value of function first argument|all|only|
|Arg|Arge2|Value of function second argument|all|only|
|Arg|Arge3|Value of function third argument|all|only|
|Arg|Arge4|Value of function fourth argument|all|only|
|Output|Output|Output|all|-|
  
---
  
#### Func(Return) Block
・When executed within a function, it will terminate the execution of that function.  
・The value to be returned by the function is specified as an argument.   
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Type|Type name of return value|type|none|
|Arg|Output||Value of return value|all|only|  
  
---
---
  
### Method
  
---
  
#### If Block
・This Block provides conditional branching.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Bool|Boolean|bool|none|
|実行|True|Destination of true pattern|exe|-|  
|実行|False|Destination of false pattern|exe|-|  
  
---
  
#### Loop Block
・This Block provides a loop process.  
・The loop process continues until it executes Loop(Break) Block.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|実行|Function|Destination|exe|-|  
  
---
  
#### Loop(Break) Block
・This Block stops the loop process.  
  
---
  
#### Async Block
・This Block provides a asynchronous process.  
・Since it run an asynchronous process, the next Block will be executed without waiting for the destination Block to be executed.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|実行|Function|Destination|exe|-|  
  
---
---
  
### Compute
  
---
  
#### Calculation Block
・This Block provides a calculation.
・Types of "Add","Subtract","Multiply","Divide","Remain"("+","-","×","÷","*","/","%","&","|") can be used.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Arge1|Number to be calculate|num|only|  
|Arg|Arge2|Number to calculated|num|only|  
|Arg|Kind|Cal Kind|enum|none|  
|Output|Output|Output|num|-|  
  
>Kind Enum : +, -, ×, ÷, *, /, %, &, |, plus, minus, multi, div, remain, and, or

>The output type is the type of the argument that can hold the larger value.  
>In the uint64 type, only calculations with unsigned integer types or float64 types are provided.  
  
---
  
#### Evaluation Block
・This Block provides a evaluation.  
・Types of "Equal", "Not equal","More or Equal","Less or Equal","More","Less" can be used.  
・Equivalent evaluation can be used in all types. Size evaluation can be used only in number types.
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Arge1|Value to be evaluated|all|one|  
|Arg|Arge2|Value to evaluate|all|one|  
|Arg|Kind|Type|enum|none|  
|Output|Output|Output|bool|-|  
  
>Evaluation Enum : ==, !=, >=, <=, >, <
  
---
  
#### Math(Const) Block
・This Block provides mathematical constants.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
|Output|Output|Output|float64|-|  
  
|Const Name|Description|
|:--:|:--|
|PI|Pi|
|Tau|Tau|
|E|Napier's constant|
  
---
  
#### Math(Func) Block
・This Block provides mathematical functions.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
|Arg|Arge1|Argument1|num|one|  
|Arg|Arge2|Argument2|all|one|  
|Output|Output|Output|float64|-|  
  
|Function Name|Description|Arge1|Arge2|Output|
|:--:|:--|:--:|:--:|:--:|
|Pow|Power|Base value|Exponent|=|
|Abs|Absolute value|=|-|=|
|Ceiling|The smallest integer value greater than or equal to the specified number|=|-|=|
|Floor|The largest integer value less than or equal to the specified number|=|-|=|
|Truncate|The integer part of the given number|=|-|=|
|Sign|A number representing the sign(1, -1, 0)|=|-|=|
|SquareRoot|Root(2root, square root)|=|-|=|
|CubeRoot|3Root(cube root)|=|-|=|
|Log|Logarithm|=|base|=|
|Log2|Log(base=2)|=|-|=|
|Log10|Log(base=10)|=|-|=|
|Sin|Sine|Angle in radians|-|=|
|Cos|Cosine|Angle in radians|-|=|
|Tan|Tangent|Angle in radians|-|=|
|Asin|Arc sine|=|-|Angle in radians|
|Acos|Arc cosine|=|-|Angle in radians|
|Atan|Arc tangent|=|-|Angle in radians|
|Sinh|Hyperbolic sine|Angle in radians|-|=|
|Cosh|Hyperbolic cosine|Angle in radians|-|=|
|Tanh|Hyperbolic tangent|Angle in radians|-|=|
|Asinh|Arc hyperbolic sine|=|-|Angle in radians|
|Acosh|Arc hyperbolic cosine|=|-|Angle in radians|
|Atanh|Arc hyperbolic tangent|=|-|Angle in radians|  
|Max|Whichever is bigger|=|=|=|
|Min|Whichever is smaller|=|=|=| 
  
> ＝ : no explanation  
> ー : invalid
  
---
  
#### Cast Block
・This Block provides a type conversion in number types.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|From|Type name before conversion|type|none|  
|Arg|To|Type name after conversion|type|none|  
|Arg|Value|Value|num|only|  
|Output|Output|Output|num|-|  
    
---
  
#### BoolOps(And) Block
・This Block gets the boolean logical conjunction of boolean values.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Bool1|Value1|bool|only|  
|Arg|Bool2|Valu2|bool|only|  
|Output|Output|Output|bool|-|  
    
---
  
#### BoolOps(Or) Block
・This Block gets the boolean logical disjunction of boolean values.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Bool1|Value1|bool|only|  
|Arg|Bool2|Value2|bool|only|  
|Output|Output|Output|bool|-|  
    
---
  
#### BoolOps(Not) Block
・This Block gets boolean logical negation of boolean value.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Bool|Value|bool|only|  
|Output|Output|Output|bool|-|  
    
---
  
#### ToString Block
・This Block provides a type conversion to string.
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Value|Value|all|only|  
|Output|Output|Output|string|-|  
    
---
  
#### ToNumber Block
・This Block provides a type conversion from string to num.
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Type|Type name after conversion|type|none|  
|Arg|Value|Value|string|only|  
|Output|Output|Output|num|-|  
  
---
---
  
### Timer
    
---
  
#### Timer(Create) Block
・This Block creates a timer.
・A timer events are executed at minimum intervals of 25 ms. However, they will be executed the same number of times as the number of events that occur during that time.  
・A timer events are executed by opening a separate Thread.
・The unit of duration is milliseconds.
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
|Arg|Dura|Event duration|int|one|  
|実行|Tick|Destination of the timer event|exe|-|  
    
---
  
#### Timer(Start) Block
・This Block starts a timer.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
    
---
  
#### Timer(Stop) Block
・This Block finishes a timer.
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
    
---
  
#### Timer(Kill) Block
・This Block removes a timer.
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
    
---
  
#### StopWatch(Create) Block
・This Block creates a stopwatch.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
    
---
  
#### StopWatch(Start) Block
・This Block starts a stopwatch.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
    
---
  
#### Timer(Stop) Block
・This Block stops a stopwatch.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
    
---
  
#### StopWatch(Reset) Block
・This Block resets a stopwatch.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
    
---
  
#### Timer(Restart) Block
・This Block restarts a stopwatch.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
    
---
  
#### Timer(Kill) Block
・This Block removes a stopwatch.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
    
---
  
#### Timer(Kill) Block
・Gets the current stopwatch time.  
・A stopwatch time is measured in milliseconds.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Name|Name|name|none|  
|Output|Output|Output|uint64|-|  
  
---
---
  
### Time
    
---
  
#### Wait Block
・Wait for a fixed period of time.  
・The unit of time is milliseconds.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Time|Time|int|one|  
  
---
---
  
### File
    
---
  
This is coming soon.
  
---
---
  
### Output
    
---
  
#### Output(Write) Block
・This Block writes the Input from Output.
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Value|Input|string|one|  
    
---
  
#### Output(Read) Block
・This Block gets from Output.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Line|Line Index|int|one|  
|Output|Output|Output|string|-|  
    
---
  
#### Output(Write) Block
・This Block resets Output.  
  
---
---
  
### Canvas
    
---
  
#### Canvas(Clear) Block
・This Block fills the Canvas with the specified color.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|Color|Color|color|one|  
    
---
  
#### Canvas(GetPixel) Block
・This Block gets the color of the specified location.  
・The size of the Canvas is 1280*720. Please set it so that it does not exceed that range. (0<=X<=1279, 0<=Y<=719)  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|X|LocateX|int|one|  
|Arg|Y|LocateY|int|one|  
|Output|Output|色|color|-|  
    
---
  
#### Canvas(SetPixel) Block
・This Block sets the color of the specified location.  
・The size of the Canvas is 1280*720. Please set it so that it does not exceed that range. (0<=X<=1279, 0<=Y<=719)  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|X|LocateX|int|one|  
|Arg|Y|LocateY|int|one|  
|Arg|Color|Color|color|one| 
    
---
  
#### DrawLine Block
・This Block draws a line at the specified location.   
・The size of the Canvas is 1280*720. Any drawing that exceeds this range will only be calculated and not drawn.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|X1|StartX|int|one|  
|Arg|Y1|StartY|int|one|  
|Arg|X2|EndX|int|one|  
|Arg|Y2|EndY|int|one|  
|Arg|Color|Color|color|one| 
|Arg|Weight|Weight|int|one|  
    
---
  
#### DrawRectangle Block
・This Block draws a rectangle at the specified location.  
・If you do not need to round the corners, set the corner radius to 0.  
・The size of the Canvas is 1280*720. Any drawing that exceeds this range will only be calculated and not drawn.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|X|X of left edge|int|one|  
|Arg|Y|Y of left edge|int|one|  
|Arg|Width|Width|int|one|  
|Arg|Height|Height|int|one|  
|Arg|Color|Color|color|one| 
|Arg|RadiusX|RadiusX|int|one|  
|Arg|RadiusY|RadiusY|int|one|  
|Arg|Weight|Weight|int|one|  
    
---
  
#### FillRectangle Block
・This Block fills a rectangle at the specified location.  
・If you do not need to round the corners, set the corner radius to 0.  
・The size of the Canvas is 1280*720. Any drawing that exceeds this range will only be calculated and not drawn.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|X|X of left edge|int|one|  
|Arg|Y|Y of left edge|int|one|  
|Arg|Width|Width|int|one|  
|Arg|Height|Height|int|one|  
|Arg|Color|Color|color|one| 
|Arg|RadiusX|RadiusX|int|one|  
|Arg|RadiusY|RadiusY|int|one|  
    
---
  
#### DrawText Block (short)
・This Block draws a string or character at the specified location.  
・The size of the Canvas is 1280*720. Any drawing that exceeds this range will only be calculated and not drawn.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|X|X of left edge|int|one|  
|Arg|Y|Y of left edge|int|one|  
|Arg|Width|Width|int|one|  
|Arg|Height|Height|int|one|  
|Arg|Color|Color|color|one| 
|Arg|Text|Text to draw|string, char|one|  
|Arg|Size|Font size|int|one|  
    
---
  
#### DrawText Block (middle)
・This Block draws a string or character at the specified location.  
・The size of the Canvas is 1280*720. Any drawing that exceeds this range will only be calculated and not drawn.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|X|X of left edge|int|one|  
|Arg|Y|Y of left edge|int|one|  
|Arg|Width|Width|int|one|  
|Arg|Height|Height|int|one|  
|Arg|Color|Color|color|one| 
|Arg|Text|Text to draw|string, char|one|  
|Arg|Size|Font size|int|one|  
|Arg|Font|Font name|string, char|one|  
|Arg|Fstyle|Font style|enum|none|  
|Arg|Fwght|Font weight|enum, int|none|  
|Arg|Wrap|Text wrap|enum|none|  
|Arg|Lspace|Line space|int|one|  
  
>Fstyle Enum : normal, italic, oblique
  
>Fwght Enum : 
>|Value|Content|
>|:--:|:--:|
>|normal|400|
>|thin|100|
>|extralight|200|
>|ultralight|200|
>|light|300|
>|regular|400|
>|medium|500|
>|semibold|600|
>|bold | 700|
>|extrabold|800|
>|ultrabold|800|
>|black|900|
>|heavy|900|
>|extrablack|950|
>|ultrablack|950|
  
>Wrap Enum : no, wrap
    
---
  
#### DrawCircle Block
・This Block draws a circle at the specified location.  
・The size of the Canvas is 1280*720. Any drawing that exceeds this range will only be calculated and not drawn.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|X|CenterX|int|one|  
|Arg|Y|CenterY|int|one|  
|Arg|Color|Color|color|one| 
|Arg|Radius|Radius|int|one|  
|Arg|Weight|Weight|int|one|  
    
---
  
#### FillCircle Block
・This Block fills a circle at the specified location.  
・The size of the Canvas is 1280*720. Any drawing that exceeds this range will only be calculated and not drawn.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|X|CenterX|int|one|  
|Arg|Y|CenterY|int|one|  
|Arg|Color|Color|color|one| 
|Arg|Radius|Radius|int|one|  
    
---
  
#### DrawEllipse Block
・This Block draws a ellipse at the specified location.  
・The size of the Canvas is 1280*720. Any drawing that exceeds this range will only be calculated and not drawn.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|X|CenterX|int|one|  
|Arg|Y|CenterY|int|one|  
|Arg|Color|Color|color|one| 
|Arg|RadiusX|RadiusX|int|one|  
|Arg|RadiusY|RadiusY|int|one|  
|Arg|Weight|Weight|int|one|  
    
---
  
#### FillEllipse Block
・This Block fills a ellipse at the specified location.  
・The size of the Canvas is 1280*720. Any drawing that exceeds this range will only be calculated and not drawn.  
|Kind|Name|Description|Type|In|
|:--:|:--:|:--:|:--:|:--:|
|Arg|X|CenterX|int|one|  
|Arg|Y|CenterY|int|one|  
|Arg|Color|Color|color|one| 
|Arg|RadiusX|RadiusX|int|one|  
|Arg|RadiusY|RadiusY|int|one|  
  
---
  
## About Output
 This cannot be written to except during runtime.  
 Click the "clear" button at the bottom right to reset it.  
   
---
  
## About Canvas
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
 In the current version, overlapping or spaces in variable names, constant names, stopwatch names, and timer names are not allowed. Spaces are not allowed in function names. This may change in the future.
