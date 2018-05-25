# HELLO SWIFT!

## Basics

### Printing
---

'''swift

	/*:
	 # Hello, world!
	 */


로그 출력을 위한 함수 (Free Function)

'''

	print(3.14)
	
	var num = 1
	print(num)
	
	print("숫자", num)
	
	print("숫자 \(num)")
	
	print("숫자 " + String(num))


	/*:
	 ## Comment
	 [Quick Help Markup](https://goo.gl/YTge3C)
	 */
	 

###주석 (Comment)
---
 1. //  : 한 줄 주석
 2. /// : 한 줄 주석 + Quick Help Markup
 3. /* */ : 멀티 라인 주석  (Nested 가능)
	 
	 1. 빠르게 특정 부분의 코드를 비활성화
	 2. 협업 또는 인계 시 이해를 돕기 위해
	 3. 자기 자신을 위해
	 4. 문서화
	 
	 - 주석 없이도 쉽게 이해할 수 있을 만한 코드를 짜는 것이 베스트
	 

	''' swift
	print("Hello, world!")
	// print("Hello, world!")
	/// print("Hello, world!")
	
	/*
	 print("Hello, world!")
	 print("Hello, world!")
	 */
	
	/* This is also a comment
	 but is written over multiple lines. */
	
	/*
	 This is the start of the first multiline comment.
	 /* This is the second, nested multiline comment. */
	 This is the end of the first multiline comment.
	 */
	
	
	/*:
	 ## Semicolon (;)
	 - 각 라인의 마지막에 붙는 세미콜론은 옵션
	 - 한 라인에 여러 구문(다중 명령)을 사용하고 싶을 경우는 세미콜론 필수
	 */
	print(1); print(2); print(3);
	//print(1);
	//print(2);
	//print(3);
	



### Constants and Variables
---
 상수와 변수는 현재 어떤 데이터에 대한 상태값, 속성 정보 등을 담고 있는 컨테이너
 
* 상수 (Constants) : 한 번 설정되면 값 변경 불가
* 변수 (Variables) : 설정한 값을 변경 가능



'''swift

	let maximumNumberOfLoginAttempts = 10. //10
	maximumNumberOfLoginAttempts = 20	      //error (let은 constant 선언이기 때문에)	
	// currentLoginAttempt = 1             //error (currentLoginAttempt를 밑에 선언했기 때문에)
	var currentLoginAttempt = 0
	currentLoginAttempt = 1                //1
	


 1. 네이밍 확인 (의미, 방식, 길이 등)
 2. 네이밍 컨벤션
 3. 선언 순서



### Declare multiple constants or variables
--- 


'''swift

	var x = 0.0, y = 0.0, z = 0.0
	x = 1
	y = 2
	z = 3



### Naming
 ---
 영어 외에도 유니코드 문자를 포함한 대부분의 문자를 사용해 네이밍 가능

'''swift

	let π = 3.14159
	let 你好 = "你好世界"
	let 🐶🐮 = "dogcow"
	let 한글 = "세종대왕"
	let `let` = 1   // Swift 에서 사용되는 키워드일 경우 backquote(`) 를 이용해 사용 가능
	
	print(π)
	print(你好)
	print(한글)
	print(🐶🐮)
	print(`let`)



 변수로 사용할 수 없는 이름
 
 1. 같은 스코프 범위 내에서 중복되는 이름
 2. 공백문자
 3. 수학 기호 (√, ∑ 등)
 4. 화살표 (→, ← 등)
 5. 숫자로 시작하는 이름 (시작 부분 외에는 사용 가능)

'''swift

	// e.g.
	// let 한글 = "ㄱ"
	// let 공 백 = "X"
	// let √ = "root"
	// let → = "arrow"
	// let 369게임 = "12짝45짝..."


---

## Type Annotation & Type Inference

### Type Annotation
---
변수 선언 시 사용될 자료의 타입을 명확하게 지정하는 것

'''swift
	
	let year: Int = 10
	let language: String
	language = "Swift 4"
	var red, green, blue: Double
	red = 255.0
	green = 150.123
	blue = 75
	
	
### Type Inference
---
변수 선언 시 초기화로 사용되는 값의 타입을 통해 변수의 타입을 추론하여 적용하는 것

'''swift
	
	let name: String = "Tori"
	type(of: name)							//String.Type
	
	let age: Int = 4
	type(of: age)							//Int.Type
	
	var weight = 6.4
	type(of: weight)						//Double.Type	
	
	var spelling = ["T", "O", "R", "I"]
	type(of: spelling)						//Array<String>.Type
	
	
	

## Literals & Types


 * 상수 - 고정된 값 (메모리 주소) 을 가지는 심볼/식별자
 * 리터럴
   - 소스코드에서 고정된 값으로 표현되는 문자 (데이터) 그 자체
   - 정수 / 실수 / 문자 / 문자열 / 불리언 리터럴 등



### Numeric Literals
---

'''swift
	
	var signedInteger = 123	
	signedInteger = +123
	signedInteger = -123
	type(of: signedInteger)				//Int.Type
	
	let decimalInteger = 17				//17
	let binaryInteger = 0b10001			//17
	type(of: binaryInteger)				//Int.Type
	let octalInteger = 0o21				//17
	let hexadecimalInteger = 0x11		//17
	
	var bigNumber = 1_000_000_000
	bigNumber = 000_001_000_000_000
	bigNumber = 0b1000_1000_0000		//2176
	bigNumber = 0xAB_00_FF_00_FF		//734456119551
	

### Integer Types
---
 *  8-bit : Int8, UInt8
 * 16-bit : Int16, UInt16
 * 32-bit : Int32, UInt32
 * 64-bit : Int64, UInt64
 * Platform dependent : Int, UInt (64-bit on modern devices)

 메모리 사이즈를 알고 싶을 떄 MemroyLayout<>를 사용

'''swift

	var integer = 123
	integer = -123
	type(of: integer)
	
	var unsignedInteger: UInt = 123
	//unsignedInteger = -123
	type(of: unsignedInteger)			//UInt.Type
	
	
	MemoryLayout<Int>.size				//8
	Int.max								//9223372036854775807
	Int.min
	
	MemoryLayout<UInt>.size				//8
	UInt.max							//9223372036854775807
	UInt.min							//0
	
	MemoryLayout<Int8>.size				//1
	Int8.max							//127
	Int8.min							//-128
	
	MemoryLayout<UInt8>.size			//1
	UInt8.max							//255
	UInt8.min							//0
	
	MemoryLayout<Int16>.size			//2
	Int16.max							//3267
	Int16.min							//-3267
	
	MemoryLayout<UInt16>.size			//2
	UInt16.max							//65535
	UInt16.min							//0
	
	MemoryLayout<Int32>.size			//4
	Int32.max							//2147483647
	Int32.min							//-2147483647
	
	MemoryLayout<UInt32>.size			//4
	UInt32.max							//4294967295
	UInt32.min							//0
	
	MemoryLayout<Int64>.size			//8
	Int64.max							//9223372036854775807
	Int64.min							//-9223372036854775807
	
	MemoryLayout<UInt64>.size			//8
	UInt64.max 		  // Playground Bug	//9223372036854775807
	UInt64.min
	print(UInt64.max)				   // 18,446,744,073,709,551,615


#### Question
 - UInt에 음수를 넣으면?	
 	// q1 ->  error: Negative integer '-1' overflows when stored into unsigned type 'UInt8'		
 - Int8 에 127 을 초과하는 숫자를 넣으면?
 	// q2 -> error: Basics(1).playground:97:25: error: arithmetic operation '127 + 1' (on type 'Int8') results in an overflow
 - Int 에 Int32.max ~ Int64.max 사이의 숫자를 넣었을 경우 생각해야 할 내용은?
 	//  
 ---

''' swift

	//let q1: UInt8 = -1
	//let q2: Int8 = Int8.max + 1
	//let q2: Int8 = 127 + 1
	//let q2 = Int8(127 + 1)
	let q3 = Int(Int32.max) + 1				//2147483648
	
	//Int32.max + 1
	//Int64.max + 1
	
	 Int32.max
	 Int64.max
	
	// Overflow addition operator
	// 01111111  1000000
	
	Int8.max &+ 1							//-128
	Int32.max &+ 1							//-2147483648
	Int64.max &+ 1							//-9223372036854775808
	
	Int8.min &- 1							//127
	Int32.min &- 1							//2147483647
	Int64.min &- 1							//9223372036854775807



### Floating-point Literal
---

'''swift

	var floatingPoint = 1.23				//1.23
	floatingPoint = 1.23e4					//12300
	floatingPoint = 0xFp3					//120
	type(of: floatingPoint)					//Double.Type
	
	var floatingPointValue = 1.23			//1.23
	type(of: floatingPointValue)			//Double.Type // 기본적으로 소수는 Double로 지정.
	
	var floatValue: Float = 1.23			//1.23
	type(of: floatValue)					//Float.Type
	
	MemoryLayout<Float>.size				//4
	Float.greatestFiniteMagnitude	  		// FLT_MAX 3.402823e+38
	Float.leastNormalMagnitude   			// FLT_MIN 1.175494e-38
	
	MemoryLayout<Double>.size				//8
	Double.greatestFiniteMagnitude   		// DBL_MAX 1.797693134862316e+308
	Double.leastNormalMagnitude   			// DBL_MIN 2.225073858507201e-308


- Double - 최소 소수점 이하 15 자리수 이하의 정밀도
- Float - 최소 소수점 이하 6 자리수 이하의 정밀도
	- 부동 소수점이므로 소수점 이하의 정밀도는 변경 될 수 있음




### Boolean Literal
---
'''swift
	
	var isBool = true			//true
	type(of: isBool)			//Bool.Type
	
	isBool = false				//false
	//isBool = False			//Use of unresolved identifier 'False'
	//isBool = 1				//Cannot assign value of type 'Int' to type 'Bool'
	//isBool = 0				//Cannot assign value of type 'Int' to type 'Bool'
	
	let shouldChange: Bool = true		//true


### String Literal
---
'''swift
	
	let str = "Hello, world!"			//"Hello, world!"
	type(of: str)						//String.Type
	
	let str1 = ""						//""
	type(of: str1)						//String.Type
	
	var language: String = "Swift"		//"Swift"


###Character Literal
---

'''swift
	
	var nonCharacter = "C"
	type(of: nonCharacter)					//String.Type
	
	var character: Character = "C"
	type(of: character)						//Character.Type
	
	MemoryLayout<String>.size				//24
	MemoryLayout<Character>.size			//8
	
	character = " "
	type(of: character)						//Character.Type
	
	//character = ""
	//character = "string"


### Typealias
----
'''swift
	
	// typealias <#type name#> = <#type expression#>
	
	typealias AudioSample = UInt16
	
	var maxAmplitudeFound = AudioSample.min	//0
	var maxAmplitudeFound1 = UInt16.min		//0
	
	type(of: maxAmplitudeFound)			//UInt16.Type
	type(of: maxAmplitudeFound1)		//UInt16.Type
	



### Type Conversion
---
'''swift

	let height = Int8(5)
	let width = 10
	//let area = height * width	//error: Binary operator '*' cannot be applied to operands of type 'Int8' and 'Int'
	//print(area)
	
	
	let h = UInt8(25)		//25
	let x = 10 * h			//250
	print(x)					//"250\n"
	
	

##Basic Operators

###Terminology
---

'''swift

	
	let a = 123
	let b = 456
	let c: Int? = 789
	
	// Unary Operator (단항 연산자)
	-a
	// Prefix (전위 표기법)
	-a
	// Postfix (후위 표기법)
	c!
	// Binary Operator (이항 연산자)
	a + b
	// Infix (중위 표기법)
	a + b
	
	// Ternary Operator (삼항 연산자)
	// Swift 에서 삼항 연산자는 단 하나
	a > 0 ? "positive" : "negative"
	
	//if a > 0 {
	//  "positive"
	//} else {
	//  "negative"
	//}



### Assignment Operators
---

'''swift
	
	// Basic assignment operator
	var value = 0
	
	// Addition assignment operator
	value = value + 10						//10
	
	// Subraction assignment operator
	value = value - 5						//5
	
	// Multiplication assignment operator
	value = value * 2						//10
	
	// Division assignment operator
	value = value / 2						//5
	
	// Modulo assignment operator
	value = value % 2						//1
	
	// Compound Assignment Operators
	value += 10								//11
	value -= 5								//6
	value *= 2								//12
	value /= 2								//6
	value %= 2								//0
	
	// Swift does not support : value++ , value--
	
	//value++
	//value += 1
	//value = value + 1
	
	//var (x, y) = (1, 2)
	//if x = y {
	//  // This is not valid, because x = y does not return a value.
	//}


### Arithmetic Operators
---

'''swift

	// Unary plus opertor
	+a
	// Addition Operator
	a + b
	"Hello, " + "world"
	// Unary minus Operator
	-a
	// Subtraction Operator
	a - b
	// Multiplication Operator
	a * b
	// Division Operator
	b / a
	// Modulo operator
	b % a
	
	// 실수에서의 나눗셈
	let e = 123.4
	let f = 5.678
	
	// 나누기
	e / f										//21.73300457907714
	
	// 나머지1
	e.truncatingRemainder(dividingBy: f)   //4.162000000000007
	
	// 나머지2
	e.remainder(dividingBy: f)				  //-1.515999999999993
	
	
	let quotient = (e / f).rounded()		//22
	let remainder = e.remainder(dividingBy: f)	//-1.515999999999993
	let sum = f * quotient + remainder	//123.4
	
	
#### Precedence
---
'''swift
		
	1 + 2 * 3				//7
	1 + (2 * 3)				//7
	(1 + 2) * 3				//9
	
	1 + 2 * 3 + 3			//10
	1 + (2 * 3) + 3			//10
	1 + 2 * (3 + 3)			//13
	
	1 * 2 - 3				//-1
	(1 * 2) - 3				//-1
	1 * (2 - 3)				//-1


### Overflow Operators
---
'''

	// Overflow addition
	//var add: Int8 = Int8.max + 1		
	var add: Int8 = Int8.max &+ 1			//-128
	
	// Overflow subtraction
	//var subtract: Int8 = Int8.min - 1
	var subtract: Int8 = Int8.min &- 1	//127
	
	// Overflow multiplication
	//var multiplication: Int8 = Int8.max * 2
	var multiplication: Int8 = Int8.max &* 2		//-2
	
### Comparison Operators
---
'''swift

	// Equal to operator
	a == b
	
	// Not equal to operator
	a != b
	
	// Greater than operator
	a > b
	
	// Greater than or equal to operator
	a >= b
	
	// Less than operator
	a < b
	
	// Less than or equal to operator
	a <= b


### Logical Operators
---
'''swift

	
	// Logical AND Operator
	true && true						//true
	true && false						//false
	false && true						//false
	false && false					//false
	
	// Logical OR Operator
	true || true						//true
	true || false						//true
	false || true						//true
	false || false					//false
	
	// Logical Negation Operator
	!true								//false
	!false								//true
	
	
	// Combining Logical Operators
	let enteredDoorCode = true
	let passedRetinaScan = false
	let hasDoorKey = false
	let knowsOverridePassword = true
	
	var x = 0
	func addOne() -> Bool {
	  x += 1
	  print("111")
	  return true
	}
	
	
	if enteredDoorCode && passedRetinaScan || hasDoorKey || knowsOverridePassword {
	  print("Open the door")
	} else {
	  print("Can't open the door")
	}
	
	
	// Explicit Parentheses
	if (enteredDoorCode && passedRetinaScan) || hasDoorKey || knowsOverridePassword {
	  // ...
	} else {
	  // ...
	}
	


### Ternary Conditional Operator
---
'''swift

	
	a > 0 ? "positive" : "zero or negative"	// positive
	
	if a > 0 {
	  "positive"
	} else {
	  "zero or negative"
	}
			//positive

### Range Operator
---
'''swift

	// Closed Range Operator
	0...100
	
	for index in 1...5 {
	  print("\(index) times 5 is \(index * 5)")
	}
						//1 times 5 is 5
						//2 times 5 is 10
						//3 times 5 is 15
						//4 times 5 is 20
						//5 times 5 is 25
	
	// Half-Open Range Operator
	0..<100
	
	let names = ["Anna", "Alex", "Brian", "Jack"]
	let count = names.count
	for i in 0..<count {   // 0,1,2,3
	  print("Person \(i + 1) is called \(names[i])")
	}
	
						//Person 1 is called Anna
						//Person 2 is called Alex
						//Person 3 is called Brian
						//Person 4 is called Jack
	
	// One-Sided Ranges
	1...
	...100
	..<100
	
	
	//               0       1        2       3
	//let names = ["Anna", "Alex", "Brian", "Jack"]
	names[2...]		//["Brian", "Jack"]
	names[...2]		//["Anna", "Alex", "Brian"]
	names[..<2]		//["Anna", "Alex"]
	
	
	

