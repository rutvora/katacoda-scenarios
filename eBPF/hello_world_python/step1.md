# Set up the environment

For those of you who are completely new to Linux, let us begin by checking which environment we are dealing with here!
The command below shows you which Linux Distribution you are on. 

`lsb_release -a`{{execute T1}}
You should see Ubuntu 20.04 LTS 

Now, we need to install the packages required to support eBPF development.
_Note: eBPF already has support in the Linux Kernel and does not require installation. But you need to install the development tools to write and compile eBPF programs_

First, we need to update the local cache of the Ubuntu repositories, so Ubuntu knows where to fetch/download the tools from. 
`sudo apt update`{{execute T1}}

Now, we install all the required tools
`sudo apt install bpfcc-tools libbpfcc-dev linux-headers-$(uname -r) python3-bpfcc`{{execute}}
The `$(uname -r)` above returns your kernel version. This in turn is used to fetch the kernel headers (like the header files that you use in C)

Next, we fetch the Hello World code to hello_ebpf.py in your Home directory (where you currently should be)
`wget -O hello_ebpf.py https://pastebin.com/raw/Jj7xB7ZU`{{execute T1}}

With this, we conclude our set up.
