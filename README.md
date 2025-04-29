# pku-ics2021-lab-2--optimized-performance-of-a-pipelined-processor-solved
**TO GET THIS SOLUTION VISIT:** [PKU_ICS2021 Lab 2- Optimized Performance of a Pipelined Processor Solved](https://www.ankitcodinghub.com/product/pku_ics2021-arch-lab-optimizing-the-performance-of-a-pipelined-processor-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;113756&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;PKU_ICS2021  Lab 2- Optimized  Performance of a Pipelined Processor Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
1 Introduction

In this lab, you will learn about the design and implementation of a pipelined Y86-64 processor, optimizing both it and a benchmark program to maximize performance. You are allowed to make any semanticspreserving transformation to the benchmark program, or to make enhancements to the pipelined processor, or both. When you have completed the lab, you will have a keen appreciation for the interactions between code and hardware that affect the performance of your programs.

The lab is organized into three parts, each with its own handin. In Part A you will write some simple Y86-64 programs and become familiar with the Y86-64 tools. In Part B, you will extend the SEQ simulator with a new instruction. These two parts will prepare you for Part C, the heart of the lab, where you will optimize the Y86-64 benchmark program and the processor design.

2 Logistics

You will work on this lab alone.

Any clarifications and revisions to the assignment will be posted on the course Web page.

3 Handout Instructions

1. You can do the lab on Linux and Mac systems.

2. To build the Y86-64 tools, you need install the following libraries : flex, bison. On Ubuntu systems, you can use the command: sudo apt install flex bison

3. Start by copying the file archlab-handout.tar to a (protected) directory in which you plan to do your work.

4. Then give the command: tar xvf archlab-handout.tar. This will cause the following files to be unpacked into the directory: README, Makefile, sim.tar, archlab.pdf, and simguide.pdf.

5. Next, give the command tar xvf sim.tar. This will create the directory sim, which contains your personal copy of the Y86-64 tools. You will be doing all of your work inside this directory.

6. Finally, change to the sim directory and build the Y86-64 tools

unix&gt; cd sim unix&gt; make clean; make

4 Part A

You will be working in directory sim/misc in this part.

Your task is to write and simulate the following three Y86-64 programs. The required behavior of these programs is defined by the example C functions in examples.c. Be sure to put your name and ID in a comment at the beginning of each program. You can test your programs by first assemblying them with the program YAS and then running them with the instruction set simulator YIS.

In all of your Y86-64 functions, you should follow the x86-64 conventions for passing function arguments, using registers, and using the stack. This includes saving and restoring any callee-save registers that you use.

sum.ys: Iteratively sum linked list elements

Write a Y86-64 program sum.ys that iteratively sums the elements of a linked list. Your program should consist of some code that sets up the stack structure, invokes a function, and then halts. In this case, the function should be Y86-64 code for a function (sumlist) that is functionally equivalent to the C sumlist function in Figure 1. Test your program using the following three-element list:

# Sample linked list

.align 8 ele1:

.quad 0x00a

.quad ele2 ele2:

.quad 0x0b0

.quad ele3 ele3:

.quad 0xc00

.quad 0

rsum.ys: Recursively sum linked list elements

Write a Y86-64 program rsum.ys that recursively sums the elements of a linked list. This code should be similar to the code in sum.ys, except that it should use a function rsumlist that recursively sums a list of numbers, as shown with the C function rsumlist in Figure 1. Test your program using the same three-element list you used for testing list.ys.

bubble.ys: Sort a block of ints(8 byte) in ascending order using bubble-sort

Your program should consist of code that sets up a stack frame, invokes a function bubblesort, and then halts. The function should be functionally equivalent to the C function bubblesort shown in Figure 1. Test your program using the following six-element source and destination blocks:

.align 8 Array:

.quad 0xbca

.quad 0xcba

.quad 0xacb

.quad 0xcab

.quad 0xabc

.quad 0xbac

5 Part B

You will be working in directory sim/seq in this part.

Your task in Part B is to extend the SEQ processor to support the iaddq, described in Homework problems

4.51 and 4.52, and jm, described as:

• jm rB, V: Jump to the instruction located at M[rB+V].

To add these instructions, you will modify the file seq-full.hcl, which implements the version of SEQ described in the CS:APP3e textbook. In addition, it contains declarations of some constants that you will need for your solution.

Your HCL file must begin with a header comment containing the following information:

• Your name and ID.

1 /* linked list element */

2 typedef struct ELE {

3 long val;

4 struct ELE *next; 5 } *list_ptr;

6

7 /* sum_list – Sum the elements of a linked list */

8 long sum_list(list_ptr ls)

9 {

10 long val = 0;

11 while (ls) {

12 val += ls-&gt;val;

13 ls = ls-&gt;next;

14 }

15 return val;

16 }

17

18 /* rsum_list – Recursive version of sum_list */

19 long rsum_list(list_ptr ls)

20 {

21 if (!ls)

22 return 0;

23 else {

24 long val = ls-&gt;val;

25 long rest = rsum_list(ls-&gt;next);

26 return val + rest;

27 }

28 }

29

30 /* bubble_sort – Sort long numbers at data in ascending order */

31 void bubble_sort(long *data, long count)

32 {

33 long *i, *last;

34 for(last = data + count – 1; last &gt; data; last–) {

35 for(i = data; i &lt; last; i++) {

36 if(*(i + 1) &lt; *i) {

37 long t = *(i + 1);

38 *(i + 1) = *i;

39 *i = t;

40 }

41 }

42 }

43 }

Figure 1: C versions of the Y86-64 solution functions. Seesim/misc/examples.c

• A description of the computations required for the iaddq instruction. Use the descriptions of irmovq and OPq in Figure 4.18 in the CS:APP3e text as a guide.

• A description of the computations required for the jm instruction. Use the descriptions of popq in Figure 4.20 in the CS:APP3e text as a guide.

Building and Testing Your Solution

Once you have finished modifying the seq-full.hcl file, then you will need to build a new instance of the SEQ simulator (ssim) based on this HCL file, and then test it:

• Building a new simulator. You can use make to build a new SEQ simulator: unix&gt; make clean; make VERSION=full

This builds a version of ssim that uses the control logic you specified in seq-full.hcl. To save typing, you can assign VERSION=full in the Makefile.

• Testing your solution on a simple Y86-64 program. For your initial testing, we recommend running simple programs such as asumi.yo (testing iaddq) and asumj.yo (testing jm)in TTY mode, comparing the results against the ISA simulation:

unix&gt; ./ssim -t ../y86-code/asumi.yo unix&gt; ./ssim -t ../y86-code/asumj.yo

unix&gt; ./ssim -g ../y86-code/asumi.yo unix&gt; ./ssim -g ../y86-code/asumj.yo

• Retesting your solution using the benchmark programs. Once your simulator is able to correctly execute small programs, then you can automatically test it on the Y86-64 benchmark programs in ../y86-code: unix&gt; (cd ../y86-code; make testssim)

This will run ssim on the benchmark programs and check for correctness by comparing the resulting processor state with the state from a high-level ISA simulation. Note that none of these programs test the added instructions. You are simply making sure that your solution did not inject errors for the original instructions. See file ../y86-code/README file for more details.

• Performing regression tests. Once you can execute the benchmark programs correctly, then you should run the extensive set of regression tests in ../ptest. To test everything except iaddq and jm:

unix&gt; (cd ../ptest; make SIM=../seq/ssim)

1 /*

2 * ncopy – copy src to dst, returning number of positive ints 3 * contained in src array.

4 */

5 word_t ncopy(word_t *src, word_t *dst, word_t len)

6 {

7 word_t count = 0;

8 word_t val;

9

10 while (len &gt; 0) {

11 val = *src++;

12 *dst++ = val;

13 if (val &gt; 0)

14 count++;

15 len–;

16 }

17 return count;

18 }

Figure 2: C version of the ncopy function. Seesim/pipe/ncopy.c.

To test your implementation of iaddq: unix&gt; (cd ../ptest; make SIM=../seq/ssim TFLAGS=-i)

To test your implementation of jm:

unix&gt; (cd ../ptest; make SIM=../seq/ssim TFLAGS=-j) To test both iaddq and jm: unix&gt; (cd ../ptest; make SIM=../seq/ssim TFLAGS=-ij)

For more information on the SEQ simulator refer to the handout CS:APP3e Guide to Y86-64 Processor Simulators (simguide.pdf).

6 Part C

You will be working in directory sim/pipe in this part.

The ncopy function in Figure 2 copies a len-element integer array src to a non-overlapping dst, returning a count of the number of positive integers contained in src. Figure 3 shows the baseline Y86-64 version of ncopy. The file pipe-full.hcl contains a copy of the HCL code for PIPE, along with a declaration of the constant value IADDQ.

Your task in Part C is to modify ncopy.ys and pipe-full.hcl with the goal of making ncopy.ys run as fast as possible.

1 ################################################################## 2 # ncopy.ys – Copy a src block of len words to dst.

3 # Return the number of positive words (&gt;0) contained in src.

4 #

5 # Include your name and ID here.

6 #

7 # Describe how and why you modified the baseline code.

8 #

9 ##################################################################

10 # Do not modify this portion 11 # Function prologue.

12 # %rdi = src, %rsi = dst, %rdx = len 13 ncopy:

14

15 ##################################################################

16 # You can modify this portion

17 # Loop header

18 xorq %rax,%rax # count = 0; 19 andq %rdx,%rdx # len &lt;= 0?

20 jle Done # if so, goto Done:

21

22 Loop: mrmovq (%rdi), %r10 # read val from src… 23 rmmovq %r10, (%rsi) # …and store it to dst 24 andq %r10, %r10 # val &lt;= 0?

25 jle Npos # if so, goto Npos:

26 irmovq $1, %r10

27 addq %r10, %rax # count++

28 Npos: irmovq $1, %r10

29 subq %r10, %rdx # len–

30 irmovq $8, %r10

31 addq %r10, %rdi # src++

32 addq %r10, %rsi # dst++

33 andq %rdx,%rdx # len &gt; 0?

34 jg Loop # if so, goto Loop:

35 ##################################################################

36 # Do not modify the following section of code 37 # Function epilogue.

38 Done:

39 ret

40 ##################################################################

41 # Keep the following label at the end of your function 42 End:

Figure 3: Baseline Y86-64 version of the ncopy function. Seesim/pipe/ncopy.ys.

You will be handing in two files: pipe-full.hcl and ncopy.ys. Each file should begin with a header comment with the following information:

• Your name and ID.

• A high-level description of your code. In each case, describe how and why you modified your code.

Coding Rules

You are free to make any modifications you wish, with the following constraints:

• Your ncopy.ys function must work for arbitrary array sizes. You might be tempted to hardwire your solution for 64-element arrays by simply coding 64 copy instructions, but this would be a bad idea because we will be grading your solution based on its performance on arbitrary arrays.

• Your ncopy.ys function must run correctly with YIS. By correctly, we mean that it must correctly copy the src block and return (in %rax) the correct number of positive integers.

• The assembled version of your ncopy file must not be more than 1000 bytes long. You can check the length of any program with the ncopy function embedded using the provided script check-len.pl: unix&gt; ./check-len.pl &lt; ncopy.yo

• Your pipe-full.hcl implementation must pass the regression tests in ../y86-code and ../ptest (without the -ij flags that tests iaddq and jm).

Building and Running Your Solution

In order to test your solution, you will need to build a driver program that calls your ncopy function. We have provided you with the gen-driver.pl program that generates a driver program for arbitrary sized input arrays. For example, typing

unix&gt; make drivers

will construct the following two useful driver programs:

• sdriver.yo: A small driver program that tests an ncopy function on small arrays with 4 elements. If your solution is correct, then this program will halt with a value of 2 in register %rax after copying the src array.

• ldriver.yo: A large driver program that tests an ncopy function on larger arrays with 63 elements. If your solution is correct, then this program will halt with a value of 31 (0x1f) in register %rax after copying the src array.

Each time you modify your ncopy.ys program, you can rebuild the driver programs by typing

unix&gt; make drivers

Each time you modify your pipe-full.hcl file, you can rebuild the simulator by typing

unix&gt; make clean; make psim VERSION=full

If you want to rebuild the simulator and the driver programs, type

unix&gt; make VERSION=full

To test your solution on a small 4-element array, type

unix&gt; ./psim sdriver.yo

To test your solution on a larger 63-element array, type

unix&gt; ./psim ldriver.yo

To test your solution on GUI mode, type

unix&gt; ./psim -g sdriver.yo

and

unix&gt; ./psim -g ldriver.yo

instead.

Once your simulator correctly runs your version of ncopy.ys on these two block lengths, you will want to perform the following additional tests:

• Testing your driver files on the ISA simulator. Make sure that your ncopy.ys function works properly with YIS:

unix&gt; make drivers unix&gt; ../misc/yis sdriver.yo

• Testing your code on a range of block lengths with the ISA simulator. The Perl script correctness.pl generates driver files with block lengths from 0 up to some limit (default 65), plus some larger sizes. It simulates them (by default with YIS), and checks the results. It generates a report showing the status for each block length:

unix&gt; ./correctness.pl

This script generates test programs where the result count varies randomly from one run to another, and so it provides a more stringent test than the standard drivers.

If you get incorrect results for some length K, you can generate a driver file for that length that includes checking code, and where the result varies randomly:

unix&gt; ./gen-driver.pl -f ncopy.ys -n K -rc &gt; driver.ys unix&gt; make driver.yo unix&gt; ../misc/yis driver.yo

The program will end with register %rax having the following value:

0xaaaa : All tests pass.

0xbbbb : Incorrect count

0xcccc : Function ncopy is more than 1000 bytes long.

0xdddd : Some of the source data was not copied to its destination.

0xeeee : Some word just before or just after the destination region was corrupted.

• Testing your pipeline simulator on the benchmark programs. Once your simulator is able to correctly execute sdriver.ys and ldriver.ys, you should test it against the Y86-64 benchmark programs in ../y86-code: unix&gt; (cd ../y86-code; make testpsim)

This will run psim on the benchmark programs and compare results with YIS.

• Testing your pipeline simulator with extensive regression tests. Once you can execute the benchmark programs correctly, then you should check it with the regression tests in ../ptest. For example, if your solution implements the iaddq instruction, then

unix&gt; (cd ../ptest; make SIM=../pipe/psim TFLAGS=-i)

• Testing your code on a range of block lengths with the pipeline simulator. Finally, you can run the same code tests on the pipeline simulator that you did earlier with the ISA simulator

unix&gt; ./correctness.pl -p

7 Evaluation

The lab is worth 190 points: 30 points for Part A, 60 points for Part B, and 100 points for Part C.

Part A

Part A is worth 30 points, 10 points for each Y86-64 solution program. Each solution program will be evaluated for correctness, including proper handling of the stack and registers, as well as functional equivalence with the example C functions in examples.c.

The programs sum.ys and rsum.ys will be considered correct if the graders do not spot any errors in them, and their respective sumlist and rsumlist functions return the sum 0xcba in register %rax.

The program bubble.ys will be considered correct if the graders do not spot any errors in them, and the bubblesort function sorts the 6 integers correctly in ascending order, with the results in the same 48 bytes beginning at address Array, and does not corrupt other memory locations.

Part B

This part of the lab is worth 60 points:

• 10 points for your description of the computations required for the iaddq instruction.

• 10 points for your description of the computations required for the jm instruction.

• 10 points for passing the benchmark regression tests in y86-code, to verify that your simulator still correctly executes the benchmark suite.

• 15 points for passing the regression tests in ptest for iaddq.

• 15 points for passing the regression tests in ptest for jm.

Part C

This part of the Lab is worth 100 points: You will not receive any credit if either your code for ncopy.ys or your modified simulator fails any of the tests described earlier.

• 20 points each for your descriptions in the headers of ncopy.ys and pipe-full.hcl and the quality of these implementations.

• 60 points for performance. To receive credit here, your solution must be correct, as defined earlier. That is, ncopy runs correctly with YIS, and pipe-full.hcl passes all tests in y86-code and ptest.

We will express the performance of your function in units of cycles per element (CPE). That is, if the simulated code requires C cycles to copy a block of N elements, then the CPE is C/N. The PIPE simulator displays the total number of cycles required to complete the program. The baseline version of the ncopy function running on the standard PIPE simulator with a large 63-element array requires 897 cycles to copy 63 elements, for a CPE of 897/63 = 14.24.

Since some cycles are used to set up the call to ncopy and to set up the loop within ncopy, you will find that you will get different values of the CPE for different block lengths (generally the CPE will drop as N increases). We will therefore evaluate the performance of your function by computing the average of the CPEs for blocks ranging from 1 to 64 elements. You can use the Perl script benchmark.pl in the pipe directory to run simulations of your ncopy.ys code over a range of block lengths and compute the average CPE. Simply run the command

unix&gt; ./benchmark.pl

to see what happens. For example, the baseline version of the ncopy function has CPE values ranging between 29.00 and 14.27, with an average of 15.18. Note that this Perl script does not check for the correctness of the answer. Use the script correctness.pl for this.

You should be able to achieve an average CPE of less than 9.00. Our best version averages 5.80. If your average CPE is c, then your score S for this portion of the lab will be:

S = 

0,



20 · (10.5 − c),

 60, c &gt; 10.5

7.50 ≤ c ≤ 10.50 c &lt; 7.50

By default, benchmark.pl and correctness.pl compile and test ncopy.ys. Use the -f argument to specify a different file name. The -h flag gives a complete list of the command line arguments.

8 Handin Instructions

• You will be handing in three sets of files:

– Part A: sum.ys, rsum.ys, and bubble.ys.

– Part B: seq-full.hcl.

– Part C: ncopy.ys and pipe-full.hcl.

• Make sure you have included your name and ID in a comment at the top of each of your handin files.

• To create your handin files for the lab, go to your archlab-handout directory and type: unix&gt; make handin USER=userID

where userID is your unique userID. For example, if your userID is studID@stu.pku.edu.cn, then to handin the files you would type: unix&gt; make handin USER=studID@stu.pku.edu.cn

• To handin your work, select your handin tarball userID.tar in archlab webpage.

9 Hints

• By design, both sdriver.yo and ldriver.yo are small enough to debug with in GUI mode. We find it easiest to debug in GUI mode, and suggest that you use it.

• If you running in GUI mode on a Unix server, make sure that you have initialized the DISPLAY environment variable:

unix&gt; setenv DISPLAY myhost.edu:0

• With some X servers, the “Program Code” window begins life as a closed icon when you run psim or ssim in GUI mode. Simply click on the icon to expand the window.

• With some Microsoft Windows-based X servers, the “Memory Contents” window will not automatically resize itself. You’ll need to resize the window by hand.

• The psim and ssim simulators terminate with a segmentation fault if you ask them to execute a file that is not a valid Y86-64 object file.
