Download Link: https://assignmentchef.com/product/solved-csc139-scheduler-simulator
<br>
<strong>Abstract: </strong>Compute the performance data for the <strong>schedulers of three types of Operating Systems</strong>. Do not get scared! Only the timing for each scheduler is of interest. You can compute these timing data by hand or by actually implementing a simulator. Either solution is feasible and permitted. The simulator measures key performance data, such as <em>throughput, wait time</em>, and<em> turn-around time</em>. You may also manually compute these numbers without having to run them in a simulation environment.




If you chose to “manually” compute the data, i.e. without implementing a SW simulator, the amount of “generated performance data” is at times allowed to be less detailed than what is suggested here.




<strong>One OS</strong> is a strict <em>batch system</em> with a<em> non-preemptive First Come First Serve (FCFS)</em> scheduler. The <strong>second OS</strong> uses a <em>non-preemptive, high-priority first</em> <em>(HPF)</em> scheduler, while the <strong>third OS</strong> uses <em>a preemptive round robin (RR) </em>scheduler with a variable time-quantum with varying context switch <em>overhead</em>. Design meaningful input data, run them through all schedulers, generate output data, and interpret and discuss the results. To start your simulations, use the sample data from this HW assignment. In addition, provide 2 additional, meaningful input scenarios, and generate their execution schedules.




<strong>Detail</strong>: Your HomeWork consists of the following parts with equal weight each:

Compute performance data for the scheduler of a non-preemptive FCFS batch system

Ditto for a non-preemptive HPF batch system, and

Ditto for a preemptive RR; vary time quantum and overhead.

Invent meaningful input data; run them through your schedulers to produce output    Discuss very briefly the generated data. Hand in discussions in printed form




<strong>Input:</strong> Input to the schedulers is a <strong><em>list of processes</em></strong>, for which you happen to know the execution time in milliseconds. For your program input, each process is represented by a triple of decimal numbers <strong><em>id, time, priority</em></strong>. These multiple processes are scheduled and compete for the CPU resource. Here <strong><em>id</em></strong> is the <em>name</em> of a process; <strong><em>time</em></strong> is the time in milliseconds that process<strong><em> id</em></strong> needs to run to completion, and <strong><em>priority</em></strong> is the priority of process <strong><em>id</em></strong>. A plausible input sample for two processes with process id 1 and process id 4 is:




id      time   priority

<strong>1          2          3 </strong>       <strong>4             50       6 </strong>




Depending on the scheduler, the priority may be ignored. The meaning of triples is as follows:




1   2 3           process 1 uses 2 milliseconds to run, has priority 3, with 0 being highest

4 50 6           process 4 uses 50 milliseconds, has priority 6, with priority 0 being the highest




Use the definitions below to compute for each process <em>Throughput, Wait Time</em>, and <em>Turnaround Time</em>. Compute these for each of the 3 schedulers; also compute the average for all processes.




For the preemptive RR scheduler, vary the time quantum <strong>q</strong> from 1 to 5 milliseconds (ms).

Also, for each <strong>q</strong> selected, vary the overhead <strong>o</strong> of a context switch from 0 ms up to <strong>q</strong> itself. There is no need to vary the <strong>o</strong> beyond <strong>q</strong>. When a process scheduled by the RR system has received all time needed to completion, do not add a final <strong>o</strong> unit in the computation of the total time for that process. Also the first time around, act as if the initial schedule overhead <strong>o </strong>is 0. Use the sample outputs below as a guide for the detail you should generate for this HW.




<strong> </strong>

<strong>Definitions: </strong>

<table width="604">

 <tbody>

  <tr>

   <td width="192"></td>

   <td width="412"></td>

  </tr>

  <tr>

   <td width="192"><strong>Throughput:</strong></td>

   <td width="412">Number of <em>jobs</em> (processes) completed per time unit</td>

  </tr>

  <tr>

   <td width="192"><strong>Wait Time:</strong></td>

   <td width="412">The total time a process is in <em>Ready Queue </em></td>

  </tr>

  <tr>

   <td width="192"><strong>Average Wait Time:</strong></td>

   <td width="412">Average Wait Time of <em>n</em> processes is: total wait time by <em>n</em></td>

  </tr>

  <tr>

   <td width="192"><strong>Turn-around Time:</strong> </td>

   <td width="412">span of time from <em>moment of submission </em>to<em> completion time</em></td>

  </tr>

 </tbody>

</table>

<strong><em>Example 1: </em></strong>




Enter triples: process id, time in ms, and priority:

For example:

1 12 0

3  9 1

2 99 9

process 1 needs 12 ms and has priority 0, very high, process 3 needs  9 ms and has priority 1.

and so on …

<h1>                <strong>1 2 3                         &lt;- this is user input </strong></h1>

<h2>2 1 2</h2>




Process list in FCFS order as entered:

1 2 3

<h1>2 1 2</h1>

End of list.

fcfs wait of p1 = 0 fcfs wait of p2 = 2

average wait for 2 procs = 1

fcfs turn-around time for p1 = 2

fcfs turn-around time for p2 = 3

average turn-around for 2 procs = 2.5

fcfs throughput for 2 procs = 0.666667 proc/ms

&lt;&gt;&lt;&gt; end FCFS &lt;&gt;&lt;&gt;




Process list in HPF order:

<h1>2 1 2</h1>

1 2 3

End of list.




hpf wait of p2 = 0 hpf wait of p1 = 1

average wait time for 2 procs = 0.5

hpf turn-around for p2 = 1

hpf turn-around for p1 = 3

average turn-around for 2 procs = 2

hpf throughput for 2 procs = 0.666667 proc/ms

&lt;&gt;&lt;&gt; end HPF schedule &lt;&gt;&lt;&gt;




Process list for RR in order entered:

<ul>

 <li>2 3</li>

 <li>1 2 End of list.</li>

</ul>




preemptive RR schedule, quantum = 1 overhead = 0

RR TA time for finished p2 = 2, needed: 1 ms, and: 1 time slices.

RR TA time for finished p1 = 3, needed: 2 ms, and: 2 time slices.

RR Throughput, 2 p, with q: 1, o: 0, is: 0.666667 p/ms, or 666.667 p/us Average RR TA, 2 p, with q: 1, o: 0, is: 2.5

preemptive RR schedule, quantum = 1 overhead = 1

RR TA time for finished p2 = 3, needed: 1 ms, and: 1 time slices.

RR TA time for finished p1 = 5, needed: 2 ms, and: 2 time slices.

RR Throughput, 2 p, with q: 1, o: 1, is: 0.4 p/ms, or 400 p/us

Average RR TA, 2 p, with q: 1, o: 1, is: 4




preemptive RR schedule, quantum = 2 overhead = 0

RR TA time for finished p1 = 2, needed: 2 ms, and: 1 time slices.

RR TA time for finished p2 = 3, needed: 1 ms, and: 1 time slices.

RR Throughput, 2 p, with q: 2, o: 0, is: 0.666667 p/ms, or 666.667 p/us

Average RR TA, 2 p, with q: 2, o: 0, is: 2.5

preemptive RR schedule, quantum = 2 overhead = 1

RR TA time for finished p1 = 2, needed: 2 ms, and: 1 time slices.

RR TA time for finished p2 = 4, needed: 1 ms, and: 1 time slices.

RR Throughput, 2 p, with q: 2, o: 1, is: 0.5 p/ms, or 500 p/us

Average RR TA, 2 p, with q: 2, o: 1, is: 3

preemptive RR schedule, quantum = 2 overhead = 2

RR TA time for finished p1 = 2, needed: 2 ms, and: 1 time slices.

RR TA time for finished p2 = 5, needed: 1 ms, and: 1 time slices.

RR Throughput, 2 p, with q: 2, o: 2, is: 0.4 p/ms, or 400 p/us

Average RR TA, 2 p, with q: 2, o: 2, is: 3.5




&lt;&gt;&lt;&gt; end preemptive RR schedule &lt;&gt;&lt;&gt;




<strong><em>Example 2: </em></strong>




Enter triples: process id, time in ms, and priority:

For example:

1 12 0

3  9 1 2 99 9

process 1 needs 12 ms and has priority 0, very high, process 3 needs  9 ms and has priority 1.

and so on …

<h2>1 10 5                        &lt;- this is user input 2  8 1  3 12 7</h2>




Process list in FCFS order as entered:

<ul>

 <li>10 5</li>

 <li>8 1 3 12 7  End of list.</li>

</ul>




fcfs wait of p1 = 0

fcfs wait of p2 = 10

fcfs wait of p3 = 18

average wait for 3 procs = 9.33333 fcfs turn-around time for p1 = 10 fcfs turn-around time for p2 = 18 fcfs turn-around time for p3 = 30 average turn-around for 3 procs = 19.3333 fcfs throughput for 3 procs = 0.1 proc/ms

&lt;&gt;&lt;&gt; end FCFS &lt;&gt;&lt;&gt;




Process list in HPF order:

2 8 1

1 10 5

3 12 7  End of list.

hpf wait of p2 = 0 hpf wait of p1 = 8 hpf wait of p3 = 18

average wait time for 3 procs = 8.66667 hpf turn-around for p2 = 8 hpf turn-around for p1 = 18 hpf turn-around for p3 = 30 average turn-around for 3 procs = 18.6667 hpf throughput for 3 procs = 0.1 proc/ms

&lt;&gt;&lt;&gt; end HPF schedule &lt;&gt;&lt;&gt;




Process list for RR in order entered:

1 10 5  2 8 1  3 12 7  End of list.

preemptive RR schedule, quantum = 1 overhead = 0

RR TA time for finished p2 = 23, needed: 8 ms, and: 8 time slices.

RR TA time for finished p1 = 27, needed: 10 ms, and: 10 time slices.

RR TA time for finished p3 = 30, needed: 12 ms, and: 12 time slices.

RR Throughput, 3 p, with q: 1, o: 0, is: 0.1 p/ms, or 100 p/us

Average RR TA, 3 p, with q: 1, o: 0, is: 26.6667

preemptive RR schedule, quantum = 1 overhead = 1

RR TA time for finished p2 = 45, needed: 8 ms, and: 8 time slices.

RR TA time for finished p1 = 53, needed: 10 ms, and: 10 time slices.

RR TA time for finished p3 = 59, needed: 12 ms, and: 12 time slices.

RR Throughput, 3 p, with q: 1, o: 1, is: 0.0508475 p/ms, or 50.8475 p/us

Average RR TA, 3 p, with q: 1, o: 1, is: 52.3333

preemptive RR schedule, quantum = 2 overhead = 0

RR TA time for finished p2 = 22, needed: 8 ms, and: 4 time slices. RR TA time for finished p1 = 26, needed: 10 ms, and: 5 time slices.

RR TA time for finished p3 = 30, needed: 12 ms, and: 6 time slices.

RR Throughput, 3 p, with q: 2, o: 0, is: 0.1 p/ms, or 100 p/us

Average RR TA, 3 p, with q: 2, o: 0, is: 26

preemptive RR schedule, quantum = 2 overhead = 1

RR TA time for finished p2 = 32, needed: 8 ms, and: 4 time slices. RR TA time for finished p1 = 38, needed: 10 ms, and: 5 time slices.

RR TA time for finished p3 = 44, needed: 12 ms, and: 6 time slices.

RR Throughput, 3 p, with q: 2, o: 1, is: 0.0681818 p/ms, or 68.1818 p/us

Average RR TA, 3 p, with q: 2, o: 1, is: 38

preemptive RR schedule, quantum = 2 overhead = 2

RR TA time for finished p2 = 42, needed: 8 ms, and: 4 time slices. RR TA time for finished p1 = 50, needed: 10 ms, and: 5 time slices.

RR TA time for finished p3 = 58, needed: 12 ms, and: 6 time slices.

RR Throughput, 3 p, with q: 2, o: 2, is: 0.0517241 p/ms, or 51.7241 p/us

Average RR TA, 3 p, with q: 2, o: 2, is: 50

preemptive RR schedule, quantum = 3 overhead = 0

RR TA time for finished p2 = 23, needed: 8 ms, and: 3 time slices. RR TA time for finished p1 = 27, needed: 10 ms, and: 4 time slices.

RR TA time for finished p3 = 30, needed: 12 ms, and: 4 time slices.

RR Throughput, 3 p, with q: 3, o: 0, is: 0.1 p/ms, or 100 p/us

Average RR TA, 3 p, with q: 3, o: 0, is: 26.6667

preemptive RR schedule, quantum = 3 overhead = 1

RR TA time for finished p2 = 30, needed: 8 ms, and: 3 time slices. RR TA time for finished p1 = 36, needed: 10 ms, and: 4 time slices.

RR TA time for finished p3 = 40, needed: 12 ms, and: 4 time slices.

RR Throughput, 3 p, with q: 3, o: 1, is: 0.075 p/ms, or 75 p/us

Average RR TA, 3 p, with q: 3, o: 1, is: 35.3333

preemptive RR schedule, quantum = 3 overhead = 2

RR TA time for finished p2 = 37, needed: 8 ms, and: 3 time slices. RR TA time for finished p1 = 45, needed: 10 ms, and: 4 time slices.

RR TA time for finished p3 = 50, needed: 12 ms, and: 4 time slices.

RR Throughput, 3 p, with q: 3, o: 2, is: 0.06 p/ms, or 60 p/us

Average RR TA, 3 p, with q: 3, o: 2, is: 44

preemptive RR schedule, quantum = 3 overhead = 3

RR TA time for finished p2 = 44, needed: 8 ms, and: 3 time slices. RR TA time for finished p1 = 54, needed: 10 ms, and: 4 time slices.

RR TA time for finished p3 = 60, needed: 12 ms, and: 4 time slices.

RR Throughput, 3 p, with q: 3, o: 3, is: 0.05 p/ms, or 50 p/us

Average RR TA, 3 p, with q: 3, o: 3, is: 52.6667

preemptive RR schedule, quantum = 4 overhead = 0

RR TA time for finished p2 = 20, needed: 8 ms, and: 2 time slices. RR TA time for finished p1 = 26, needed: 10 ms, and: 3 time slices.

RR TA time for finished p3 = 30, needed: 12 ms, and: 3 time slices.

RR Throughput, 3 p, with q: 4, o: 0, is: 0.1 p/ms, or 100 p/us

Average RR TA, 3 p, with q: 4, o: 0, is: 25.3333

preemptive RR schedule, quantum = 4 overhead = 1

RR TA time for finished p2 = 24, needed: 8 ms, and: 2 time slices. RR TA time for finished p1 = 32, needed: 10 ms, and: 3 time slices.

RR TA time for finished p3 = 37, needed: 12 ms, and: 3 time slices.

RR Throughput, 3 p, with q: 4, o: 1, is: 0.0810811 p/ms, or 81.0811 p/us

Average RR TA, 3 p, with q: 4, o: 1, is: 31

preemptive RR schedule, quantum = 4 overhead = 2

RR TA time for finished p2 = 28, needed: 8 ms, and: 2 time slices. RR TA time for finished p1 = 38, needed: 10 ms, and: 3 time slices.

RR TA time for finished p3 = 44, needed: 12 ms, and: 3 time slices.

RR Throughput, 3 p, with q: 4, o: 2, is: 0.0681818 p/ms, or 68.1818 p/us

Average RR TA, 3 p, with q: 4, o: 2, is: 36.6667

preemptive RR schedule, quantum = 4 overhead = 3

RR TA time for finished p2 = 32, needed: 8 ms, and: 2 time slices. RR TA time for finished p1 = 44, needed: 10 ms, and: 3 time slices.

RR TA time for finished p3 = 51, needed: 12 ms, and: 3 time slices.

RR Throughput, 3 p, with q: 4, o: 3, is: 0.0588235 p/ms, or 58.8235 p/us

Average RR TA, 3 p, with q: 4, o: 3, is: 42.3333




preemptive RR schedule, quantum = 4 overhead = 4

RR TA time for finished p2 = 36, needed: 8 ms, and: 2 time slices. RR TA time for finished p1 = 50, needed: 10 ms, and: 3 time slices.

RR TA time for finished p3 = 58, needed: 12 ms, and: 3 time slices.

RR Throughput, 3 p, with q: 4, o: 4, is: 0.0517241 p/ms, or 51.7241 p/us

Average RR TA, 3 p, with q: 4, o: 4, is: 48

preemptive RR schedule, quantum = 5 overhead = 0

RR TA time for finished p1 = 20, needed: 10 ms, and: 2 time slices. RR TA time for finished p2 = 23, needed: 8 ms, and: 2 time slices. RR TA time for finished p3 = 30, needed: 12 ms, and: 3 time slices.

RR Throughput, 3 p, with q: 5, o: 0, is: 0.1 p/ms, or 100 p/us

Average RR TA, 3 p, with q: 5, o: 0, is: 24.3333

preemptive RR schedule, quantum = 5 overhead = 1

RR TA time for finished p1 = 23, needed: 10 ms, and: 2 time slices. RR TA time for finished p2 = 27, needed: 8 ms, and: 2 time slices. RR TA time for finished p3 = 36, needed: 12 ms, and: 3 time slices.

RR Throughput, 3 p, with q: 5, o: 1, is: 0.0833333 p/ms, or 83.3333 p/us Average RR TA, 3 p, with q: 5, o: 1, is: 28.6667

preemptive RR schedule, quantum = 5 overhead = 2

RR TA time for finished p1 = 26, needed: 10 ms, and: 2 time slices. RR TA time for finished p2 = 31, needed: 8 ms, and: 2 time slices. RR TA time for finished p3 = 42, needed: 12 ms, and: 3 time slices.

RR Throughput, 3 p, with q: 5, o: 2, is: 0.0714286 p/ms, or 71.4286 p/us Average RR TA, 3 p, with q: 5, o: 2, is: 33

preemptive RR schedule, quantum = 5 overhead = 3

RR TA time for finished p1 = 29, needed: 10 ms, and: 2 time slices. RR TA time for finished p2 = 35, needed: 8 ms, and: 2 time slices. RR TA time for finished p3 = 48, needed: 12 ms, and: 3 time slices. RR Throughput, 3 p, with q: 5, o: 3, is: 0.0625 p/ms, or 62.5 p/us

Average RR TA, 3 p, with q: 5, o: 3, is: 37.3333

preemptive RR schedule, quantum = 5 overhead = 4

RR TA time for finished p1 = 32, needed: 10 ms, and: 2 time slices. RR TA time for finished p2 = 39, needed: 8 ms, and: 2 time slices. RR TA time for finished p3 = 54, needed: 12 ms, and: 3 time slices.

RR Throughput, 3 p, with q: 5, o: 4, is: 0.0555556 p/ms, or 55.5556 p/us

Average RR TA, 3 p, with q: 5, o: 4, is: 41.6667

preemptive RR schedule, quantum = 5 overhead = 5

RR TA time for finished p1 = 35, needed: 10 ms, and: 2 time slices. RR TA time for finished p2 = 43, needed: 8 ms, and: 2 time slices. RR TA time for finished p3 = 60, needed: 12 ms, and: 3 time slices.

RR Throughput, 3 p, with q: 5, o: 5, is: 0.05 p/ms, or 50 p/us

Average RR TA, 3 p, with q: 5, o: 5, is: 46

&lt;&gt;&lt;&gt; end preemptive RR schedule &lt;&gt;&lt;&gt;


