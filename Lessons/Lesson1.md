# Variables
## Motivation
Most times when creating a program we will need to store some informations to be used later. For that we use variables:

    int a = 10;
To declare a variable we need a type and a name. The type will tell our computer how much memory to reserve for our variable, while the name will serve as a reference so the programs knows with what variable we are dealing with.

## Primitive Types
There are many types in C++ and we can make our own if we want.  But some types are very important and come bundled in C++, those are called Primitive Types and are:

 - **Integer** (int) - Hold the information of an integer number like: 1, 2, 3, 4, 10, -1, -30.
 - **Floating Point** (float) - Stores the value of an decimal number like: 1.1, 2.001, 16.003, 3.1415.
 - **Character** (char) - Keeps the track of a single digit like: 'a', 'b', 'c'. *Important:* Remember to use quotation marks when declaring a char since 'A' is a character but A is just a variable name.
 - **Boolean** (bool) - Can store only two values: true or false. You can also use 1 or 0 that are equivalent to true and false respectively.
 - **Double Precision Floating Point** (double) - As the name suggest, it's a more precise version of float that needs more memory.

## Name
The main purpose of the name is so that the computer knows which of the variables we are talking about. However, the art of naming is understood by few. As variables hold information, a good name will give you and others a hint of what data is kept there. 

For example, if we have a variable that stores the number of books in a library it would be bad naming it "books" since we can be talking about lent, destroyed or even sold books. The best approach would be naming it all_books or library_books.

## Declaring
The act of creating a variable is commonly named declaring. In C++ to declare a variable we digit the variable type and name respectively.

    int example;

It's also possible to set an initial value to the variable, but it needs to be the same type as the variable. To define a initial value just type "=" after the variable and then the value.

    char example = 's';

 If a variable receives a value that's not of it's type it may convert it or result in an error.
 

    # Example will store a value of 5 since it's an int.
    int example = 5.5;

	# This other example will throw and error and stop our program
	char example = 5;
    
It's also possible set the initial value as an operation

    # This program will work and sum will have the value of 11
    int sum = 5 + 6;

 ## Acessing
 To get a value of a variable we just need to say it's name. For example, we can use it in a sum:
 

    int a = 5;
    int b = a + 3;

Since the computer doesn't know what 'a' is, it checks if there's an variable with this name and gets the value 5. Then, it calculates the sum of 5 + 3 and creates another variable 'b' with this value.

If we try to access a variable without declaring it the program will throw an error and stop.

    # This program will throw an error since a doesn't exists
    int b = a + 3;

The same will occur if we try the access a variable that we didn't declared yet.

    # This program will also throw an error
    int b = a + 3;
    int a = 5;

# Outputs
All of our program calculations are done in the processor and nothing is shown to us, only if we ask. In C++ we will use a strange function called cout (c + out) to print information to a console.

    cout << "Hello World";

This piece of code will print "Hello World" to the console. However, printing a static phrase wouldn't be of great help now. We can use this same function to print the content of a variable. This code below will print "10" to the console.


    int number = 10;
    cout << number;


 It`s also possible to join many outputs together in the same output with more "<<". The code below will print "10 - 20 - 40"
 

    int number1 = 10;
    int number2 = 20;
    int number3 = 40;
    
    cout << number1 << " - " << number2 << " - " << number3 << endl;

# Arrays
## Motivation
If we have a Music Store and want to keep in our program the names of all albums we have, we would need to create a thousand variables?

As you probably imagined, no. For that occasion we use an Array: an variable that hold a series of same type data.

    int numbers[3];

This code will generate a variable that stores the information of three numbers. It`s syntax is very close to a normal variable but, we must pass the size of the array.

## Defining
If you remember well, to define a variable, we need a type. Does the array uses the same types of a normal variable? Yes, every type is available to an array, the only difference is that while a variable hold one piece of data, an array can hold many more. 

The naming is also the same as a normal variable. However, as you can see from the code above, there's an extra "[3]" right after the name. This is the array size, the amount of data it can hold. We must tell it to our computer because of the same reason we tell it if it's an int or float: memory allocation.

Because arrays are also variables, we can define a start value. Any element of the array is contained inside curly brackets ("{}") and all but the last is followed of a comma.

    char name[5] = {"B","r","e","n","o"};

In the code above we are asking to our computer to spare enough memory to store an array of size 5 and type char. Altogether we are defining what kind of char we want to store. The program above will run just fine. 

## Acessing
Accessing values from the array is also very similar to a normal variable. Just digit the variable name followed of the position in which we want to access. **The position needs to be an int**.

    char name[5] = {"B","r","e","n","o"};
    cout << name[0] << endl;

The code above will print "B" which is the first element of the array. But why we used "0" if we want to access the first element of the array, wouldn't it be "1"? Well, no. In programming we usually start counting from 0 instead of 1, it's a convention. So by that standard, name[0] will return the **first** element while name[1] would return the **second** element and so forward. You should also notice that the last index of an array with size 5 is 4, so the code below shouldn't work:

    char name[5] = {"B","r","e","n","o"}; 
    cout << name[5] << endl;
    
   Accessing an array with an out of bounds index will result in an error. So, you should remember: arrays **always** start on **0** and **end** in the **size of array minus one**.
   

    char name[5] = {"B","r","e","n","o"};
    int start = 0;
    int end = 5 - 1;
    
    cout << name[start] << " - " << name[end]; 

The code above will print "B - o" which are the start and end of array name.

## Strings
A string is an array containing one or more characters. To make one we could use a normal array like:

    char name[5] = {"B","r","e","n","o"};
But, for our sake, C++ provide us with a variable type string which syntax is:

    string name = "Breno";

This way is much easier to handle phrases and names but, always remember, a string is nothing more than an array of characters. This imply that we can do things such:

    string name = "Breno";
    cout << name[0] << endl;
This code will print "B" that is the string's first letter or, as you can also say, the first element of a size 5 character array.  
 
 
# Loops

## Motivation
We already created a variable that can store the name of all albums in a store. But what if we want to print all of them? We would need to use "cout" a thousand times? 

Well, as you imagined, no. We can use loops when we want to do **repeated** tasks such as: **for each** album name in array print it; **while** there's album in an array, print it. There are many types of loops that are designed to suit certain situations.

## For

    for(int a = 0; a < 2; a++){
	    cout << a << endl;
    }
If you run the code above you'll notice that it prints a sequence of numbers from 0 to 1, but why? Every code inside those curly brackets ("{}") will be run x times starting by an number n. This number will be defined by the the "int a = 0;" part of code, that tells our loop where to begin and which variable to follow. The second part "a < 10;" is a Boolean that **while** it's true, our loop will execute the code bellow it. Finally, the third part "a++" is one line of code that will be run every time our loops execute the code inside the curly brackets ("{}"). We can think of this loop as follow steps:

 - We define a variable int a = 0.
 - "a < 2" is true since a = 0.
 - Execute the code "cout << a << endl";
 - Execute the code "a++".
 - "a < 2" is true since a = 1.
 - Execute the code "cout << a << endl";
 - Execute the code "a++".
 - "a < 2" is not true since a = 2.
 - Loop ends.
