# shell_development


myshell – Custom Shell in C for Ubuntu/Linux

 Developed by:
	•	Hala Ibraheem
	•	Aya Breaka
	•	Lina Tubail

 Project Overview 
myshell is a lightweight command-line interpreter (CLI) developed in the C programming 
language as part of an Operating Systems course. It replicates core functionalities of 
UNIX/Linux shells, allowing users to execute internal commands, run external programs, 
manage I/O redirection, execute batch files, and utilize background processing. 
This project offers a foundational understanding of how operating systems handle user 
commands, file redirection, and process creation using system calls like fork() and execvp(). 


 ️ File Structure 
 
File                            Description 
myshell.c Main logic: handles user input, command execution, batch/interactive modes 
myshell.h Header file: constants, environment variables, function prototypes 
utility.c Implements internal commands (cd, clr, echo, etc.) 
makefile Builds the project using GCC compiler 
readme.md Full documentation and usage guide

  Features 
• Interactive shell prompt 
• Batch file execution 
• Internal command support:  
           o cd, clr, dir, echo, pause, pwd, environ, help, quit 
• External command execution via fork() and execvp() 
• I/O Redirection (<, >, >>) 
• Background execution using & 
• Custom environment variables (shell, readme_path) 
• Modular and extensible codebase 


 ️ Installation & Compilation 
To compile the shell: 
make 
   This will generate an executable file named myshell. 


 How to Run :
Interactive Mode 
               ./myshell 
Batch Mode 
              ./myshell filename.txt 
The shell reads and executes all commands listed in the specified file. 


Example Commands 
cd .. 
clr 
dir /home/user 
echo Hello, World! 
pause 
ls > files.txt 
cat < input.txt 
echo Log Entry >> log.txt 
./script.sh & 


 Help System 
Use the built-in help command to get assistance on any topic: 
       help [topic] 
       
Examples: 
• help cd 
• help redirection 
• help more — view the complete manual 

 Supported Commands 
 
Command           Description 

cd             Change the current directory 
clr/clear      Clear the terminal screen 
dir            List contents of a directory 
echo           Display a message or file content 
environ        Display environment variables 
help           Show help topics and command usage  
myshell         Run shell in batch mode
pause          Wait for the user to press ENTER 
pwd            Print the current directory path 
quit/exit       Exit the shell gracefully



 I/O Redirection
 
myshell supports redirection of standard input and output: 
Symbol                          Meaning 
<                               Redirect input from a file 
>                               Redirect (overwrite) output  
>>                              Redirect (append) output

  
Example: 
        echo Hello < input.txt > output.txt 

 
 Background Execution 
 
To run any command in the background: 
         ./long_process.sh & 
	 
The shell will immediately return to the prompt without waiting for the process to finish.

️ File Paths & Special Characters 
• .. → parent directory 
• . → current directory 
• ~ → user's home directory 
• Use \ to escape spaces in filenames (e.g., file\ name.txt) 


 How myshell Works 
1. Displays prompt and waits for user input (or reads from batch file) 
2. Parses command and arguments 
3. Detects internal vs. external commands 
4. Handles redirection and background flags 
5. Executes command accordingly 
6. Repeats until quit or exit is entered 

 Sample Output 
/home/user/myshell$ echo Hello 
Hello 

/home/user/myshell$ dir . 
file1.txt file2.txt 

/home/user/myshell$ pause 
Press ENTER to continue... 

/home/user/myshell$ quit 
Sad to see you quit myshell :( 


 System Requirements 
• Linux (Ubuntu recommended) 
• GCC compiler 
• Terminal access 
• Optional: VirtualBox for sandboxed testing
