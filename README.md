Cpy - A C-like scripting language

Cpy is the real general purposed dynamic c-like syntax scripting language. __Cpy provides you a way to write Python codes in C syntax!__

## Hello World!

```js
// file: hello.cpy
printf("Hello World!\n");

$ cpy hello.cpy
Hello World!
$
```

## Reading from stdin

```js
// file: stdin.cpy
print "input 'q' to quit:";

while(true){
	printf("> ");
	line = stdin.readline();
	line = line.strip().lower();
	if(line == 'q'){
		print "bye.";
		break;
	}else{
		print 'your input:', repr(line);
	}
}
```

## classes and functions

```js
class A{
	public a = 0;
	public static s = 1;
	
	function init(a){
		this.a = a;
		print 'A init', a;
	}

	function f(a, b=1){
		return a + b;
	}
}

print A.s; // 1
a = new A(1); // A init 1
print a.f(1, 2); // 3
```

## Reusing Python codes

```js
import time; // Python's built-in time module
time.sleep(1);
```

## C-like vs Pythonic

### Whitespace indentation to delimit block is bad

Python’s syntax is said to be clear and elegant. It is good for small peace of codes, but not good for more than 100 lines of codes. I usually mis-understand the number of indents when first glance at a more than 10 lines block of codes after an if.

__And TAB vs SPACE is particularly annoying!__

The curly braces are quit clear and elegant, most people feel comfortable at curly braces.

### i++

i++ is very usefull.

### “this” is that!

Python requires you to put an unnecessary “self” as the first argument of a function definition in a class, but to omit it when invoking that function. What’s the meaning of that? It’s total garbage.

### Confusing expression of calling function in parent class

Couldn’t it be as simple as “parent.f()”?

### Useless lambda expression

The lambda body can only be a single expression – useless! Ah-ha, now you are regret for discriminating curly braces, aren’t you? Look at the really ELEGANT syntax of JavaScript’s anonymous function.

### Unwelcomed None/True/False

Just let those be: null, true, false. “i is None” is no more elegant than “i == null”.

### Implicit static variable(Non-primative default argument)

Non-primative default arguments in function definitions are implicitly static, that cause many hidden bugs by mistake.

### Cpy – The comfortable way to write Python codes in C syntax

Cpy is a C-like scripting language. Cpy codes are converted into python code first, then run by Python at the same time.

__Relax and enjoy!__
