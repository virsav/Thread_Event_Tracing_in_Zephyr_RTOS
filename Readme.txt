
#########################################################################################################################
***********************************************Course Information********************************************************
                            	        CSE 522: Real Time Embedded Systems           
                                                Sem - Spring 2021                     
                                            Arizona State University                    
                                          Instructor: Dr. Yann-Hang Lee                 
*************************************************************************************************************************
#########################################################################################################################



#########################################################################################################################
----------------------------------------------Assignment Information-----------------------------------------------------

Author: Viraj Savaliya          ; ASU ID - 

Assignment 3 : Thread Event Tracing in Zephyr RTOS

Date : 03/31/2021

-------------------------------------------------------------------------------------------------------------------------
---------------------------------------Instructions to Compile and Execute-----------------------------------------------

How patch was created:
Command - 'diff -Naur ./old_zephyr ./zephyr > assignment3.patch'
This command was used to create a patch named assignment3.patch from '~/zephyrproject' directory

How to use the patch:
Command - 'patch -p1 < assignment3.patch'
Use this command from '~/zephyrproject' directory to apply the changes in zephyr directory

How to Compile:
1. Goto '~/zephyrproject/zephyr' and open terminal
2. Set zephyr environment using 'source zephyr-env.sh'
3. Export environment variables 'export ZEPHYR_TOOLCHAIN_VARIANT=zephyr', 
   'export ZEPHYR_SDK_INSTALL_DIR=<sdk installation directory>'
5. Goto '~/zephyrproject/zephyr/samples/trace_app' from terminal
6. Make the script (runall) executable using the command 'sudo chmod +x runall'
7. Now you can run the script file 'runall' to build. Execute it using './runall'
8. The script file will delete the existing (if any) build directory and zephyr.strip file from current directory
   And then make a new build directory use cmake and make and then copy the zephyr.strip to your current directory

How to execute:
1. Copy the zephyr.strip file you got in '~/zephyrproject/zephyr/samples/trace_app' to
   your sd card under directory name kernel.
2. Insert the sd card on galileo board and connect board via FTDI cable with the machine.
3. Power on the board.
4. ssh terminal using '/dev/ttyUSB0' on speed '115200' in PUTTY session logging specifying the file name as 'logfile.txt'
   to store output logs from terminal at the file location.
5. Press Enter on boot option and then press enter for 'Zephyr Kernel'
6. Close the session after all dumped values are printed and entire session output will be saved in your log file.
7. Use the python script 'vcd_generator.py' provided in '~/zephyrproject/zephyr/samples/trace_app' to generate 'test.vcd'
   file from 'logfile.txt'
8. Open the vcd file in GTKwave to observe the waveforms

-------------------------------------------------------------------------------------------------------------------------
#########################################################################################################################



#########################################################################################################################
------------------------------------------------Sample Output------------------------------------------------------------


uart:~$ CSE 522: RTES - Thread tracing App
tracing_flag true
tracing_flag set
tracing_flag false
tracing_flag unset
0 task 0 11505178 3
1 task 1 11505212 3
2 task 2 11505243 3
3 task 3 11505275 3
4 task 4 11505308 3
5 task 5 11505339 3
6 task 0 11513940 0
7 task 0 11513941 1
8 task 0 11513943 1
9 task 0 11513946 6
10 task 0 11522521 7
11 task 0 11522525 0
12 task 0 11522526 1
13 task 0 11522528 1
14 task 0 11531110 0
15 task 0 11531111 1
16 task 1 11539895 0
17 task 1 11539897 1
18 task 1 11539899 1
19 task 1 11539901 6
20 task 1 11548683 7
21 task 1 11548687 0
22 task 1 11548688 1
23 task 1 11548690 1
24 task 0 11549459 4
25 task 1 11549462 1
26 task 0 11549463 1
27 task 0 11558039 0
28 task 0 11558040 1
29 task 0 11558042 1
30 task 0 11558044 6
31 task 0 11566617 7
32 task 0 11566621 0
33 task 0 11566622 1
34 task 0 11566624 1
35 task 0 11575205 0
36 task 0 11575206 1
37 task 1 11583262 0
38 task 1 11583263 1
39 task 0 11589367 4
40 task 2 11589370 1
41 task 0 11589372 1
42 task 0 11598508 0
43 task 0 11598508 1
44 task 0 11598510 1
45 task 0 11598512 6
46 task 0 11607086 7
47 task 0 11607089 0
48 task 0 11607090 1
49 task 0 11607091 1
50 task 0 11615671 0
51 task 0 11615672 1
52 task 2 11618808 0
53 task 2 11618809 1
54 task 2 11618811 1
55 task 2 11618813 6
56 task 1 11619296 4
57 task 2 11619299 1
58 task 1 11619300 1
59 task 1 11628085 0
60 task 1 11628086 1
61 task 1 11628088 1
62 task 1 11628090 6
63 task 0 11629273 4
64 task 1 11629276 1
65 task 0 11629278 1
66 task 0 11637857 5
67 task 0 11637859 0
68 task 0 11637860 1
69 task 1 11645468 7
70 task 1 11645472 0
71 task 1 11645473 1
72 task 1 11645475 1
73 task 1 11654265 0
74 task 1 11654266 1
75 task 2 11663024 7
76 task 0 11663027 4
77 task 2 11663032 1
78 task 0 11663034 1
79 task 0 11663037 0
80 task 0 11663038 1
.
.
.
.
990 task 0 13472199 1
991 task 0 13472201 1
992 task 0 13480780 0
993 task 0 13480781 1
994 task 1 13484967 4
995 task 2 13484970 1
996 task 1 13484972 1
997 task 1 13494119 0
998 task 1 13494120 1
999 task 1 13494122 1
Traced threads dumped

-------------------------------------------------------------------------------------------------------------------------
#########################################################################################################################
