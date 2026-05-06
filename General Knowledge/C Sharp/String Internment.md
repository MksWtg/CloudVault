Prerequisites: [[Value Type vs Reference Type]]

In most programming languages, strings are reference types. So for the code:

```
string a = "hello"
string b = "hello"
```

Despite being created the same way and having the same contents, they point to different objects on the heap and are not exactly the same. 

```
if (a == b):
	print "equal"
else:
	print "not equal"
```

If we run the above code it will print "not equal".

But in C#, it will print "equal".

This is because the [[CLR]] 'interns' the string "hello"- it stores "hello" on the heap and any reference to any other string "hello" is replaced with a reference to this one.

So `a` and `b` are the same object, and they are equal.