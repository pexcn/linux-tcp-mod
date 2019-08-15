NAME = tcp_tsunami
obj-m += $(NAME).o

all:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules

clean:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean

install:
	install $(NAME).ko /lib/modules/$(shell uname -r)/kernel/net/ipv4
	depmod -a
	modprobe $(NAME)

uninstall:
	rm -f /lib/modules/$(shell uname -r)/kernel/net/ipv4/$(NAME).ko
	depmod -a
