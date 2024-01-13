# Lab Report 1
Testing different cases with `cd` , `ls` and `cat` commands.

---
---
## `cd`
1. Using the command with no arguments:
   
   ```
   [user@sahara ~/lecture1]$ pwd
   /home/lecture1
   [user@sahara ~/lecture1]$ cd
   [user@sahara ~]$ pwd
   /home
   ```
   >Takes the user back to the home dierctory.
   
2. Using the command with a path to a directory as an argument:

   ```
   [user@sahara ~]$ pwd
   /home
   [user@sahara ~]$ cd lecture1
   [user@sahara ~/lecture1]$ pwd
   /home/lecture1
   ```
   >Takes the user to the specified directory.

3. Using the command with a path to a file as an argument:

   ```
   [user@sahara ~/lecture1]$ pwd
   /home/lecture1
   [user@sahara ~/lecture1]$ cd Hello.java
   bash: cd: Hello.java: Not a directory
   ```
   >Gives the user an error "Not a directory".

   ---

## `ls`
1. Using the command with no arguments:
   
   ```
   [user@sahara ~]$ pwd
   /home
   [user@sahara ~]$ ls
   lecture1
   ```
   >Gives the user the list of all the files and directories in the home directory.

2. Using the command with a path to a directory as an argument:

   ```
   [user@sahara ~]$ pwd
   /home
   [user@sahara ~]$ ls lecture1
   Hello.class  Hello.java  messages  README
   ```
   >Gives the user the list of all the files and directories in the argumnent directory.

3. Using the command with a path to a file as an argument:
  
   ```
   [user@sahara ~/lecture1/messages]$ pwd
   /home/lecture1/messages
   [user@sahara ~/lecture1/messages]$ ls en-us.txt
   en-us.txt
   ```
   >Gives the user the name of the test file.

---

## `cat`
1. Using the command with no arguments:
   
   ```
   [user@sahara ~]$ cat
   cat
   cat
   clear
   clear
   ```
   >Terminal gets stuck in a loop and prints whatever the user puts in the input.

2. Using the command with a path to a directory as an argument:

   ```
   [user@sahara ~]$ pwd
   /home
   [user@sahara ~]$ cat lecture1
   cat: lecture1: Is a directory
   ```
   >Gives the user an error "Is a directory".

3. Using the command with a path to a file as an argument:
  
   ```
   [user@sahara ~/lecture1]$ pwd
   /home/lecture1
   [user@sahara ~/lecture1]$ cat Hello.java
   import java.io.IOException;
   import java.nio.charset.StandardCharsets;
   import java.nio.file.Files;
   import java.nio.file.Path;

   public class Hello {
     public static void main(String[] args) throws IOException {
       String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
       System.out.println(content);
    }
   ```
   >Prints the content of the argument file.





