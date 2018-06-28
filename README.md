# distcc-manual-wiki

Welcome to the distcc-manual wiki!

Here is the guide how to setup and start using distcc for your compilation:

1. Install distcc on your master and slave machines by running
`sudo apt install distcc`
2. On your slaves run
`sudo distccd --daemon -a IPs_OF_YOUR_SLAVES`
3. Change slaves' config
Edit `/etc/default/distcc`:

```bash
STARTDISTCC="true"

# Change ip according to your master ip
ALLOWEDNETS="127.0.0.1 192.168.0.107 "

# Set max number of jobs
JOBS="4"
```
4. On your master run
`export DISTCC_HOSTS='localhost A B C'`, 
where A, B and C are the slaves' IPs or hostnames
5. Force compiler on master use distcc
```
export PATH="/usr/lib/distcc:$PATH"
export CC=/usr/lib/distcc/gcc
export CXX=/usr/lib/distcc/g++
```

6. Compile!
`make -j8 CC=distcc`
