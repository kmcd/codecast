
## Processes 4m

  e.g. Rails develeopment: start/stop server, background jobs

  Chapter 12: Job Control
  ps / pstree
  top / htop / activity monitor
  job control: bg, fg
  kill / killall
  nohup
  at
  cron
  cron format
  Deamon processes
  init
  OSX launchctl

  Job control ( 12.1 )

  Chapter 38: Starting, Stopping, and Killing Processes
  Chapter 39: Time and Performance
  Chapter 40: Delayed Execution

  154 Running a Command in the Background
  155 Checking on a Process
  162 Canceling a Process

  127 Processes
  
## Examples
  view ps/pstree
  view top/htop/activity monitor
  kill
  job control
  crontab hour/min
  crontab day/week
  crontab month
  at

## Processes 4m

  PROCESSES
  Modern operating systems are usually multitasking, meaning that they create the illusion of doing more than one thing at once by rapidly switching from one executing program to another. The Linux kernel manages this through the use of processes. Processes are how Linux organizes the different programs wait- ing for their turn at the CPU.
  Sometimes a computer will become sluggish, or an application will stop responding. In this chapter, we will look at some of the tools available at the command line that let us examine what programs are doing and how to ter- minate processes that are misbehaving.
  This chapter will introduce the following commands:
    ps—Report a snapshot of current processes.
    top—Display tasks.
    jobs—List active jobs.
    bg—Place a job in the background.
    fg—Place a job in the foreground.
    kill—Send a signal to a process.
    killall—Kill processes by name.
    shutdown—Shut down or reboot the system. How a Process Works
  When a system starts up, the kernel initiates a few of its own activities as pro- cesses and launches a program called init. init, in turn, runs a series of shell scripts (located in /etc) called init scripts, which start all the system services. Many of these services are implemented as daemon programs, programs that just sit in the background and do their thing without having any user inter- face. So even if we are not logged in, the system is at least a little busy per- forming routine stuff.
  The fact that a program can launch other programs is expressed in the process scheme as a parent process producing a child process.
  The kernel maintains information about each process to help keep things organized. For example, each process is assigned a number called a process ID (PID). PIDs are assigned in ascending order, with init always get- ting PID 1. The kernel also keeps track of the memory assigned to each pro- cess, as well as the processes’ readiness to resume execution. Like files, processes also have owners and user IDs, effective user IDs, and so on.
  Viewing Processes with ps
  The most commonly used command to view processes (there are several) is ps. The ps program has a lot of options, but in it simplest form it is used like this:
  [me@linuxbox ~]$ ps
     PID TTY
   5198 pts/1
  10129 pts/1
      TIME CMD
  00:00:00 bash
  00:00:00 ps
   96 Chapter 10
  The result in this example lists two processes: process 5198 and pro- cess 10129, which are bash and ps respectively. As we can see, by default ps doesn’t show us very much, just the processes associated with the current terminal session. To see more, we need to add some options, but before we do that, let’s look at the other fields produced by ps. TTY is short for teletype and refers to the controlling terminal for the process. Unix is showing its age here. The TIME field is the amount of CPU time consumed by the process. As we can see, neither process makes the computer work very hard.
  If we add an option, we can get a bigger picture of what the system is doing:
  [me@linuxbox ~]$ ps x
     PID TTY
   2799 ?
   2820 ?
  15647 ?
  15751 ?
  15754 ?
  15755 ?
  15774 ?
  15793 ?
  15794 ?
  15797 ?
  STAT   TIME COMMAND
  Ssl    0:00 /usr/libexec/bonobo-activation-server –ac
  Sl     0:01 /usr/libexec/evolution-data-server-1.10 --
  Ss     0:00 /bin/sh /usr/bin/startkde
  Ss     0:00 /usr/bin/ssh-agent /usr/bin/dbus-launch --
  S      0:00 /usr/bin/dbus-launch --exit-with-session
  Ss     0:01 /bin/dbus-daemon --fork --print-pid 4 –pr
  Ss     0:02 /usr/bin/gpg-agent -s –daemon
  S      0:00 start_kdeinit --new-startup +kcminit_start
  Ss     0:00 kdeinit Running...
  S      0:00 dcopserver –nosid
  and many more...
  Adding the x option (note that there is no leading dash) tells ps to show all of our processes regardless of what terminal (if any) they are controlled by. The presence of a ? in the TTY column indicates no controlling terminal. Using this option, we see a list of every process that we own.
  Since the system is running a lot of processes, ps produces a long list. It is often helpful to pipe the output from ps into less for easier viewing. Some option combinations also produce long lines of output, so maximizing the terminal emulator window may be a good idea, too.
  A new column titled STAT has been added to the output. STAT is short for state and reveals the current status of the process, as shown in Table 10-1.
  Table 10-1: Process States
  State Meaning
  R Running. The process is running or ready to run.
  S Sleeping. The process is not running; rather, it is waiting for an event,
  such as a keystroke or network packet.
  D Uninterruptible sleep. Process is waiting for I/O such as a disk drive.
  T Stopped. Process has been instructed to stop (more on this later).
  Z A defunct or "zombie" process. This is a child process that has terminated but has not been cleaned up by its parent.
  < A high-priority process. It’s possible to grant more importance to a process, giving it more time on the CPU. This property of a process is called niceness. A process with high priority is said to be less nice because it’s taking more of the CPU’s time, which leaves less for everybody else.
  N A low-priority process. A process with low priority (a nice process) will get processor time only after other processes with higher priority have been serviced.
                  Processes 97
  The process state may be followed by other characters. These indicate various exotic process characteristics. See the ps man page for more detail.
  Another popular set of options is aux (without a leading dash). This gives us even more information:
   [me@linuxbox ~]$ ps aux
  USER PID %CPU %MEM VSZ RSS TTY root 1 0.0 0.0 2136 644 ?
  STAT START   TIME COMMAND
  Ss   Mar05   0:31 init
  root      2  0.0  0.0
  root      3  0.0  0.0
  root      4  0.0  0.0
  root      5  0.0  0.0
  root      6  0.0  0.0
  root      7  0.0  0.0
  and many more...
  0 0? 0 0? 0 0? 0 0? 0 0? 0 0?
  S   Mar05
  S   Mar05
  S   Mar05
  S   Mar05
  S   Mar05
  S   Mar05
  0:00 [kt]
  0:00 [mi]
  0:00 [ks]
  0:06 [wa]
  0:36 [ev]
  0:00 [kh]
   This set of options displays the processes belonging to every user. Using the options without the leading dash invokes the command with "BSD-style" behavior. The Linux version of ps can emulate the behavior of the ps pro- gram found in several Unix implementations. With these options, we get the additional columns shown in Table 10-2.
  Table 10-2: BSD-Style ps Column Headers
  Header Meaning
  USER User ID. This is the owner of the process. %CPU CPU usage as a percent.
  %MEM Memory usage as a percent.
  VSZ Virtual memory size.
  RSS Resident Set Size. The amount of physical memory (RAM) the process is using in kilobytes.
  START Time when the process started. For values over 24 hours, a date is used.
  Viewing Processes Dynamically with top
  While the ps command can reveal a lot about what the machine is doing, it provides only a snapshot of the machine’s state at the moment the ps com- mand is executed. To see a more dynamic view of the machine’s activity, we use the top command:
  [me@linuxbox ~]$ top
  The top program displays a continuously updating (by default, every
  3 seconds) display of the system processes listed in order of process activity.
                 98 Chapter 10
  Its name comes from the fact that the top program is used to see the "top" processes on the system. The top display consists of two parts: a system sum- mary at the top of the display, followed by a table of processes sorted by CPU activity:
  top - 14:59:20 up 6:30, 2 users, load average: 0.07, 0.02, 0.00 Tasks: 109 total, 1 running, 106 sleeping, 0 stopped, 2 zombie Cpu(s): 0.7%us, 1.0%sy, 0.0%ni, 98.3%id, 0.0%wa, 0.0%hi, 0.0%si
   Mem:    319496k total,   314860k used,
  Swap:   875500k total,   149128k used,
    4636k free,    19392k buff
  726372k free,   114676k cach
  PID USER
   6244 me
  11071 me
   6180 me
   6321 me
   4955 root
      1 root
  PR  NI  VIRT  RES  SHR
  39 19 31752 3124 2188 20 0 2304 1092 840 20 0 2700 1100 772 20 0 20944 7248 6560 20 0 104m 9668 5776 20 0 2976 528 476
  S %CPU %MEM
  S  6.3  1.0
  R  1.3  0.3
  S  0.7  0.3
  S  0.7  2.3
  S  0.3  3.0
  S  0.0  0.2
    TIME+  COMMAND
  16:24.42 trackerd
   0:00.14 top
   0:03.66 dbus-dae
   2:51.38 multiloa
   2:19.39 Xorg
   0:03.14 init
       2 root      15  -5     0    0    0 S  0.0  0.0   0:00.00 kthreadd
      3 root      RT  -5     0    0    0 S  0.0  0.0   0:00.00 migratio
      4 root      15  -5     0    0    0 S  0.0  0.0   0:00.72 ksoftirq
      5 root      RT  -5     0    0    0 S  0.0  0.0   0:00.04 watchdog
      6 root      15  -5     0    0    0 S  0.0  0.0   0:00.42 events/0
      7 root      15  -5     0    0    0 S  0.0  0.0   0:00.06 khelper
     41 root      15  -5     0    0    0 S  0.0  0.0   0:01.08 kblockd/
     67 root      15  -5     0    0    0 S  0.0  0.0   0:00.00 kseriod
    114 root      20   0     0    0    0 S  0.0  0.0   0:01.62 pdflush
    116 root      15  -5     0    0    0 S  0.0  0.0   0:02.44 kswapd0
  The system summary contains a lot of good stuff; see Table 10-3 for a rundown.
  Table 10-3: top Information Fields
    Row Field
  1 top 14:59:20
  up 6:30
           2 users
           load average:
  Meaning
  Name of the program.
  Current time of day.
  This is called uptime. It is the amount of time since the machine was last booted. In this example, the system has been up for 61⁄2 hours.
  Two users are logged in.
  Load average refers to the number of processes that are waiting to run; that is, the number of pro- cesses that are in a runnable state and are sharing the CPU. Three values are shown, each for a differ- ent period of time. The first is the average for the last 60 seconds, the next the previous 5 minutes, and finally the previous 15 minutes. Values under 1.0 indicate that the machine is not busy.
  (continued ) Processes 99

  Table 10-3 (continued ) Row Field
  Meaning
   2
  Tasks: This summarizes the number of processes and their various process states.
  0.7%us 0.7% of the CPU is being used for user processes. This means processes outside of the kernel itself.
  1.0%sy 1.0% of the CPU is being used for system (kernel) processes.
  0.0%ni 0.0% of the CPU is being used by nice (low-priority) processes.
  98.3%id 98.3% of the CPU is idle.
  0.0%wa 0.0% of the CPU is waiting for I/O.
  Mem: Shows how physical RAM is being used.
  Swap: Shows how swap space (virtual memory) is being used.
                    4 5
        The top program accepts a number of keyboard commands. The two most interesting are h, which displays the program’s help screen, and q, which quits top.
  Both major desktop environments provide graphical applications that display information similar to top (in much the same way that Task Manager in Windows does), but I find that top is better than the graphical versions because it is faster and consumes far fewer system resources. After all, our system monitor program shouldn’t add to the system slowdown that we are trying to track.
  Controlling Processes
  Now that we can see and monitor processes, let’s gain some control over them. For our experiments, we’re going to use a little program called xlogo as our guinea pig. The xlogo program is a sample program supplied with the X Window System (the underlying engine that makes the graphics on our display go), which simply displays a resizable window containing the X logo. First, we’ll get to know our test subject:
  [me@linuxbox ~]$ xlogo
  After we enter the command, a small window containing the logo should appear somewhere on the screen. On some systems, xlogo may print a warning message, but it may be safely ignored.
    100
  Chapter 10
  Note: If your system does not include the xlogo program, try using gedit or kwrite instead.
  We can verify that xlogo is running by resizing its window. If the logo is redrawn in the new size, the program is running.
  Notice how our shell prompt has not returned? This is because the shell is waiting for the program to finish, just like all the other programs we have used so far. If we close the xlogo window, the prompt returns.
  Interrupting a Process
  Let’s observe what happens when we run xlogo again. First, enter the xlogo command and verify that the program is running. Next, return to the ter- minal window and press CTRL-C.
  [me@linuxbox ~]$ xlogo [me@linuxbox ~]$
  In a terminal, pressing CTRL-C interrupts a program. This means that we politely asked the program to terminate. After we pressed CTRL-C, the xlogo window closed and the shell prompt returned.
  Many (but not all) command-line programs can be interrupted by using this technique.
  Putting a Process in the Background
  Let’s say we wanted to get the shell prompt back without terminating the xlogo program. We’ll do this by placing the program in the background. Think of the terminal as having a foreground (with stuff visible on the sur- face, like the shell prompt) and a background (with hidden stuff below the surface). To launch a program so that it is immediately placed in the back- ground, we follow the command with an ampersand character (&):
  [me@linuxbox ~]$ xlogo & [1] 28236
  [me@linuxbox ~]$
  After the command was entered, the xlogo window appeared and the shell prompt returned, but some funny numbers were printed too. This message is part of a shell feature called job control. With this message, the shell is telling us that we have started job number 1 ([1]) and that it has PID 28236. If we run ps, we can see our process:
  [me@linuxbox ~]$ ps
         PID TTY
  10603 pts/1
  28236 pts/1
  28239 pts/1
      TIME CMD
  00:00:00 bash
  00:00:00 xlogo
  00:00:00 ps
   Processes 101
  The shell’s job control facility also gives us a way to list the jobs that have been launched from our terminal. Using the jobs command, we can see the following list:
  [me@linuxbox ~]$ jobs
  [1]+ Running xlogo &
  The results show that we have one job, numbered 1, that it is running, and that the command was xlogo &.
  Returning a Process to the Foreground
  A process in the background is immune from keyboard input, including any attempt to interrupt it with a CTRL-C. To return a process to the foreground, use the fg command, as in this example:
  [me@linuxbox ~]$ jobs
  [1]+ Running xlogo & [me@linuxbox ~]$ fg %1
  xlogo
  The command fg followed by a percent sign and the job number (called a jobspec) does the trick. If we have only one background job, the jobspec is optional. To terminate xlogo, type CTRL-C.
  Stopping (Pausing) a Process
  Sometimes we’ll want to stop a process without terminating it. This is often done to allow a foreground process to be moved to the background. To stop a foreground process, type CTRL-Z. Let’s try it. At the command prompt, type xlogo, press the ENTER key, and then type CTRL-Z:
  [me@linuxbox ~]$ xlogo
  [1]+ Stopped xlogo [me@linuxbox ~]$
  After stopping xlogo, we can verify that the program has stopped by attempting to resize the xlogo window. We will see that it appears quite dead. We can either restore the program to the foreground, using the fg command, or move the program to the background with the bg command:
  [me@linuxbox ~]$ bg %1 [1]+ xlogo & [me@linuxbox ~]$
  As with the fg command, the jobspec is optional if there is only one job.
  Moving a process from the foreground to the background is handy if we launch a graphical program from the command but forget to place it in the background by appending the trailing &.
          102 Chapter 10
  Why would you want to launch a graphical program from the com- mand line? There are two reasons. First, the program you wish to run might not be listed on the window manager’s menus (such as xlogo).
  Second, by launching a program from the command line, you might be able to see error messages that would be invisible if the program were launched graphically. Sometimes, a program will fail to start up when launched from the graphical menu. By launching it from the command line instead, we may see an error message that will reveal the problem. Also, some graphical pro- grams have many interesting and useful command-line options.
  Signals
  The kill command is used to "kill" (terminate) processes. This allows us to end the execution of a program that is behaving badly or otherwise refuses to terminate on its own. Here’s an example:
  [me@linuxbox ~]$ xlogo &
  [1] 28401
  [me@linuxbox ~]$ kill 28401
  [1]+ Terminated xlogo
  We first launch xlogo in the background. The shell prints the jobspec and the PID of the background process. Next, we use the kill command and spe- cify the PID of the process we want to terminate. We could also have specified the process using a jobspec (for example, %1) instead of a PID.
  While this is all very straightforward, there is more to it. The kill com- mand doesn’t exactly "kill" processes; rather it sends them signals. Signals are one of several ways that the operating system communicates with pro- grams. We have already seen signals in action with the use of CTRL-C and CTRL-Z. When the terminal receives one of these keystrokes, it sends a signal to the program in the foreground. In the case of CTRL-C, a signal called INT (Interrupt) is sent; with CTRL-Z, a signal called TSTP (Terminal Stop) is sent. Programs, in turn, "listen" for signals and may act upon them as they are received. The fact that a program can listen and act upon signals allows it to do things like save work in progress when it is sent a termination signal.
  Sending Signals to Processes with kill
  The most common syntax for the kill command looks like this: kill [-signal] PID...
  If no signal is specified on the command line, then the TERM (Termin- ate) signal is sent by default. The kill command is most often used to send the signals shown in Table 10-4.
    Processes 103
  Table 10-4: Common Signals
   Number Name
  1 HUP
  Meaning
  Hang up. This is a vestige of the good old days when terminals were attached to remote computers with phone lines and modems. The signal is used to indicate to programs that the controlling ter- minal has "hung up." The effect of this signal can be demonstrated by closing a terminal session. The foreground program running on the terminal will be sent the signal and will terminate.
  This signal is also used by many daemon programs to cause a reinitialization. This means that when a daemon is sent this signal, it will restart and reread its configuration file. The Apache web server is an example of a daemon that uses the HUP signal in this way.
  Interrupt. Performs the same function as the CTRL-C key sent from the terminal. It will usually terminate a program.
  Kill. This signal is special. Whereas programs may choose to handle signals sent to them in different ways, including by ignoring them altogether, the KILL signal is never actually sent to the target program. Rather, the kernel immediately termin- ates the process. When a process is terminated in this manner, it is given no opportunity to "clean up" after itself or save its work. For this reason, the KILL signal should be used only as a last resort when other termination signals fail.
  Terminate. This is the default signal sent by the kill command. If a program is still "alive" enough to receive signals, it will terminate.
  Continue. This will restore a process after a STOP signal.
  Stop. This signal causes a process to pause without terminating. Like the KILL signal, it is not sent to the target process, and thus it cannot be ignored.
     2 INT
  9 KILL
        15 TERM
  18 CONT
  19 STOP
           104 Chapter 10
  Let’s try out the kill command:
  [me@linuxbox ~]$ xlogo &
  [1] 13546
  [me@linuxbox ~]$ kill -1 13546
  [1]+ Hangup xlogo
  In this example, we start the xlogo program in the background and then send it a HUP signal with kill. The xlogo program terminates, and the shell indicates that the background process has received a hangup signal. You may need to press the ENTER key a couple of times before you see the mes- sage. Note that signals may be specified either by number or by name, including the name prefixed with the letters SIG:
  [me@linuxbox ~]$ xlogo &
  [1] 13601
  [me@linuxbox ~]$ kill -INT 13601 [1]+ Interrupt xlogo [me@linuxbox ~]$ xlogo &
  [1] 13608
  [me@linuxbox ~]$ kill -SIGINT 13608 [1]+ Interrupt xlogo
  Repeat the example above and try out the other signals. Remember, you can also use jobspecs in place of PIDs.
  Processes, like files, have owners, and you must be the owner of a pro- cess (or the superuser) in order to send it signals with kill.
  In addition to the signals listed in Table 10-4, which are most often used with kill, other signals are frequently used by the system. Table 10-5 lists the other common signals.
  Table 10-5: Other Common Signals
       Number Name
  3 QUIT 11 SEGV
  20 TSTP
  28 WINCH
  Meaning
  Quit.
  Segmentation violation. This signal is sent if a program makes illegal use of memory; that is, it tried to write somewhere it was not allowed to.
  Terminal stop. This is the signal sent by the terminal when CTRL-Z is pressed. Unlike the STOP signal, the
  TSTP signal is received by the program but the pro- gram may choose to ignore it.
  Window change. This is a signal sent by the system when a window changes size. Some programs,
  like top and less, will respond to this signal by redrawing themselves to fit the new window dimensions.
              Processes 105
  For the curious, a complete list of signals can be seen with the following command:
  [me@linuxbox ~]$ kill -l
  Sending Signals to Multiple Processes with killall
  It’s also possible to send signals to multiple processes matching a specified program or username by using the killall command. Here is the syntax:
  killall [-u user] [-signal] name...
  To demonstrate, we will start a couple of instances of the xlogo program
    and then terminate them:
  [me@linuxbox ~]$ xlogo & [1] 18801
  [me@linuxbox ~]$ xlogo & [2] 18802
  [me@linuxbox ~]$ killall xlogo [1]- Terminated
  [2]+ Terminated
  xlogo xlogo
    Remember, as with kill, you must have superuser privileges to send sig- nals to processes that do not belong to you.
  More Process-Related Commands
  Since monitoring processes is an important system administration task, there are a lot of commands for it. Table 10-6 lists some to play with.
  Table 10-6: Other Process-Related Commands
  Command
  pstree
  vmstat
  xload tload
  Description
  Outputs a process list arranged in a tree-like pattern showing the parent/child relationships between processes.
  Outputs a snapshot of system resource usage including memory, swap, and disk I/O. To see a continuous display, follow the command with a time delay (in seconds) for updates (e.g., vmstat 5). Terminate the output with CTRL-C.
  A graphical program that draws a graph showing system load over time.
  Similar to the xload program, but draws the graph in the terminal. Terminate the output with CTRL-C.

  12.1.1 Foreground and Background

  UNIX distinguishes between foreground and background programs. This feature allows you to run several programs simultaneously from your terminal. When a program is running in the foreground, anything you type at the keyboard is sent to the program's standard input unless you have redirected it. As a result, you can't do anything else until the program finishes. When you run a program in the background, it is disconnected from the keyboard. Anything you type reaches the UNIX shell and is interpreted as a command. Therefore, you can run many programs simultaneously in the background. You can run only one program at a time in the foreground.

  To run a program in the background, type an ampersand ( & ) at the end of the command line. For example:

      %

      f77 program.F &


      [1] 9145
      %

  This runs a FORTRAN compilation in the background, letting you continue other work while the compilation proceeds. The shell responds by printing a job number in brackets ( [] ), followed by the process identification (PID) number ( 38.3 ) for the command. It then prompts you for a new command. Entering the command jobs produces a short report describing all the programs you are executing in the background. For example:

      %

      f77 program.F &


      [1] 9145
      %

      jobs


      [1]     + Running       f77 program.F
      %

  To bring a program from the background into the foreground, use the foreground command, fg . If you have more than one background job, follow fg with a job identifier - a percent sign ( % ) followed by the job number:

      %

      jobs


      [1]     - Running       f77 program.F
      [2]     + Stopped       vi sinus.F
      %

      fg %1

  The plus sign ( + ) in the report from jobs indicates which job will return to the foreground by default ( 12.3 ) .

  To suspend a job running in the foreground, press CTRL-z. [You can use this to stop most frozen or runaway programs until you figure out what to do next. Also, CTRL-z can stop programs that interrupt characters ( 5.9 ) like CTRL-c can't. -JP  ]

  Entering the background command, bg , lets a stopped program continue execution in the background. The foreground command, fg , restores this program to execution in the foreground. For example:

      %

      f77 -o program program.F



      [CTRL-z]

      Stopped
      %

      bg


      [1]     + Running       f77 -o program program.F
      %

  There is no prompt after the f77 command because the compiler is running in the foreground. After you press CTRL-z, the shell prints the word "Stopped" to indicate that it has stopped execution. At this point, you can enter any command; the bg command lets the job continue executing in the background. This feature is useful if you forget to type an & at the end of the command line or if you decide to do something else while the job is running.

  To terminate a background job, you can use the command's job number rather than its PID number, as follows:

      %

      kill %1

  If you omit it, UNIX interprets the job number as a process number. This will probably be the process number of some operating system function. UNIX will not let you make such a mistake unless you are superuser ( 1.24 ) . If you are superuser, the command is fatal. You may be superuser from time to time and therefore should not develop sloppy habits.

  In the next few seconds, press RETURN a few times. You should see the message:

      [1]  Terminated    f77 -o program program.F

  If you don't see that, use the jobs command to check whether the job is still running. If it's still running, use the -9 option as a last resort:

      %

      kill -9 %1


      [1]  Killed        f77 -o program program.F

  The -9 option doesn't give the process a chance to clean up its temporary files and exit gracefully, so don't use it unless you need to.

  A program running in the background cannot read input from a terminal. If a background job needs terminal input, it will stop; the jobs command will print the message Stopped (tty input) . Before the program can continue, you must bring it into the foreground with the fg command and type the required input. You can save yourself this trouble by redirecting the program's input so that it reads all its data from a file. You may also want to redirect standard output and standard error. If you don't, any output the program produces will appear on your terminal (unless you've used stty tostop ( 12.7 ) ). Since you will probably be using other commands, having miscellaneous data and other messages flying across your terminal may be confusing.

  On systems and shells without job control features, an & will start a command in the background. It is impossible to move a job from the foreground to the background or vice versa. The ps ( 38.5 ) command is the only tool available for determining what background jobs you have running.

  Two commands, time and /bin/time , provide simple timings. Their information is highly accurate, because no profiling overhead distorts the program's performance. Neither program provides any analysis on the routine or trace level. They report the total execution time, some other global statistics, and nothing more. You can use them on any program.

  time and /bin/time differ primarily in that time is built into the C shell. Therefore, it cannot be used in Bourne shell scripts or in makefiles. It also cannot be used if you prefer the Bourne shell ( sh ). /bin/time is an independent executable file and therefore can be used in any situation. To get a simple program timing, enter either time or /bin/time , followed by the command you would normally use to execute the program. For example, to time a program named analyze , enter the following command:

      %

      time analyze inputdata outputfile


      9.0u 6.7s 0:30 18% 23+24k 285+148io 625pf+0w

  This indicates that the program spent 9.0 seconds on behalf of the user (user time), 6.7 seconds on behalf of the system (system time, or time spent executing UNIX kernel routines on the user's behalf), and a total of 30 seconds elapsed time. Elapsed time is the wall clock time from the moment you enter the command until it terminates, including time spent waiting for other users, I/O time, etc.

  By definition, the elapsed time is greater than your total CPU time and can even be several times larger. You can set programs to be timed automatically (without typing time first) or change the output format by setting the csh time variable ( 39.3 ) .

  The example above shows the CPU time as a percentage of the elapsed time (18 percent). The remaining data report virtual memory management and I/O statistics. The meaning varies, depending on your shell; check your online csh manual page or article 39.3 .

  In this example, under SunOS 4.1.1, the other fields show the amount of shared memory used, the amount of nonshared memory used ( k ), the number of block input and output operations ( io ), and the number of page faults plus the number of swaps ( pf and w ). The memory management figures are unreliable in many implementations, so take them with a grain of salt.

  /bin/time reports only the real time (elapsed time), user time, and system time. For example:

      %

      /bin/time analyze inputdata outputfile


             60.8 real        11.4 user         4.6 sys

  [If you use the Bourne shell, you can just type time . -JP  ] This reports that the program ran for 60.8 seconds before terminating, using 11.4 seconds of user time and 4.6 seconds of system time, for a total of 16 seconds of CPU time.

  There's a third timer on many systems: timex . It can give much more detail if your system has process accounting enabled. Check the timex (1) manpage.

  Article 39.5 has more about the terms used in this article.

  UNIX Power Tools
  Previous: 40.11 Send Yourself Reminder Mail 	Chapter 40
  Delayed Execution 	Next: 40.13 Adding crontab Entries

  40.12 Periodic Program Execution: The cron Facility

  cron allows you to schedule programs for periodic execution. For example, you can use cron to call a particular UUCP ( 1.33 ) site every hour, to clean up editor backup files every night, or to perform any number of other tasks. However, cron is not a general facility for scheduling program execution off-hours; use the at command ( 40.3 ) .

  With redirection ( 13.1 ) , cron can send program output to a log file or to any username via the mail system ( 1.33 ) .

      NOTE: cron jobs are run by a system program in an environment that's much different from your normal login sessions. The search path ( 8.7 ) is usually shorter; you may need to use absolute pathnames for programs that aren't in standard system directories. Be careful about using command aliases, shell functions and variables, and other things that may not be set for you by the system.

  40.12.1 Execution Scheduling

  The cron system is serviced by the cron daemon ( 1.14 ) . What to run and when to run it are specified to cron by crontab entries, which are stored in the system's cron schedule. Under BSD, this consists of the files /usr/lib/crontab and /usr/lib/crontab.local ; either file may be used to store crontab entries. Both are ASCII files and may be modified with any text editor. Since usually only root has access to these files, all cron scheduling must go through the system administrator. This can be either an advantage or a disadvantage, depending on the needs and personality of your site.

  Under System V (and many other versions of UNIX), any user may add entries to the cron schedule. crontab entries are stored in separate files for each user. The crontab files are not edited directly by ordinary users, but are placed there with the crontab command (described later in this section). [In my experience, the cron jobs are run from your home directory. If you read a file or redirect output to a file with a relative pathname ( 14.2 ) , that'll probably be in your home directory. Check your system to be sure. -JP  ]

  crontab entries direct cron to run commands at regular intervals. Each one-line entry in the crontab file has the following format:

      mins hrs day-of-month month weekday username cmd (BSD)
      mins hrs day-of-month month weekday cmd (System V)

  Spaces separate the fields. However, the final field, cmd , can contain spaces within it (i.e., the cmd field consists of everything after the space following weekday ); the other fields must not contain spaces. The username field is used in the BSD version only and specifies the username under which to run the command. Under System V, commands are run by the user who owns the crontab in which they appear (and for whom it is named).

  The first five fields specify the times at which cron should execute cmd . Their meanings are described in Table 40.1 .
  Table 40.1: crontab Entry Time Fields Field 	Meaning 	Range
  mins 	The minutes after the hour. 	0-59
  hrs 	The hours of the day. 	0-23 (0 = midnight)
  day-of-month 	The day within a month. 	1-31
  month 	The month of the year. 	1-12
  weekday 	The day of the week. 	1-7 (1 = Monday) BSD
      0-6 (0=Sunday) System V

  These fields can contain a single number, a pair of numbers separated by a dash (indicating a range of numbers), a comma-separated list of numbers and ranges, or an asterisk (a wildcard that represents all valid values for that field).

  If the first character in an entry is a hash mark (#), cron will treat the entry as a comment and ignore it. This is an easy way to temporarily disable an entry without permanently deleting it.

  Here are some example crontab entries (shown in System V format):






  2>&1




  \%





  0,15,30,45 * * * *  (echo -n '   '; date; echo "") >/dev/console
  0,10,20,30,40,50 7-18 * * * /usr/lib/atrun
  7 0 * * *  find / -name "*.bak" -type f -atime +7 -exec rm {} \;
  12 4 * * *  /bin/sh /usr/adm/ckdsk >/usr/adm/disk.log 2>&1
  22 2 * * *  /bin/sh /usr/adm/ckpwd 2>&1 | mail root
  30 3 * * 1 /bin/csh -f /usr/lib/uucp/uu.weekly >/dev/null 2>&1
  12 5 15-21 * * test `date +\%a` = Mon && /usr/local/etc/mtg-notice
  #30 2 * * 0,6  /usr/lib/newsbin/news.weekend

  The first entry displays the date on the console terminal every fifteen minutes (on the quarter hour); notice that multiple commands are enclosed in parentheses in order to redirect their output as a group. (Technically, this says to run the commands together in a subshell ( 13.7 ) .) The second entry runs /usr/lib/atrun every ten minutes from 7:00 a.m. to 6:00 p.m. daily. The third entry runs a find command at seven minutes after midnight to remove all .bak files not accessed in seven days. [To cut wear and tear and load on your disk, try to combine find jobs ( 23.22 ) . Also, as article 40.5 explains, try not to schedule your jobs at often-chosen times like 1:00 a.m., 2:00 a.m., and so on; pick oddball times like 4:12 a.m. -JP  ]

  The fourth and fifth lines run a shell script every day, at 4:12 a.m. and 2:22 a.m., respectively. The shell to execute the script is specified explicitly on the command line in both cases; the system default shell, usually the Bourne shell, is used if none is explicitly specified. Both lines' entries redirect standard output and standard error, sending it to a file in one case and mailing it to root in the other.

  The sixth entry executes a C shell script named uu.weekly , stored in /usr/lib/uucp , at 3:30 a.m. on Monday mornings. Notice that the command format - specifically the output redirection - is for the Bourne shell even though the script itself will be run under the C shell. The seventh entry runs on the third Monday of every month; there's more explanation below. The final entry would run the command /usr/lib/newsbin/news.weekend at 2:30 a.m. on Saturday and Sunday mornings if it were not disabled with a # . ( # can also be used to add comments to your crontab .)

  The fourth through sixth entries illustrate three output-handling alternatives: redirecting it to a file, piping it through mail, and discarding it to /dev/null ( 13.14 ) . If no output redirection is performed, the output is sent via mail to the user who ran the command.

  The cmd field can be any UNIX command or group of commands (properly separated with semicolons). The entire crontab entry can be arbitrarily long, but it must be a single physical line in the file.

  One problem with the crontab syntax is that it lets you specify any day of the month, and any day of the week; but it doesn't let you construct cases like "the third Monday of every month." You might think that the crontab entry:

      12 5 15-21 * 1

      your-command

  would do the trick, but it won't; this crontab entry runs your command on every Monday, plus the 15th through the 21st of each month. [1] An answer from Greg Ubben is shown in the seventh entry. He uses the test ( 44.20 ) and date ( 51.10 ) commands to compare the name of today (like Tue ) to the day we want the entry to be executed (here, Mon ). This entry will be run between the 15th and 21st of each month, but the mtg-notice command will only run on the Monday during that period. The shell's && operator ( 44.9 ) runs the mtg-notice command only when the previous test succeeds. Greg actually writes the entry as shown here, testing for failure of the test command:

      [1] This strange behavior seems to be a System V peculiarity that somehow infected the rest of the world. "True" BSD systems behave the way we explained earlier. However, SunOS 4.X systems have incorporated System V's behavior; and, with the advent of Solaris, there are relatively few true commercial BSD systems left in the world.

      12 5 15-21 * * test `date +\%a` != Mon || /usr/local/etc/mtg-notice

  He did it in that "backwards" way so the cron job's exit status would be 0 (success) in the case when it doesn't execute mtg-notice . You may need that technique, too.

  The cron command starts the cron program. It has no options. Once started, cron never terminates. It is normally started automatically by one of the system initialization scripts. cron reads the crontab file(s) every minute to see whether there have been changes. Therefore, any change to its schedule will take effect within one minute.

  - AF , JP

  The at facility submits a command line (or a script) for execution at an arbitrary later time. It has the form:

    %

    at



    options time < scriptfile

  This submits the scriptfile for execution at a later time . The redirection ( < ) isn't required on BSD and some other UNIX systems. If you don't want to write a script, you can omit it and type your commands on the terminal, terminated by CTRL-d:

      %

      at



      options time
      Command 1
      Command 2


      ...

      [CTRL-d]

  The time is most commonly a four-digit number representing a time on a 24-hour clock. For example, 0130 represents 1:30 a.m. and 1400 represents 2 p.m. You can also use abbreviations such as 1am , 130pm , and so on.

  11.9 Using date and cron to Run a Script on the Nth Day

  Problem
  You need to run a script on the Nth weekday of the month (e.g., the second Wednes- day), and most crons will not allow that.
  Solution
  Use a bit of shell code in the command to be run. In your Linux Vixie Cron crontab adapt one of the following lines. If you are using another cron program, you may need to convert the day of the week names to numbers according to the schedule your cron uses (0–6 or 1–7) and use +%w (day of week as number) in place of +%a (locale’s abbreviated weekday name):
       # Vixie Cron
       # Min   Hour DoM   Mnth DoW Program
       # 0-59 0-23 1-31 1-12 0-7
       # Run the first Wednesday @ 23:00
       00 23 1-7 * Wed [ "$(date '+%a')" == "Wed" ] && /path/to/command args to command
       # Run the second Thursday @ 23:00
       00 23 8-14 * Thu [ "$(date '+%a')" == "Thu" ] && /path/to/command
       # Run the third Friday @ 23:00
       00 23 15-21 * Fri [ "$(date '+%a')" == "Fri" ] && /path/to/command
       # Run the fourth Saturday @ 23:00
       00 23 22-27 * Sat [ "$(date '+%a')" == "Sat" ] && /path/to/command
       # Run the fifth Sunday @ 23:00
       00 23 28-31 * Sun [ "$(date '+%a')" == "Sun" ] && /path/to/command
  Note that any given day of the week doesn’t always happen five times during one month, so be sure you really know what you are asking for if you schedule something for the fifth week of the month.
    228
  | Chapter 11: Working with Dates and Times
  Discussion
  Most versions of cron (including Linux’s Vixie Cron) do not allow you to schedule a job on the Nth day of the month. To get around that, we schedule the job to run dur- ing the range of days when the Nth day we need occurs, then check to see if it is the correct day on which to run. The "second Wednesday of the month" must occur somewhere in the range of the 8th to 14th day of the month. So we simply run every day and see if it’s Wednesday. If so, we execute our command.
  Table 11-2 shows the ranges noted above.
  Table 11-2. Day ranges for each week of a month
  Week
  First
  Second
  Third
  Fourth
  Fifth (see previous warning note)
  Day range
  1 to 7
  8 to 14 15 to 21 22 to 27 28 to 31
   We know this almost seems too simplistic; check a calendar if you don’t believe us:
      $ cal 10 2006
          October 2006
  S M Tu W Th F S 1234567 8 9 10 11 12 13 14
      15 16 17 18 19 20 21
      22 23 24 25 26 27 28
      29 30 31



### VO 600w

  ps—Report a snapshot of current processes.
  pstree

  psa

  top—Display tasks.
  open -a 'activity monitor'
  htop

  kill—Send a signal to a process.
  killall—Kill processes by name.

  kill -TERM
  kill -9

  jobs—List active jobs.
  bg—Place a job in the background.
  fg—Place a job in the foreground.

  To run a program in the background, type an ampersand ( & ) at the end of the command line. For example:

      %

      f77 program.F &


      [1] 9145
      %

  This runs a FORTRAN compilation in the background, letting you continue other work while the compilation proceeds. The shell responds by printing a job number in brackets ( [] ), followed by the process identification (PID) number ( 38.3 ) for the command. It then prompts you for a new command. Entering the command jobs produces a short report describing all the programs you are executing in the background. For example:

      %

      f77 program.F &


      [1] 9145
      %

      jobs


      [1]     + Running       f77 program.F
      %

  To bring a program from the background into the foreground, use the foreground command, fg . If you have more than one background job, follow fg with a job identifier - a percent sign ( % ) followed by the job number:

      %

      jobs


      [1]     - Running       f77 program.F
      [2]     + Stopped       vi sinus.F
      %

      fg %1

  The plus sign ( + ) in the report from jobs indicates which job will return to the foreground by default ( 12.3 ) .

  To suspend a job running in the foreground, press CTRL-z. [You can use this to stop most frozen or runaway programs until you figure out what to do next. Also, CTRL-z can stop programs that interrupt characters ( 5.9 ) like CTRL-c can't. -JP  ]

  Entering the background command, bg , lets a stopped program continue execution in the background. The foreground command, fg , restores this program to execution in the foreground. For example:

      %

      f77 -o program program.F



      [CTRL-z]

      Stopped
      %

      bg


      [1]     + Running       f77 -o program program.F
      %

  There is no prompt after the f77 command because the compiler is running in the foreground. After you press CTRL-z, the shell prints the word "Stopped" to indicate that it has stopped execution. At this point, you can enter any command; the bg command lets the job continue executing in the background. This feature is useful if you forget to type an & at the end of the command line or if you decide to do something else while the job is running.

  To terminate a background job, you can use the command's job number rather than its PID number, as follows:

      %

      kill %1

  If you omit it, UNIX interprets the job number as a process number. This will probably be the process number of some operating system function. UNIX will not let you make such a mistake unless you are superuser ( 1.24 ) . If you are superuser, the command is fatal. You may be superuser from time to time and therefore should not develop sloppy habits.

  In the next few seconds, press RETURN a few times. You should see the message:

      [1]  Terminated    f77 -o program program.F

  If you don't see that, use the jobs command to check whether the job is still running. If it's still running, use the -9 option as a last resort:

      %

      kill -9 %1


      [1]  Killed        f77 -o program program.F

  The -9 option doesn't give the process a chance to clean up its temporary files and exit gracefully, so don't use it unless you need to.

  A program running in the background cannot read input from a terminal. If a background job needs terminal input, it will stop; the jobs command will print the message Stopped (tty input) .

  /bin/time reports only the real time (elapsed time), user time, and system time. For example:

      %

      /bin/time analyze inputdata outputfile


             60.8 real        11.4 user         4.6 sys

  cron allows you to schedule programs for periodic execution. For example, you can use cron to call a particular UUCP ( 1.33 ) site every hour, to clean up editor backup files every night, or to perform any number of other tasks. However, cron is not a general facility for scheduling program execution off-hours; use the at command ( 40.3 ) .

  With redirection ( 13.1 ) , cron can send program output to a log file or to any username via the mail system ( 1.33 ) .

    NOTE: cron jobs are run by a system program in an environment that's much different from your normal login sessions. The search path ( 8.7 ) is usually shorter; you may need to use absolute pathnames for programs that aren't in standard system directories. Be careful about using command aliases, shell functions and variables, and other things that may not be set for you by the system.


  mins 	The minutes after the hour. 	0-59
  hrs 	The hours of the day. 	0-23 (0 = midnight)
  day-of-month 	The day within a month. 	1-31
  month 	The month of the year. 	1-12
  weekday 	The day of the week. 	1-7 (1 = Monday) BSD
   0-6 (0=Sunday) System V


  The at facility submits a command line (or a script) for execution at an arbitrary later time. It has the form:

    %

    at



    options time < scriptfile

  This submits the scriptfile for execution at a later time . The redirection ( < ) isn't required on BSD and some other UNIX systems. If you don't want to write a script, you can omit it and type your commands on the terminal, terminated by CTRL-d:

      %

      at


      options time
      Command 1
      Command 2


      ...

      [CTRL-d]

  The time is most commonly a four-digit number representing a time on a 24-hour clock. For example, 0130 represents 1:30 a.m. and 1400 represents 2 p.m. You can also use abbreviations such as 1am , 130pm , and so on.

  https://developer.apple.com/library/mac/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/ScheduledJobs.html


