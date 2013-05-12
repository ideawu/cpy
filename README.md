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

Relax and enjoy!
