# distcc-manual-wiki

Welcome to the distcc-manual wiki!

Here is the guide how to setup and start using distcc for your compilation:

1. Install distcc on your master and slave machines by running
`sudo apt install distcc`
2. On your slaves run
`sudo distccd --daemon -a IPs_OF_YOUR_SLAVES`
3. On your master run
`export DISTCC_HOSTS='localhost A B C`, 
where A, B and C are the slaves' IPs
4. Compile!
`make -j8 CC=distcc`
