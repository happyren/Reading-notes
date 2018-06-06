# Absolute Java

## Array

An array behaves like a list of variables with a uniform naming mechanism that can be declared in a single line of simple code.

An variable represent in terms of array is **index variable**, or **subscripted variable**, **element**. Number inside the variable is called **index** or **subscript**. Number of variables is **length** or **size**. Variables in the array are of the same type which is **base type**.

The array is declared and defined: *Base_Type[] Array_Name = new Base_Type[length]*

The square bracket is used in three ways in using array:

1. **Create a type name**: *double[] number;*

2. **Bracket with a integer value as syntax of creating a new array**: *new double[10];*

3. **To name an index variable using index**: *number[9];*

- Array has only one public instance variable: *length*.

- *length* cannot be directly assigned value.

- Array index always starts with *0* end with *length-1*

- *Array Index Out Of Bound*, using array accessing non-existed index.

When initializing the array, the values for the various indexed variables are enclosed in braces and separated with commas: *int[] number = {1, 2, 3};* it is equivalent to:

*int[] number = new int[3];* *number[0] = 1;* *number[1] = 2;* *number[2] = 3;*

It could also be initialized with an array.

- **An array of characters is not a String**, assign a char array to String is illegal. But *String s1 = new String(char[] a)* is legal. And one can go with *String s1 = new String(a,2,3)* while *a* is an char array of length 10.

*public static void main(String[] args)* in side this main method identifier, the args is traditional, but it is perfectly legal to use others. If commandline no arguments is input, the default array of arguments would be generated.

**for-each loop**: *for(Array_Base_Type element : Array_Name) Statement* If the index is used for nothing but enumerate through the elements, then for each loop is prefered.

*public static int max(int... arg)* this is **vararg(Variable number of Argument)**, allows taking variable number of argument and form a array of arg.

For enum, *value* returns the value of the enum list as an array in that order.

## File IO

A **stream** is a flow of data. If the data flows into your program, then the stream is called an **input stream**. If the data flows out of your program, the stream is called an **output stream**.

**Text file** is **ASCII file** contains encoded data. **Binary file** is unencoded binary data.

A file has two names: (1) the real file name that is used by the operating system and (2) the name of the stream that is connected to the file.

### Text file

#### Writing

*PrintWriter* Class, combined with *FileOutputStream* Class.

FileOutputStream will alias a file with an output stream.

Using FileOutputStream to open a file and then use PrintWriter to write to the file.

*FileOutputStream* A file output stream is an output stream for writing data to a File or to a FileDescriptor.

*FileInputStream* A FileInputStream obtains input bytes from a file in a file system.

*FileReader* Convenience class for reading character files.

*FileWriter* Convenience class for writing character files.

*PrintWriter* uses *FileOutputStream*

*Scanner* uses *FileInputStream*

*BufferedReader* uses *FileReader*

*BufferedWriter* uses *FileWriter*

*errStream* Error stream let user to redirect the error message to a different location. Syntax is using

> *PrintStream errStream = new PrintStream(new FileOutputStream("errormessage.txt"))*

### Binary file

*File* class: An abstract representation of file and directory pathnames, is able to check properties of a file.

Binary file access, must has the object serialized, that is the object to be writen should *implements serializable*

*ObjectInputStream* An ObjectInputStream deserializes primitive data and objects previously written using an ObjectOutputStream.

*ObjectOutputStream* An ObjectOutputStream writes primitive data types and graphs of Java objects to an OutputStream.

## Interface

An interface is something like the extreme case of an abstract class. An interface is not a class. It is, however, a type that can be satisfied by any class that implements the interface.

*implements Interface_Name;* *implements SomeInterface, OtherInterface;*