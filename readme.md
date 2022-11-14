# **Go Overview**

### **Software Development fun facts**

All software(code) must be translated (compiled/interpreted) into the machine language of processor.

- **Compiled Language**: Translate intsructions once before running the code.
  - C, C++, Java (partially - byte code)
  - compiled executable = machine language code
  - compiled code is generally faster because translation does not happen everytime code is run.
- **Interpreted Language**: Translate instructions while code is excuted.
  - Python, JavaScript, Java(partially - JVM)
  - translation occurs on every execution. (slower)
  - makes coding easier
    - manage memory automatically (garbage collection)
    - infer variable types. (you dont have to state the type of the varaible before you can use them. eg. Int, String, ect)

#### Types of Programming Languages

- **Machine language**

  - Written directly to the CPU/Processor
  - CPU instructions represented in binary

- **Assembly Language**
  - 1:1 mappping to a machine language
  - CPU instructions with mnemonics (easier to read)
- **High Level language**
  - Commonly used (C, C++, Java, Python, Go, etc)

### **Adavntages of Go**

1. Runs Fast
   - Go is a compiled language with the good features of interpreted language.
1. garbage collection
1. simpler objects
   - Go uses `structs` a.k.a Data (different data that needs to be associated together)
   - no inheritance, constructors or generics
1. concurrency efficient
   - Goroutines, Channels, Select

### **How Code is Organized**

> Common organization is good for sharing.

There are three recommended subdirectories:

- `src` - contains source code files
- `pkg` - contains packages (libraries)
- `bin` - contains executables

### **Go Fun Facts**

- `go.mod` file is used to track dependencies (when your code imports packages contained in other modules).
- Workspace directory is defined by >the `GOPATH` variable

---

## **Variables**

- Initialize in the declaration

  ```go
  var x int = 100
  var x = 100
  ```

- Initialize after the declaration

  ```go
  var x int // declares but will be set to zero value (0).
  x = 100 // initialization
  ```

- Short variable declaration
  ```go
  x := 100 // declares and initializes. can only be done in a function.
  ```

### **Variable Scope**

The places in code where a variable can be accessed. Go is lexically scoped using blocks.

#### **Implicit Blocks**

- Universe block - all Go source code
- Package block - all source in a package
- `if`, `for`, `switch` - all code inside the statement
- `select`, `switch` clauses - individual clauses each get a block

#### **Implicit Blocks**

- File block
- Function block

### **Memory (Stack vs. Heap)**

- Stack is the area of the memory primarily dedicated to function calls.
- Stack stores local variables and deallocates then after function call is complete.
- Heap is the persistent area of the memory. Deallocation happens manually.

---

## **Data Types**

- **Pointers**

  - A pointer is an address to some data in memory.
  - `&` operator returns the address of a variable/function.
  - `*` operator returns data at an address (defreferencing).

  ```go
  var x int = 1
  var y int
  var ip *int // ip is ponter to int

  ip = &x // ip now points to x
  y = *ip // y is now 1
  ```

- **New**

  - An alternative way to create a variable
  - `new()` function creates a variable ad returns a pointer to the variable
  - variables are initialized to zero.

  ```go
  ptr := new(int) // returns a pointer to an integer
  *ptr = 3 // places the value 3 at the ptr address
  ```
