
31p: "C++'s ability to be used effectively for applications that require work in a variety of application areas is an important strength. Applications that involve local- and wide-area networking, numerics, graphics, user interaction, and database access are common. Traditionally, such application areas were considered distinct and were served by distinct technical communities using a variety of programming languages. However, C++ is widely used in all of those areas, and more. It is designed so that C++ code can coexist with code written in other languages. Here, again, C++'s stability over decades is important. Furthermore, no really major system is written 100
% in a single langyuage. Thus, C++'s original design aim of interoperability becomes significant."

38p line1 : "This tour of C++ saves us from a strictly bottom-up presentation of language and library facilities by enabling the use of a rich set of acilities even in early chapters"

38p line18: "C++ is a compiled language. For a program to run, its source text has to be processed by a compiler, producing object files, which are combined by a linker yielding an excuteable program. A C++ program typically consists of many source code files (usually simply called source files).

38p line25: "Ths ISO C++ standard defines two kinds of entities. 1. Core language features, such as built-in types(e.g., char and int) and loops(e.g., for-statements and while-statements) 2. Standard-library components, such as containers (e.g., vector and map) and I/O operations (e.g., << and get line())"

39p line8: "Every C++ program must have exactly one global function named main(). The program starts by executing that function."

40p line15: "A declaration is a statement that introduces a name into the program. It specifies a type for the named entity." "A type defines a set of possible values and a set of operations (for an object)" "An object is some memory that holds a value of some type" "A value is a set of bits interpreted according to a type" "A variable is a named object"

46p : "The definition of count_x() assumes that the char* is a C-stype sting, that is, that the pointer pointes to a zero-terminated array of char. In olde code, 0 or NULL is typically used instead of nullptr. However, using nullptr eliminates potential confusion betweem intergers (such as 0 or NULL) and pointers (such as nullptr)"

47p line1: "We call the types that can be built from the fundamental types, the const modifier, and the declarator operators built-in types. C++'s set of built-in types and operations is rich, but deliberately low-level. They directly and efficiently reflect the capabilities of conventional computer hardware. However, they don't provide the programmer with high-level facilities to conveniently write advanced applications. Instead, C++ augments the built-in types and operations with a sophisticated set of abstraction mechanisms out of which programmers can build such high level facilities." "The C++ abstraction mechanisms are primarily designed to let programmers to simply and elegantly use such typs. Types bulit out of the built-in types using C++'s mechanisms are called user-defined types. They are referred to as classes and enumerations. Most of this book is devoted to the design, implementation, and use of user-defined types. They are referred to as classes and enuimerations. Most of this book is devoted to the design, implementation, and use of user defined types. The rest of this chapter presents the simplest and most funamental facilities for that."

47p : "The new operator allocates memory from an area called the free store (also known as dynamic memory and heap`)"

50p : "Access to elements is provided by a subscript"

52p : "C++ supports a notion of separate compilation where user code sees only declarations of types and functions used. The definitions of those types and functions are in separate source files and compiled separately. This can be used to organize a program into a set of semi-independent code fragments. Such separation can be used to minimize compilation times and to strictly enforce separation of logically distinct parts of a program (thus minimizing the chance of errors). A library is often a separately compiled code fragments (e.g., functions)."

53p: "Strictly speaking, using separate compilation isn't a language issue; it is an issue of how best to take advantage of a particular language implementation."

54p: "In addition to functions, classes, and enumerations, C++ offers namespaces as a mechanism for expressing that some declarations belong together and that their names shouldn't clash with other names. For example, I might want to experiment with my own complex number type." "Namespaces are primarily used to organize larger program componetsm such as libraries. They simplify the composition of a program out of separately developed parts."

60p: "The central language feature of C++ is the class."

60p: "Essentially all language facilities beyomd the fundmental types, operators, and statements exist to help define better classes or to use them more conveniently. By "better," I mean more correct, easier to maintain, more eficient, more elegant, easier to use, easier to read, and easier to reason about."

64p: "The technique of acquiring resources in a constructor and releasing them in a destructor, known as Resource Acquisition Is Initialization or RAII, allows us to eliminated "naked new operations," that is, to avoid allocations in general code and keep them buried inside the implementation of well-behaved abstractions." "Avoiding naked new and delete makes code far less error-prone and far easier to keep free of resource leaks"

65p: "The word virtual means "may be redefined later in a class derived from his one." Unsurprisingly, a function declared virtual is called a virtual function. A class derived from abstract-class provides an implementation for the class interface. The curious =0 syntax says the function is pure virtual; that is, some class derived from class must define the function. Thus, it is not possible to define an object that is just a class; a abstract-class can only serve as the interface to a class that implements its... A class with a pure virtual function is called an abstract class. 

## Chapter 4 
87P: "No significant program is written in just a bare programming language"

88P: "I very briefly present useful standard-library types, such as string, ostream, vector, map, unique_ptr, thread, regex. and complex, as well as the most common ways of using them."

89P: "It is generally in poor taste to dump every name from a namespace into the global namespace." "So, I don't prefix every use of a standard library name with std::. Nor do I '#include' the appropriate headers in every example."

93P: "By default, a whitespace character, such as a space, terminates the read, so if you enter "Eric Bloodaxe" pretending to be the ill-fated king of York, the response is still: Hello, Eric!" "You can read a whole line (including the terminating newline character) using the getline() function."

94P: "The standard strings have the nice property of expanding to hold what you put in them; you don't have to precalculate a maximum size. So, if you enter a couple of megabytes of semicolons, the program will echo pages of semicolons back at you."

94P: "A user-defined output operator takes its output stream (by reference) as its first argument and returns it as its result."