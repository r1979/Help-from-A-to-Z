# Help-from-A-to-Z

## Linux Swap space

The first thing we need to do is create an empty file of the required size. To do this open the Terminal and execute the command given below. In this example I am creating a 3GB swap file. You will not probably need that much. So, enter your own value.

`$ cd /`

`$ sudo dd if=/dev/zero of=swapfile bs=1M count=3000`

To set it as 1GB, change the count value (3000 in the example above) to 1000, 1500 for 1.5GB etc. Now change the file created to a swap file with the command below.

`$ sudo mkswap swapfile`

Turn on the swap file with the command,

`$ sudo swapon swapfile`

To ensure that the swap file is turned on automatically at system startup, open fstab.

`$ sudo nano etc/fstab`

And add the line given below. Save and close.

`/swapfile none swap sw 0 0`

That is it. You can check if the system is using the swap file you created with the command

`$ cat /proc/meminfo`

----

`cd /`
`sudo dd if=/dev/zero of=swapfile bs=1M count=3000`
`sudo chmod 600 swapfile`
`sudo mkswap swapfile`
`sudo swapon swapfile`
`sudo nano etc/fstab`
