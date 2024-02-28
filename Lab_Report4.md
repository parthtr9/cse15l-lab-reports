# Lab Report 4 - Vim
## This lab report has steps 4 to 9 from the week-7 lab
---
---

**Step 4)** Log into ieng6:
   ![LoggingIntoServerWithoutPass](https://github.com/parthtr9/cse15l-lab-reports/assets/154461332/32f7c22b-ae2a-4d29-877d-c8e9d7167070)
   ---
   *Key pressed*:
   `<up>` `<enter>`
   > `ssh patrivedi@ieng6.ucsd.edu` was one up in search history, so I used up arrow to access it.


**Step 5)** Clone the forked repository from Github account:
   <img width="1182" alt="Screenshot 2024-02-27 at 7 09 55 PM" src="https://github.com/parthtr9/cse15l-lab-reports/assets/154461332/46f16a2c-c63e-4b2b-91b6-106baf41f07d">
   ---
   *Key pressed*:
   `git` `<space>` `clone` `<space>` `Command-v`
   > I typed `git clone` and pasted the `SSH` url that I copied after forking the `https://github.com/ucsd-cse15l-s23/lab7` repository.


**Step 6)** Running the tests:
   <img width="1184" alt="image" src="https://github.com/parthtr9/cse15l-lab-reports/assets/154461332/10362f0d-2f37-448a-83d4-3f7b7dfbcfb3">
   ---
  *Key pressed*:
  `cd` `<space>` `la` `<tab>` `<enter>`, `bash` `t` `<enter>`
  > I `cd`ed into the lab7/ directory then ran the bash command with test.sh as the argument.


**Step 7)** Editing code file to fix failing test:
   <img width="1184" alt="Screenshot 2024-02-27 at 8 07 54 PM" src="https://github.com/parthtr9/cse15l-lab-reports/assets/154461332/de5e9504-35f6-43d9-85af-3fe2a3f8bd23">
   ---
   *Key pressed*:
   `vim` `<space>` `L` `<tab>` `<space>` `.` `<tab>` `<enter>`, `43 j`, `11 l`, `x`, `i`, `2`, `<escape>`, `:wq!`
   > I typed vim then tabbed into the `ListExamples.java` file opening it in the vim editor, by pressing `43 j` I moved the cursor to the line I wanted to edit.
   > `11 l` moved the cursor to the character I wanted to change, pressing `x` deleted that character, pressing `i` entered the insert mode, changed the character to 2
   > exited the insert mode using the `escape` key. Typed `:wq!` to save the file and exit the vim editor.

    
**Step 8)** Running the tests after correcting file:
   <img width="1183" alt="Screenshot 2024-02-27 at 8 09 58 PM" src="https://github.com/parthtr9/cse15l-lab-reports/assets/154461332/abfddcbb-45e7-4c6d-acfc-556f42692048">
   ---
   *Key pressed*:
   `<up>` `<up>` `<enter>`
   > The command for running the test from **Step 6** was one up in the search history, so I used up arrow to access it.


**Step 9)** Commiting the file into github:
   <img width="1183" alt="Screenshot 2024-02-27 at 8 19 25 PM" src="https://github.com/parthtr9/cse15l-lab-reports/assets/154461332/75669cf2-cd94-4231-9831-2fcae1ff3e98">
   ---
   *Key pressed*:
   `git` `<space>` `add` `L` `<tab>` `<enter>`, `git` `<space>` `commit` `-m` `<space>` `lesgo` `<enter>`
   > I used the git command `add`to add the `ListExamples.java` file and committed it using the git `commit` command into the repositry using `lesgo` as the commit message.

---
---
    

   

   

