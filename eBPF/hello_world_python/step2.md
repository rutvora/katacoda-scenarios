
# Run eBPF code

Let us first run the python code in the first terminal. Don't worry, it is supposed to wait till some other event happens. It is expected that the code will display no output till then.

`python3 hello_ebpf.py`{{execute T1}}

The eBPF code is designed to display the process, the process id and some other metrics whenever a process tries to access the file-system tree in Linux (which uses the getdents64 system call on a 64-bit system).
Hence, next we run a program which shows all the files and folders in the current directory. Though, we will run this in a new Terminal as we wish to keep the python code running. Clicking below automatically runs this in a new terminal.

`ls`{{execute T2}} (This takes some time to load)

Now Head back to the first terminal to see the output!
You will notice that opening the 2nd terminal itself caused multiple "getdents64" system calls. If you type `ls` in the 2nd terminal again, you will see it appear at the end of the output on the 1st terminal.
