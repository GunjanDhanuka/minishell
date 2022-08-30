# Minishell (built using C++)

Programming Language Used: C++

Operating Systems Used: LINUX (Ubuntu 20.10)

Steps to run the code:
```
	1. Open the Linux Terminal and navigate to the project folder.
	2. $ g++ main.cpp
	3. $ ./a.out
```
This will bring the minishell in the terminal. 
Type 'help' and press Enter to see the list of inbuilt commands.


## PROBLEM STATEMENT: 
    The mini shell is designed to simulate the bash shell of UNIX kernel. In the simulation try to include as many functionalities as possible of the bash shell. The simulation should not only work well for LINUX external commands, but also include as many internal commands as possible. 
    
    Approach to be taken and elaboration:
    The basic program structure is shown below.
    Design Steps:
    a. To execute UNIX external commands. To do this system, call execv( ) has to be used.
    b. To make provision for all kinds of redirection possible, input(<), output(>) and append(>>).
    c. To make provision for piping (single level), in process creating two-child processes and executing commands separated by pipe ( | ).
	d. To ensure additional functionalities that are not executed by execv( ) such as environment variables, cd(all	variations), history and exit commands.


> TO VIEW THE DETAILED EXPLANATION OF THE CODE AND THE FUNCTION CALL GRAPHS, REFER TO Manual.pdf FILE IN THE PROJECT. IT CONTAINS VERY DETAILED EXPLANATION OF EACH AND EVERY FUNCTION USE AND ITS PARAMETERS AND RETURN TYPES (Created using Doxygen).

## FEATURES OF THE MINISHELL:-
	1. Supports commands like echo, cd which are not allowed in execvp().
	2. Supports external commands like ls, cat, etc.
	3. Has support for single-level piping (Eg: ls | wc).
	4. Has support for redirection operations (<, >, >>).
	5. Stores history in a file in the 'tmp' directory. Can be viewed using history command!
	6. Allows displaying, setting and unsetting of environment variables like HOME, PATH, TERM.
	7. Inbuilt commands like exit, help, printenv, setenv, cd, echo, unsetenv have been also implemented.
	8. Colorful terminal with different colours for the pwd, prompt and errors!

### NOTE:
	1. If the shell gets stuck at any point due to unforeseen reasons after executing a command, kindly press Enter key to get the prompt back.(I tried to 			trace the error but it doesn't happen every time even for a particular command). If this still doesn't work, press Ctrl+C to exit out of the 			program. 
	
	2. Make sure to not execute any potentially harmful commands using the shell, it is not a tool to play with and may cause permanent loss of data if 		used inappropriately.
	
	3. The default path to save the history file is "/tmp/history.txt". If you need to change it, please change the historyPath string at the top of the code and recompile the program.
	
	4. Please provide all commands with spaces between operators(especially pipes and redirection symbols) to avoid running into unneccesary parsing problems. While everything else is handled with respect to normal commands, take special care during the redirection operation to give spaces before and after the <, >, >> symbols.
