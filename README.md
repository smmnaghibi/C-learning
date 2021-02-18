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
