
# 24F-CISC361-010  
**Project 3 - Digging into Xv6** 
---

## Overview  
In this project, we will explore the process table and scheduler in the Xv6 operating system. You will add a system call and a user program to test the system.

---

## Background  
This project can be completed on the class VM. All required software (except Xv6) is pre-installed.  

---

## Resources  
- [About Xv6](https://pdos.csail.mit.edu/6.828/2012/xv6.html)  
- [Xv6 Manual](https://pdos.csail.mit.edu/6.828/2018/xv6/book-rev11.pdf)  
- Local Mirrors: `Xv6.pdf`, `AddingUserProgramToXv6.pdf`, `AddNewSystemCallXv6.pdf`, `NewSystemCallToXv6.pdf`

---

## Tasks  

### Part 0: Create a Repository  
1. Create a repository named `CISC361 xv6` on [GitLab](https://gitlab.eecis.udel.edu).  
2. Clone the repository to the class VM using SSH.  
3. Add Xv6 code by running:  
   ```bash
   tar -xf /usa/roosen/xv6.tar
   git add . 
   git commit
   ```  
4. Compile and run Xv6 using:  
   ```bash
   make qemu-nox
   ```  
   Exit with `Ctrl-a x`.  

### Part 1: Modify the Scheduler  
1. Add a line to the `scheduler()` function in `proc.c` to print:  
   ```c
   printf("process [%s:%d] is running\n", process_name, pid);
   ```  
2. **Note:** Comment out this line after verifying it works.  

### Part 2: Add a User Program  
1. Follow [this guide](http://recolog.blogspot.com/2016/03/adding-user-program-to-xv6.html) to add a user program.  
2. Implement a program named `hello` that prints:  
   ```
   Hello, my name is <name>.
   ```  

### Part 3: Add a System Call  
1. Use [this guide](https://medium.com/@viduniwickramarachchi/add-a-new-system-call-in-xv6-5486c2437573) to add a system call.  
2. Add a system call `crsp()` to print running and sleeping processes.  
3. Use a lock to access `ptable` in `proc.c`.  

### Part 4: Use the `crsp()` System Call  
1. Write a program named `ps` in `ps.c` to test `crsp()`.  
2. Expected output:  
   ```
   name     pid     state  
   ---------------------------  
   init     1       SLEEPING  
   sh       2       SLEEPING  
   ps       5       RUNNING  
   ```  

---

## Rubric  

| **Criteria**                          | **Points** |  
|---------------------------------------|------------|  
| Part 1 (print statement)              | 10         |  
| Integration of a system call          | 20         |  
| Implementation of `crsp()`            | 25         |  
| Integration of `ps` program           | 15         |  
| Implementation of `ps` program        | 20         |  
| Integration of `hello` program        | 10         |  
| **Total**                             | **100**    |  

---

