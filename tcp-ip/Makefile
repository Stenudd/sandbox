#CFLAGS = -Wall -Wextra -pedantic -Os -pipe -std=gnu99
CFLAGS = -Wall -Wextra -pedantic -Os -pipe -std=c99

main : main.o

up1 :
	@if [ ! -e /dev/net/tap ]; then sudo mknod /dev/net/tap c 10 200; fi
	@sudo ip link set dev tap0 up
	@sudo ip route add dev tap0 10.0.0.0/8
	@sudo ip address add dev tap0 local 10.0.0.1

up2 :
	@if [ ! -e /dev/net/tap ]; then sudo mknod /dev/net/tap c 10 200; fi
	@sudo ip link set dev tap0 up
	@sudo ip route add dev tap0 172.16.0.0/12
	@sudo ip address add dev tap0 local 172.16.0.1

clean:
	rm -f *.o
	rm -f main

.PHONY : clean up1 up2
