dvbloopback-objs := dvb_loopback.o \
                    dvblb_proc.o \
                    dvblb_forward.o

obj-m += dvbloopback.o
EXTRA_CFLAGS = -Idrivers/media/dvb-core/

# for external compilation
KDIR := /lib/modules/$(shell uname -r)/build
PWD := $(shell pwd)

default:
	$(MAKE) -C $(KDIR) M=$(PWD) modules

all: add_modver
	$(MAKE) -C $(KDIR) M=$(PWD) modules
add_modver: $(SYMVER)

clean:
	rm -f *.a
	rm -f *.o
	rm -f *.ko
	rm -f *.mod.c
	rm -f *.mod
	rm -f .*.cmd
	rm -f *~
	rm -f *.symvers
	rm -f *.order
