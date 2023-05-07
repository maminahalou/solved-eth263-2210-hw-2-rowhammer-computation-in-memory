Download Link: https://assignmentchef.com/product/solved-eth263-2210-hw-2-rowhammer-computation-in-memory
<br>
<h1>1. Critical Paper Reviews</h1>

Please read the guidelines for reviewing papers and check the sample reviews. We also assign you a required reading for this homework. You may access them by <em>simply clicking on the QR codes below or scanning them</em>. We will give out extra credit that is worth 0.5% of your total grade for each good review. If you submit 5 or 6 paper reviews, you will receive 250 or 500 BONUS points on top of 1000 points you may get from paper reviews, respectively (i.e., each additional submission is worth 250 BONUS points).

Guidelines                                     Sample reviews                                 Required Reading

Write an approximately one-page critical review for the following required reading (i.e., Paper #1) and <em>at least </em>3 of the remaining 5 papers (i.e., papers from #2 to #6). A review with bullet point style is more appreciated. Try not to use very long sentences and paragraphs. Keep your writing and sentences simple. Make your points bullet by bullet, as much as possible.

<ol>

 <li>(REQUIRED) Ghose et al., “<em>Processing-in-Memory: A Workload-Driven Perspective</em>,” in IBM Journal of Research &amp; Development, 2019. <a href="https://people.inf.ethz.ch/omutlu/pub/processing-in-memory_workload-driven-perspective_IBMjrd19.pdf">https://people.inf.ethz.ch/omutlu/pub/processing-in-memo </a><a href="https://people.inf.ethz.ch/omutlu/pub/processing-in-memory_workload-driven-perspective_IBMjrd19.pdf">ry_workload-driven-perspective_IBMjrd19.pdf</a></li>

 <li>Frigo et al., “<em>TRRespass: Exploiting the Many Sides of Target Row Refresh</em>,” in Proceedings of the 41st IEEE Symposium on Security and Privacy, 2020. <a href="https://people.inf.ethz.ch/omutlu/pub/rowhammer-TRRespass_ieee_security_privacy20.pdf">https://people.inf.ethz.ch/omutlu/pub/rowham </a><a href="https://people.inf.ethz.ch/omutlu/pub/rowhammer-TRRespass_ieee_security_privacy20.pdf">mer-TRRespass_ieee_security_privacy20.pdf</a></li>

 <li>Seshadri et al., “<em>RowClone: Fast and Energy-Efficient In-DRAM Bulk Data Copy and Initialization</em>,” in Proceedings of the 46th Annual IEEE/ACM International Symposium on Microarchitecture, 2013. <a href="https://people.inf.ethz.ch/omutlu/pub/rowclone_micro13.pdf">https://people.inf.ethz.ch/omutlu/pub/rowclone_micro13.pdf</a></li>

 <li>Seshadri et al., “<em>Ambit: In-Memory Accelerator for Bulk Bitwise Operations Using Commodity DRAM Technology</em>,” in Proceedings of the 50th Annual IEEE/ACM International Symposium on Microarchitecture, 2017. <a href="https://people.inf.ethz.ch/omutlu/pub/ambit-bulk-bitwise-dram_micro17.pdf">https://people.inf.ethz.ch/omutlu/pub/ambit-bulk-bitwise-dram_micro17.pdf</a></li>

 <li>Ahn et al., “<em>A Scalable Processing-In-Memory Accelerator for Parallel Graph Processing</em>,” in Proceedings of the 42nd Annual International Symposium on Computer Architecture, 2015. <a href="https://people.inf.ethz.ch/omutlu/pub/tesseract-pim-architecture-for-graph-processing_isca15.pdf">https://people.inf.e </a><a href="https://people.inf.ethz.ch/omutlu/pub/tesseract-pim-architecture-for-graph-processing_isca15.pdf">ch/omutlu/pub/tesseract-pim-architecture-for-graph-processing_isca15.pdf</a></li>

 <li>Boroumand et al., “<em>Google Workloads for Consumer Devices: Mitigating Data Movement Bottlenecks</em>,” in Proceedings of the 23rd International Conference on Architectural Support for Programming Languages and Operating Systems, 2018. <a href="https://people.inf.ethz.ch/omutlu/pub/Google-consumer-workloads-data-movement-and-PIM_asplos18.pdf">https://people.inf.ethz.ch/omutlu/pub/Google-consumer-worklo </a><a href="https://people.inf.ethz.ch/omutlu/pub/Google-consumer-workloads-data-movement-and-PIM_asplos18.pdf">ads-data-movement-and-PIM_asplos18.pdf</a></li>

 <li>RowHammer [200 points]</li>

</ol>

<h2>2.1. RowHammer Properties</h2>

Determine whether each of following statements is true or false.

<ul>

 <li>Cells in a DRAM with a smaller technology node are more vulnerable to RowHammer.

  <ol>

   <li>True False</li>

  </ol></li>

 <li>Cells which have shorter retention times are especially vulnerable to RowHammer.

  <ol>

   <li>True False</li>

  </ol></li>

 <li>The vulnerability of cells in a victim row to RowHammer depends on the data stored in the victim row.

  <ol>

   <li>True False</li>

  </ol></li>

 <li>The vulnerability of cells in a victim row to RowHammer depends on the data stored in the aggressor row.

  <ol>

   <li>True False</li>

  </ol></li>

 <li>RowHammer-induced errors are mostly repeatable.

  <ol>

   <li>True False</li>

  </ol></li>

</ul>

<h2>2.2. RowHammer Mitigations</h2>

One research group rigorously investigated the relationship between the DRAM refresh rate and RowHammerinduced errors using real DRAM modules from three major memory manufacturers: A, B, and C. The following figure shows the characterization results of the <em>most RowHammer-vulnerable </em>modules of each DRAM manufacturer A, B, and C (<em>A</em><sub>23</sub>, <em>B</em><sub>11</sub>, and <em>C</em><sub>19</sub>, respectively). As shown in the figure below, we can achieve an <em>effectively-zero </em>probability of RowHammer-induced errors when we reduce the refresh interval to 8 ms. This is because the probability of RowHammer-induced errors becomes less than that of a random DRAM circuit fault.

As a leading computer architect of a company, you are asked to design an efficient RowHammer mitigation technique based on the characterization results.

<ul>

 <li>A junior engineer suggests to simply reduce the refresh interval from the default 64 ms to 8 ms. How will the bank utilization <em>U </em>and the DRAM energy consumption <em>E </em>of all refresh operations be changed over the current system?</li>

 <li>A DRAM manufacturer releases a higher capacity version of the same DRAM module (4x the total capacity). After rigorously reverse-engineering, you determine that the manufacturer doubles both the (1) number of rows in a bank, and (2) number of banks in a module without changing any other aspects (e.g., row size, bus rate, and timing parameters). Your company considers upgrading the current system with the higher-capacity DRAM module and asks your opinion. In the current system, the bank utilization of refresh operations is 0.05 when the refresh interval is 64 ms. Would reducing the refresh interval to 8 ms still be viable (in terms of RowHammer protection capability and performance overheads) in a module with 2x the number of rows per bank and 2x the number of banks per module? How about in a module with 4x the number of rows per bank and 4x the number of banks per module?</li>

 <li>Due to significant overheads of reducing the refresh interval, your team decides to find other RowHammer mitigation techniques with lower overhead. The junior engineer proposes a counter-based approach as follows:</li>

</ul>

In this approach, the memory controller maintains a counter for each row <em>R</em>, which increments when an adjacent row is activated, and resets when Row <em>R </em>is activated or refreshed. If the value of a row <em>R</em>’s counter exceeds a threshold value, <em>T</em>, the memory controller activates row <em>R </em>and resets its respective counter.

Here are some specifications on the current memory system:

<ul>

 <li>Interface: DDR3-1333</li>

 <li><em>CL </em>= 7</li>

 <li><em>tRCD </em>= 13<em>.</em>5 ns</li>

 <li><em>tRAS </em>= 35 ns</li>

 <li><em>tWR </em>= 15 ns</li>

 <li><em>tRP </em>= 13<em>.</em>5 ns</li>

 <li><em>tRFC </em>= 120 ns</li>

 <li>Configuration: Per-channel memory controller deals with 2 ranks, each of which has 8 banks. The number of rows per bank is 2<sup>15</sup>. Each row in one bank is 8 KiB.</li>

</ul>

Are the given specifications enough to implement the proposed approach? If no, list the specifications additionally required.

<ul>

 <li>Suppose that all the necessary specifications for implementing the proposed approach are known. Calculate the maximum value of <em>T </em>that can guarantee the same level of security against RowHammer attacks over when adopting 8-ms refresh interval?</li>

 <li>Calculate the number of bits required for counters in each memory controller. How does it change when the number of rows per bank and the number of banks per chip are doubled?</li>

</ul>

(g) You recall <em>PARA (Probabilistic Adjacent Row Activation) </em>which is proposed in the first RowHammer paper. Here is how a PARA-enabled memory controller works (for more details, see Section 8.2 in the paper<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>):

Whenever a row is closed, the controller flips a biased coin with a probability <em>p </em>of turning up heads, where <em>p &lt;&lt; </em>1. If the coin turns up heads, the controller opens one of its adjacent rows where either of the two adjacent rows are chosen with equal probability (<em>p/</em>2). Due to its probabilistic nature, PARA does not guarantee that the adjacent will always be refreshed in time. Hence, PARA cannot prevent disturbance errors with absolute certainty. However, its parameter <em>p </em>can be set so that disturbance errors occur at an extremely low probability — many orders of magnitude lower than the failure rates of other system components (e.g., more than 1% of hard-disk drives fail every year.)

Suppose that the probability of experiencing an error for PARA in 64 ms is 1<em>.</em>9×10<sup>−22 </sup>when <em>p </em>= 0<em>.</em>001 at the <em>worst operating conditions</em>. How can we estimate the probability of experiencing an error in one year based on that value? Show your work. (If you just put an answer, you will get no points for this problem.)

<h1>3. Processing in Memory: Ambit</h1>

<h2>3.1. In-DRAM Bitmap Indices I</h2>

Recall that in class we discussed Ambit, which is a DRAM design that can greatly accelerate <em>bulk bitwise operations </em>by providing the ability to perform bitwise AND/OR of two rows in a subarray.

One real-world application that can benefit from Ambit’s in-DRAM bulk bitwise operations is the database <em>bitmap index</em>, as we also discussed in the lecture. By using bitmap indices, we want to run the following query on a database that keeps track of user actions: “How many unique users were active every week for the past <em>w </em>weeks?” Every week, each user is represented by a single bit. If the user was active a given week, the corresponding bit is set to 1. The total number of users is <em>u</em>.

We assume the bits corresponding to one week are all in the same row. If <em>u </em>is greater than the total number of bits in one row (the row size is 8 kilobytes), more rows in different subarrays are used for the same week. We assume that all weeks corresponding to the users in one subarray fit in that subarray. We would like to compare two possible implementations of the database query:

<ul>

 <li><em>CPU-based implementation</em>: This implementation reads the bits of all <em>u </em>users for the <em>w </em> For each user, it ands the bits corresponding to the past <em>w </em>weeks. Then, it performs a bit-count operation to compute the final result.</li>

</ul>

Since this operation is very memory-bound, we simplify the estimation of the execution time as the time needed to read all bits for the <em>u </em>users in the last <em>w </em>weeks. The memory bandwidth that the CPU can exploit is <em>X </em>bytes/s.

<ul>

 <li><em>Ambit-based implementation</em>: This implementation takes advantage of bulk and operations of Ambit. In each subarray, we reserve one <em>Accumulation </em>row and one <em>Operand </em>row (besides the control rows that are needed for the regular operation of Ambit). Initially, all bits in the <em>Accumulation </em>row are set to 1. Any row can be moved to the <em>Operand </em>row by using RowClone (recall that RowClone is a mechanism that enables very fast copying of a row to another row in the same subarray). <em>t<sub>rc </sub></em>and <em>t<sub>and </sub></em>are the latencies (in seconds) of RowClone’s copy and Ambit’s and respectively.</li>

</ul>

Since Ambit does <em>not </em>support bit-count operations inside DRAM, the final bit-count is still executed on the CPU. We consider that the execution time of the bit-count operation is negligible compared to the time needed to read all bits from the <em>Accumulation </em>rows by the CPU.

<ul>

 <li>What is the total number of DRAM rows that are occupied by <em>u </em>users and <em>w </em>weeks?</li>

 <li>What is the throughput in users/second of the Ambit-based implementation?</li>

</ul>

(d) What is the maximum <em>w </em>for the CPU implementation to be faster than the Ambit-based implementation? Assume <em>u </em>is a multiple of the row size.

<h2>3.2. In-DRAM Bitmap Indices II</h2>

You have been hired to accelerate ETH’s student database. After profiling the system for a while, you found out that one of the most executed queries is to <em>“select the hometown of the students that are from Switzerland and speak German”</em>. The attributes <em>hometown</em>, <em>country</em>, and <em>language </em>are encoded using a fourbyte binary representation. The database has 32768 (2<sup>15</sup>) entries, and each attribute is stored contiguously in memory. The database management system executes the following query:

<table width="633">

 <tbody>

  <tr>

   <td width="633">bool position_hometown[entries]; for(int i = 0; i &lt; entries; i++){ if(students.country[i] == “Switzerland” &amp;&amp; students.language[i] == “German”){ position_hometown[i] = true;} else{ position_hometown[i] = false;}}</td>

  </tr>

 </tbody>

</table>

1

2

3

4

5

6

7

8

9

<ul>

 <li>You are running the above code on a single-core processor. Assume that:

  <ul>

   <li>Your processor has an 8 MiB direct-mapped cache, with a cache line of 64 bytes.</li>

   <li>A hit in this cache takes one cycle and a miss takes 100 cycles for both load and store operations.</li>

   <li>All load/store operations are serialized, i.e., the latency of multiple memory requests cannot be overlapped.</li>

   <li>The starting addresses of <em>country</em>, <em>students.language</em>, and <em>position_hometown </em>are 0x05000000, 0x06000000, 0x07000000, respectively.</li>

   <li>The execution time of a non-memory instruction is zero (i.e., we ignore its execution time).</li>

  </ul></li>

</ul>

How many cycles are required to run the query? Show your work.

<ul>

 <li>Recall that in class we discussed Ambit, which is a DRAM design that can greatly accelerate <em>bulk bitwise operations </em>by providing the ability to perform bitwise AND/OR/XOR of two rows in a subarray. Ambit works by issuing back-to-back ACTIVATE (A) and PRECHARGE (P) operations. For example, to compute AND, OR, and XOR operations, Ambit issues the sequence of commands described in the table below (e.g., <em>AAP</em>(<em>X,Y </em>) represents double row activation of rows <em>X </em>and <em>Y </em>followed by a precharge operation, <em>AAAP</em>(<em>X,Y,Z</em>) represents triple row activation of rows <em>X</em>, <em>Y </em>, and <em>Z </em>followed by a precharge operation). In those instructions, Ambit copies the source rows <em>D<sub>i </sub></em>and <em>D<sub>j </sub></em>to auxiliary rows (<em>B<sub>i</sub></em>). Control rows <em>C<sub>i </sub></em>dictate which operation (AND/OR) Ambit executes. The DRAM rows with dual-contact cells (i.e., rows <em>DCC<sub>i</sub></em>) are used to perform the bitwise NOT operation on the data stored in the row. Basically, copying a source row to <em>DCC<sub>i </sub></em>flips all bits in the source row and stores the result in both the source row and <em>DCC<sub>i</sub></em>. Assume that:

  <ul>

   <li>The DRAM row size is 8 Kbytes.</li>

   <li>An ACTIVATE command takes 50 cycles to execute.</li>

   <li>A PRECHARGE command takes 20 cycles to execute.</li>

   <li>DRAM has a single memory bank.</li>

   <li>The syntax of an Ambit operation is: <em>bbop_</em>[and/or/xor] <em>destination, source_1, source_2</em>.</li>

   <li>Addresses 0x08000000 and 0x09000000 are used to store partial results.</li>

   <li>The rows at addresses 0x0A000000 and 0x0B00000 store the codes for <em>“Switzerland” </em>and <em>“German”</em>, respectively, in each four bytes throughout the entire row.</li>

  </ul></li>

</ul>

<table width="407">

 <tbody>

  <tr>

   <td width="134"><em>D<sub>k </sub></em>= <em>D<sub>i </sub></em>AND <em>D<sub>j</sub></em></td>

   <td width="134"><em>D<sub>k </sub></em>= <em>D<sub>i </sub></em>OR <em>D<sub>j</sub></em></td>

   <td width="139"><em>D<sub>k </sub></em>= <em>D<sub>i </sub></em>XOR <em>D<sub>j</sub></em></td>

  </tr>

  <tr>

   <td width="134">AAP (<em>D<sub>i</sub></em>, <em>B</em><sub>0</sub>)AAP (<em>D<sub>j</sub></em>, <em>B</em><sub>1</sub>)AAP (<em>C</em><sub>0</sub>, <em>B</em><sub>2</sub>)AAAP (<em>B</em><sub>0</sub>, <em>B</em><sub>1</sub>, <em>B</em><sub>2</sub>)AAP <em>B</em><sub>0</sub>, <em>D<sub>k</sub></em></td>

   <td width="134">AAP (<em>D<sub>i</sub></em>, <em>B</em><sub>0</sub>)AAP (<em>D<sub>j</sub></em>, <em>B</em><sub>1</sub>) AAP (<em>C</em><sub>1</sub>, <em>B</em><sub>2</sub>)AAAP (<em>B</em><sub>0</sub>, <em>B</em><sub>1</sub>, <em>B</em><sub>2</sub>) AAP <em>B</em><sub>0</sub>, <em>D<sub>k</sub></em></td>

   <td width="139">AAP (<em>D<sub>i</sub></em>, <em>B</em><sub>0</sub>)AAP (<em>D<sub>j</sub></em>, <em>B</em><sub>1</sub>)AAP (<em>D<sub>i</sub></em>, <em>DCC</em><sub>0</sub>)AAP (<em>D<sub>j</sub></em>, <em>DCC</em><sub>1</sub>)AAP (<em>C</em><sub>0</sub>, <em>B</em><sub>2</sub>)AAAP (<em>B</em><sub>0</sub>, <em>DCC</em><sub>1</sub>, <em>B</em><sub>2</sub>)AAP (<em>C</em><sub>0</sub>, <em>B</em><sub>2</sub>)AAAP (<em>B</em><sub>1</sub>, <em>DCC</em><sub>0</sub>, <em>B</em><sub>2</sub>)AAP (<em>C</em><sub>1</sub>, <em>B</em><sub>2</sub>)AAAP (<em>B</em><sub>0</sub>, <em>B</em><sub>1</sub>, <em>B</em><sub>2</sub>)AAP (<em>B</em><sub>0</sub>, <em>D<sub>k</sub></em>)</td>

  </tr>

 </tbody>

</table>

<ol>

 <li>i) The following code aims to execute the query <em>“select the hometown of the students that are from Switzerland and speak German” </em>in terms of Boolean operations to make use of Ambit. Fill in the blank boxes such that the algorithm produces the correct result. Show your work.</li>

</ol>

1 for(int i = 0; i &lt;                                           ; i++){

2

<table width="570">

 <tbody>

  <tr>

   <td rowspan="2" width="57">bbop_bbop_bbop_}</td>

   <td width="65"> </td>

   <td rowspan="2" width="448">0x08000000, 0x05000000 + i*8192, 0x0A000000;0x09000000, 0x06000000 + i*8192, 0x0B000000;0x07000000 + i*8192, 0x08000000, 0x09000000;</td>

  </tr>

  <tr>

   <td width="65"></td>

  </tr>

 </tbody>

</table>

3

4

5

6

7

8

<ol>

 <li>ii) How much speedup does Ambit provide over the baseline processor when executing the same query? Show your work.</li>

</ol>

<h1>4. In-DRAM Bit Serial Computation</h1>

Recall that in class, we discussed Ambit, which is a DRAM design that can greatly accelerate bulk bitwise operations by providing the ability to perform bitwise AND/OR of two rows in a subarray and NOT of one row. Since Ambit is logically complete, it is possible to implement any other logic gate (e.g., XOR). To be able to implement arithmetic operations, bit shifting is also necessary. There is no way of shifting bits in DRAM with a conventional layout, but it can be done with a bit-serial layout, as Figure 1 shows. With such a layout, it is possible to perform bit-serial arithmetic computations in Ambit.

<strong>Figure 1. In-DRAM bit-serial layout for array </strong>A<strong>, which contains five 4-bit elements. DRAM cells in the same bitline contain the bits of an array element: </strong>A[i]_j <strong>represents bit </strong>j <strong>of element </strong>i<strong>.</strong>

We want to evaluate the potential performance benefits of using Ambit for arithmetic computations by implementing a simple workload, the element-wise addition of two arrays. Listing 1 shows a sequential code for the addition of two input arrays A and B into output array C.

<strong>Listing 1. Sequential CPU implementation of element-wise addition of arrays </strong>A <strong>and </strong>B<strong>.</strong>

<table width="633">

 <tbody>

  <tr>

   <td width="633">for(int i = 0; i &lt; num_elements; i++){C[i] = A[i] + B[i];}</td>

  </tr>

 </tbody>

</table>

1

2

3

We compare two possible implementations of the element-wise addition of two arrays: a CPU-based and an Ambit-based implementation. We make two assumptions. First, we use the most favorable layout for each implementation (i.e., conventional layout for CPU, and bit-serial layout for Ambit). Second, both implementations can operate on array elements of any size (i.e., bits/element):

<ul>

 <li><em>CPU-based implementation</em>: This implementation reads elements of A and B from memory, adds them, and writes the resulting elements of C into memory.</li>

</ul>

Since the computation is simple and regular, we can use a simple analytical performance model for the

execution time of the CPU-based implementation: , where <em>K </em>represents the cost per arithmetic operation and <em>M </em>is the DRAM bandwidth. (Note: <em>num_operations </em>should include only the operations for the array addition.)

<ul>

 <li><em>Ambit-based implementation</em>: This implementation assumes a bit serial layout for arrays A, B, and C. It performs additions in a bit serial manner, which only requires XOR, AND, and OR operations, as you can see in the 1-bit full adder in Figure 2.</li>

</ul>

<strong>Figure 2. 1-bit full adder.</strong>

Ambit implements these operations by issuing back-to-back ACTIVATE (A) and PRECHARGE (P) operations. For example, to compute AND, OR, and XOR operations, Ambit issues the sequence of commands described in Table 1, where <em>AAP</em>(<em>X,Y </em>) represents double row activation of rows X and Y followed by a precharge operation, and <em>AAAP</em>(<em>X,Y,Z</em>) represents triple row activation of rows X, Y, and Z followed by a precharge operation.

In those instructions, Ambit copies the source rows <em>D<sub>i </sub></em>and <em>D<sub>j </sub></em>to auxiliary rows (<em>B<sub>i</sub></em>). Control rows <em>C<sub>i </sub></em>dictate which operation (AND/OR) Ambit executes. The DRAM rows with dual-contact cells (i.e., rows <em>DCC<sub>i</sub></em>) are used to perform the bitwise NOT operation on the data stored in the row. Basically, the NOT operation copies a source row to <em>DCC<sub>i</sub></em>, flips all bits of the row, and stores the result in both the source row and <em>DCC<sub>i</sub></em>. Assume that:

<ul>

 <li>The DRAM row size is 8 Kbytes.</li>

 <li>An ACTIVATE command takes 20ns to execute.</li>

 <li>A PRECHARGE command takes 10ns to execute. – DRAM has a single memory bank.</li>

 <li>The syntax of an Ambit operation is: <em>bbop_</em>[and/or/xor] <em>destination, source_1, source_2</em>.</li>

 <li>The rows at addresses 0x00700000, 0x00800000, and 0x00900000 are used to store partial results. Initially, they contain all zeroes.</li>

 <li>The rows at addresses 0x00A00000, 0x00B00000, and 0x00C00000 store arrays A, B, and C, respectively.</li>

 <li>These are all byte addresses. All these rows belong to the same DRAM subarray.</li>

</ul>

<strong>Table 1. Sequences of ACTIVATE and PRECHARGE operations for the execution of Ambit’s AND, OR, and XOR.</strong>

<table width="407">

 <tbody>

  <tr>

   <td width="134"><em>D<sub>k </sub></em>= <em>D<sub>i </sub></em>AND <em>D<sub>j</sub></em></td>

   <td width="134"><em>D<sub>k </sub></em>= <em>D<sub>i </sub></em>OR <em>D<sub>j</sub></em></td>

   <td width="139"><em>D<sub>k </sub></em>= <em>D<sub>i </sub></em>XOR <em>D<sub>j</sub></em></td>

  </tr>

  <tr>

   <td width="134">AAP (<em>D<sub>i</sub></em>, <em>B</em><sub>0</sub>)AAP (<em>D<sub>j</sub></em>, <em>B</em><sub>1</sub>)AAP (<em>C</em><sub>0</sub>, <em>B</em><sub>2</sub>)AAAP (<em>B</em><sub>0</sub>, <em>B</em><sub>1</sub>, <em>B</em><sub>2</sub>)AAP <em>B</em><sub>0</sub>, <em>D<sub>k</sub></em></td>

   <td width="134">AAP (<em>D<sub>i</sub></em>, <em>B</em><sub>0</sub>)AAP (<em>D<sub>j</sub></em>, <em>B</em><sub>1</sub>) AAP (<em>C</em><sub>1</sub>, <em>B</em><sub>2</sub>)AAAP (<em>B</em><sub>0</sub>, <em>B</em><sub>1</sub>, <em>B</em><sub>2</sub>) AAP <em>B</em><sub>0</sub>, <em>D<sub>k</sub></em></td>

   <td width="139">AAP (<em>D<sub>i</sub></em>, <em>B</em><sub>0</sub>)AAP (<em>D<sub>j</sub></em>, <em>B</em><sub>1</sub>)AAP (<em>D<sub>i</sub></em>, <em>DCC</em><sub>0</sub>)AAP (<em>D<sub>j</sub></em>, <em>DCC</em><sub>1</sub>)AAP (<em>C</em><sub>0</sub>, <em>B</em><sub>2</sub>)AAAP (<em>B</em><sub>0</sub>, <em>DCC</em><sub>1</sub>, <em>B</em><sub>2</sub>)AAP (<em>C</em><sub>0</sub>, <em>B</em><sub>2</sub>)AAAP (<em>B</em><sub>1</sub>, <em>DCC</em><sub>0</sub>, <em>B</em><sub>2</sub>) AAP (<em>C</em><sub>1</sub>, <em>B</em><sub>2</sub>)AAAP (<em>B</em><sub>0</sub>, <em>B</em><sub>1</sub>, <em>B</em><sub>2</sub>)AAP (<em>B</em><sub>0</sub>, <em>D<sub>k</sub></em>)</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>For the CPU-based implementation, you want to obtain <em>K </em>and <em>M</em>. To this end, you run two experiments. In the first experiment, you run your CPU code for the element-wise array addition for 65,536 4-bit elements and measure <em>t<sub>cpu </sub></em>= 100 us. In the second experiment, you run the STREAM-Copy benchmark for 102,400 4-bit elements and measure <em>t<sub>cpu </sub></em>= 10 us. The STREAM-Copy benchmark simply copies the contents of one input array A to an output array B. What are the values of <em>K </em>and</li>

</ul>

<em>M</em>?

<ul>

 <li>Write the code for the Ambit-based implementation of the element-wise addition of arrays A and B. The resulting array is C.</li>

 <li>Compute the maximum throughput (in arithmetic operations per second, OPS) of the Ambit-based implementation as a function of the element size (i.e., bits/element).</li>

 <li>Determine the element size (in bits) for which the CPU-based implementation is faster than the Ambitbased implementation (Note: Use the same array size as in the previous part).</li>

</ul>

<h1>5. Caching vs. Processing-in-Memory</h1>

We are given the following piece of code that makes accesses to integer arrays A and B. The size of each element in both A and B is 4 bytes. The base address of array A is 0x00001000, and the base address of B is 0x00008000.

movi R1, #0x1000 // Store the base address of A in R1 movi R2, #0x8000 // Store the base address of B in R2 movi R3, #0

Outer_Loop: movi R4, #0 movi R7, #0 Inner_Loop:

add R5, R3, R4 // R5 = R3 + R4

// load 4 bytes from memory address R1+R5 ld R5, [R1, R5] // R5 = Memory[R1 + R5], ld R6, [R2, R4] // R6 = Memory[R2 + R4] mul R5, R5, R6 // R5 = R5 * R6 add R7, R7, R5 // R7 += R5

inc R4                          // R4


bne R4, #2, Inner_Loop // If R4 != 2, jump to Inner_Loop

//store the data of R7 in memory address R1+R3 st [R1, R3], R7 // Memory[R1 + R3] = R7,

inc R3                                   // R3


bne R3, #16, Outer_Loop // If R3 != 16, jump to Outer_Loop

You are running the above code on a single-core processor. For now, assume that the processor <em>does not </em>have caches. Therefore, all load/store instructions access the main memory, which has a fixed 50cycle latency, for both read and write operations. Assume that all load/store operations are serialized, i.e., the latency of multiple memory requests <em>cannot </em>be overlapped. Also assume that the execution time of a non-memory-access instruction is zero (i.e., we ignore its execution time).

<ul>

 <li>What is the execution time of the above piece of code in cycles? Show your work.</li>

 <li>Assume that a 128-byte private cache is added to the processor core in the next-generation processor. The cache block size is 8-byte. The cache is direct-mapped. On a hit, the cache services both read and write requests in 5 cycles. On a miss, the main memory is accessed and the access fills an 8-byte cache line in 50 cycles. Assuming that the cache is initially empty, what is the new execution time on this processor with the described cache? Show your work.</li>

 <li>You are not satisfied with the performance after implementing the described cache. To do better, you consider utilizing a processing unit that is available <em>close to the main memory</em>. This processing unit can directly interface to the main memory with a <em>10-cycle </em>latency, for both read and write operations. How many cycles does it take to execute the same program using the in-memory processing units? Show your work. (Assume that the in-memory processing unit does not have a cache, and the memory accesses are serialized like in the processor core. The latency of the non-memory-access operations is ignored.)</li>

 <li>You friend now suggests that, by changing the cache capacity of the single-core processor (in part (b)), she could provide as good performance as the system that utilizes the memory processing unit (in part (c)). Is she correct? What is the minimum capacity required for the cache of the single-core processor to match the performance of the program running on the memory processing unit? Show your work.</li>

 <li>What other changes could be made to the cache design to improve the performance of the single-core processor on this program?</li>

</ul>

<a href="#_ftnref1" name="_ftn1">[1]</a> Yoongu Kim, Ross Daly, Jeremie Kim, Chris Fallin, Ji Hye Lee, Donghyuk Lee, Chris Wilkerson, Konrad Lai, and Onur Mutlu, “Flipping Bits in Memory without Accessing Them: an Experimental Study of DRAM Disturbance Errors,” in Proceedings of the 41st Annual International Sympoisum on Computer Architecture, 2014. <a href="https://people.inf.ethz.ch/omutlu/pub/dram-row-hammer_isca14.pdf">https://people.inf.ethz.ch/omutl </a><a href="https://people.inf.ethz.ch/omutlu/pub/dram-row-hammer_isca14.pdf">u/pub/dram-row-hammer_isca14.pdf</a>