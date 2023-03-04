# k213056_Assign_1

1: First we will download Kernel from kernel.org i did 4.19.272 Version [tarball] format. After it is downloaded extract the folder and in the extracted folder will make a new folder named 'hello'.

2: In that folder, Run a terminal, we'll make two files 'hello.c' (our task to run) and Makefile via terminal commands 'gedit hello.c' and gedit Makefile respectively

3: In hello.c write this code #include <linux/kernel.h> asmlinkage long sys_hello(void) { printk("Hello world\n"); return 0; }

4: In Makefile add this obj-y := hello.o 

![image](https://user-images.githubusercontent.com/126978743/222920767-91981863-0bae-4f62-a86b-9d522ad5cfca.png)

5: We have to add the system call entry into the syscall_64.tbl file which keeps the name of all the system. For doing this we will open that file by running command in terminal which will open a file

6: In the syscall_64.tbl file scroll down to line [334], in the next line put this line (which will be line 335), then save the file.

![image](https://user-images.githubusercontent.com/126978743/222920783-cd12fed3-5581-42f2-a365-aa183fb7dc69.png)

7: Now we have to add the prototype of our system call in the system’s header file. In kernel folder “/include/linux/syscalls.h” we have to add the prototype of our system call function in this file.

8: In this file we just have to add our function call in the system file by simply typing in the function name in the end, save it.

![image](https://user-images.githubusercontent.com/126978743/222920806-573ac72e-1096-4660-a0f0-13ed38039de4.png)

9: Open Makefile and in Extraversion put the value equal to the roll number

10: Press CTRL+F in the same file and search for "core-y", navigate to second instance and in the end of the line put " hello/"

![image](https://user-images.githubusercontent.com/126978743/222920855-dd8be608-93d8-4e08-bb89-c403476df535.png)

11: We have to create a config file for our kernel. First, we search for the current config, copy the config, typing “cp /boot/config-4.10.0-28-generic /workingdirectory”

12: We will now write the configuration file

13: We have to clean our processes in the kernel by typing “make clean -j1” , we now type “make -j1” to start building our kernel and then install modules through command "make modules_install install".

14: now we will restart ubuntu and then choose ubuntu version with our roll number

15: write "uname -r" in ubuntu to check if you have done correctly

16: now make a c file and write the following code to check if the system call you made works

![image](https://user-images.githubusercontent.com/126978743/222920958-8d83daa5-081c-42a1-ad33-3d0ad51e2fb2.png)

17: you can verify through writing "dmesg" in terminal

![image](https://user-images.githubusercontent.com/126978743/222920929-ddf939f9-961c-4f12-8925-2552b1f1a0c4.png)



