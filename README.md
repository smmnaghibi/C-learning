# C-learning

Hi, I want to share my experien in learning **C language** as an Electrical Engineering.
P.S. I'm not native English speaker so be ready for some
typo or bad grammer.

Hope you enjoy it.
## History
### Session 0
As a tradition in learning programming language I should start with the history of the C programming language.
For me it's a little boring so i put a link to learn about the histor.[History](https://en.wikipedia.org/wiki/C_(programming_language))

For writing code you need IDE to write code and compile it to see the out put. You can download and install any IDE which is better for your system and OS.
Here is the link to see the IDE comparison for C programmin.[IDE comparison](https://en.wikipedia.org/wiki/Comparison_of_integrated_development_environments#C/C++)

## Input and Output
### Session 1
#### `printf` and `scanf`
For the begining of our journey, let's start C programmig with write the `Hello World` project.
```C
#include <stdio.h>

int main()
{
    printf("Hello World!\n");
    return 0;
}
```
first we shoul add header `standard input output`,then we should define the main function with the output format is int and name it **main**.Only the code inside the main function is executed.
the code shoud be inside the `{}`.then we want to print a formatted message the `Hello World!`by using ```printf()``` funcion.The message should be put in the`()`.then we use `\n` that means **new line**.
we call **\\** as an **escape character**.You can find more examples in this [link](https://en.wikipedia.org/wiki/Escape_character).
**Don't forget to put `;` at the end of the line.We want to say that the programm runs successfully, so we `return 0`.`0` means program runs seccessfully.

<img src="https://uupload.ir/files/gv2k_hello_world.png" alt="hello world" width="300"/>

What about if we want to get input fromt user?`scanf` funcion is the solution.First we should define a variable.
In this example we need an integer variable, so we use ```int inp;```.We have more variable type such as float,string,boolean,etc.[more informaition](https://en.wikipedia.org/wiki/C_data_types).
also you aren't able to use every name for variable name.We call them **Keywords or reserved keys**.[more informaition](https://en.wikipedia.org/wiki/C_(programming_language))
.Here we define a variable called inp which is integer.
Now lets get the user input.By using ```scanf("%d",&inp)``` you can get input from user.
inside the `scanf` function you should put two value,first we need **digit**,so we use `%d`.then we need to store the input in specefic variable.We can do this by `&inp`.
Here we can print the the input.```printf("Your number is : %d",inp)```.Again we use `%d` to show we want digit(number) then use `,` and put the variable want to show.

<img src="https://uupload.ir/files/voy1_code.png" alt="scanf" width="300"/>
<img src="https://uupload.ir/files/54dm_res.png" alt="scanf-res" width="300"/>

Lets create a project to get two number from user and return the **addition(+),subtraction(-),multiplication(x),division(/)**.
Before dive into code,in C language we use `//`  to comment just one line ane `/*  severl lines */` for commenting more than one line .comments are a useful tool to write some explanation about the code or just one line of the code.Remember compiler ignore all the comment,and don't run any thing that start with `//`.So be free to wirte the comment in your code.
P.S. for multiplication instead of using letter `x` use `*`.
```C
#include <stdio.h>

int main()
{
    int num1, num2;
    printf("Please enter the first number : ");
    scanf("%d",&num1);

    printf("\nPlease enter the second number : ");
    scanf("%d",&num2);

    int addition = num1 + num2;
    printf("\n%d + %d = %d",num1,num2,addition);

    int subtraction = num1 - num2;
    printf("\n%d - %d = %d",num1,num2,subtraction);

    int multiplication = num1 * num2;//for multiplication use * (shift + 8)
    printf("\n%d x %d = %d",num1,num2,multiplication);

    int division = num1 / num2;
    printf("\n%d / %d = %d",num1,num2,division);
    return 0;
}
```
## Conditional and Loop Statment(`if`,`else`,`while`)
### Session 2
#### `if` and `else`
One of the most important part of programming is conditional statement.You can define a condition to do sth only when the condition is True by using `if`.
When you want run sth when the condtion is False You can use `else` then write the body of else.using else sometimes is optional.
Here is the synatax:
```
if (condition)
{
    body if the condition is True
}
else
{
    body if the condition is False
}
```
**Recap** : the code inside the if only execute when the condition is True,otherwise the code inside the else execute.

E.g. Odd or Even this is a problem:
```C
#include <stdio.h>

int main()
{
    int inp;
    printf("Please enter a number : ");
    scanf("%d",&inp);

    if (inp % 2 == 0){ 
        printf("%d is even",inp);
    }
    else{
        printf("%d is odd",inp);
    }

    return 0;
}
```
Did you see we use `==` in if condition.`=` is assignment operator that puts the right side value in the left side value and `==` is equality operator to check is the right side value equal to left side value,return True if equal.
[more about relational operator](https://en.wikipedia.org/wiki/Operators_in_C_and_C%2B%2B)

Sometimes we need more than one condtion, then we use `else if`.Syntax
```
if (condition 1){
}
else if (condition 2){
}
else if (condition 3){
}
else if (condition 4){
}
.
.
.
else{
}
```
#### `while`
Sometime we want to execute a piece of code repetitively untile thie situation or the condition become True, then we use `while`.
We use `while` when we don't know how many times we want to execute the code.Syntax:

```
while (condition)
{
    the body execute forever until the condition is True,
    it means if the condition become True,it will stop excuting the code inside the while
}
```
> Be careful not to get stuck in infinite loop ;)

E.g. factorial:
```C
#include <stdio.h>

int main() //e.g. 5 factorial = 5! = 5 x 4 x 3 x 2 x 1
{
    int inp;
    printf("Please enter a number : ");
    scanf("%d",&inp);
    int multiplication = 1;
    while (inp > 1){
        multiplication *= inp;
        inp -= 1; // or we can use inp-- both of them means inp = inp - 1
        // the line above updating the program
    }
    printf("The answer is %d",multiplication);
    return 0;
}
```
Here is another example with more details in it.
```C
#include <stdio.h>

int main()
{
    int inp, addition = 0, counter = 0;
    while (1) // By put 1 in condition, the loop become infinite loop
    {
        printf("\nPlease enter a number : ");
        scanf("%d",&inp);
        if (inp == -1 ) break; // if we input -1 the program and loop will finish and print the result
        addition += inp;
        counter++;
    }
    float m = (float )addition / counter; // because int / int is int but we want a float as a result, we assign the addition as float
    printf("\nThe mean of the numbers is %0.2f\n",m); // %0.2f means we just want two numbers after dot
    return 0;
}
```
#### `for`
When you know how many times you want to execute some part of the code it's better to use `for`.
`for` is also a loop statement.Here is the syntax:
```
for ( init; condition; increment )
{
    the body of the for loop
}
```
Let's do the above example again,but this time use `for` loop:
```C
#include <stdio.h>

int main()
{
    int inp;
    printf("Please enter the number : ");
    scanf("%d",&inp);
    int mul = 1;
    for (int i = 1; i <= inp; i++)
    {
        mul *= i; // or mul = mul * i
    }
    printf("The answer is %d",mul);
    return 0;
}
```
> Which one is esier for you? `for` or `while` ?

#### `break` and `continue`
In loop sitiution c has a powerful tool called `break` and `continue`.
When we reach the `break` in code,the loop statement will finish even it has to repeat the code for several times.
The other side,when we reach `continue`,the loop statement only pass this step and go to the next step in loop.The example below will help you to understand better.

###### `break`
<img src="https://uupload.ir/files/grt5_break.png" alt="break" />

###### `continue`
<img src="https://uupload.ir/files/wy2_continue.png" alt="continue" />

Lets have another example that working like pow function (e.g. 2^3=8):
```C
#include <stdio.h>

int main()
{
    int tavan,base;
    printf("Please enter the base : ");
    scanf("%d",&base);
    printf("Please enter the tavan : ");
    scanf("%d",&tavan);
    int res = 1;
    for (int i = 0; i < tavan; i++)
    {
        res *= base;
    }
    printf("The answer is : %d",res);
    return 0;
}
```
#### `switch`
In C language, we also have `switch` function that is something like `if` and `else if` but is a simple way.
Here is the syntax of the switch:
```
switch (variable or expression)
{
	case a:
        expression;

	case b:
        expression;

	default: // acting like else
        expression;
}
```

Lets create a project for 2020 USA Election with `switch`.
The project will get the name and count them and finlly tell,who win.
F.Y.I:You'll get familiar with another type of variable called `char` that is for character and how to get only one character from user with `getchar()` funcion.
```C
#include <stdio.h>

int main()
{
    char name; // to store the name of the candidate
    int nBiden = 0; // number of vote for Biden
    int nTrump = 0; // number of vote for Trump
    printf("Enter the name of the cadidate : (b or B for Biden and t or T for Trump and f or F for finish)\n");
    while ((name = getchar()) != 'f' )
    {
        switch (name) {
            case 'b': // both b and B are accepted for the input
            case 'B':
                nBiden++;
                break;

            case 't': // both t ang T are accepted for the input
            case 'T':
                nTrump++;
                break;

            case 'f': // both f and F are accepted
            case 'F':
                break;

            default: // when the user inpute the wrong value that isn't expected
                break;
        }
        printf("Enter the name of the cadidate : (b or B for Biden and t or T for Trump and f or F for finish)\n");
    }
    int total;
    total = nTrump + nBiden; total vote
    if (nBiden > nTrump)
    {
        printf("Biden wins with %.2f",((float )nBiden/total)*100);
    }
    else
    {
        printf("Trump wins with %.2f",((float)nTrump/total)*100);
    }


    return 0;
}
``` 
#### `do while`
`Do while` is another type of loop statement and it's actually like `while`.The only difference between `while` and `do while` is in `do while` first execute the code and then check the condition,so it Warranty that the code execute atlest one time,but in `while` first check the codition and then if the condition was True the code inside the `while` execute.
Syntax of `do while`:
```
do{
    expression;
} while(condition);
```



## Appendix
- [Type of error](https://www.javatpoint.com/programming-errors-in-c)
- [Order of operation](https://en.wikipedia.org/wiki/Order_of_operations)

# To be continue ...😀