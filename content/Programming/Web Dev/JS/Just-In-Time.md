Modern JavaScript engines (like V8 in Chrome or SpiderMonkey in Firefox) use JIT compilation, essentially a mix of both [compilation](compiled.md) and [interpretation](interpreted.md).
- The code is initially translated into an intermediate format (like bytecode). 
-  During runtime, *frequently* *executed* parts of the code are compiled into machine code for faster performance. 
This approach offers a balance between the flexibility of interpretation and the speed of compiled languages.
#### So basically just compiled?

No. Because the whole code isn't compiled. Only frequent parts are compiled. Other parts might be interpreted.

Purpose? Good balance between speed and development flexibility.