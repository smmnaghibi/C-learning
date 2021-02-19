# C-learning
Hi, I want to share my experien in learning **C language**.
P.S. I'm not native English speaker so be ready for some
typo or bad grammer.

Hope you enjoy it.
## History
As a tradition in learning programming language I should start with the history of the C programming language.
For me it's a little boring so i put a link to learn about the histor.[History](https://en.wikipedia.org/wiki/C_(programming_language))

For writing code you need IDE to write code and compile it to see the out put. You can download and install any IDE which is better for your system and OS.
Here is the link to see the IDE comparison for C programmin.[IDE comparison](https://en.wikipedia.org/wiki/Comparison_of_integrated_development_environments#C/C++)

## The first step for coding
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
Here we define a variable called inp which is integer.
Now lets get the user input.By using ```scanf("%d",&inp)``` you can get input from user.
inside the `scanf` function you should put two value,first we need **digit**,so we use `%d`.then we need to store the input in specefic variable.We can do this by `&inp`.
Here we can print the the input.```printf("Your number is : %d",inp)```.Again we use `%d` to show we want digit(number) then use `,` and put the variable want to show.

<img src="https://uupload.ir/files/voy1_code.png" alt="scanf" width="300"/>
<img src="https://uupload.ir/files/54dm_res.png" alt="scanf-res" width="300"/>

Lets create a project to get two number from user and return the **addition(+),subtraction(-),multiplication(x),division(/)**.
Before dive into code,in C language we use `//` to write comment.comments are a useful tool to write some explanation about the code or just one line of the code.Remember compiler ignore all the comment,and don't run any thing that start with `//`.So be free to wirte the comment in your code.
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