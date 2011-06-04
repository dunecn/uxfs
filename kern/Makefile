# If KERNELRELEASE is defined, we've been infoked from the
# kernel build system and can use its language
ifneq ($(KERNELRELEASE),)
	obj-m := ux_dir.o ux_alloc.o ux_file.o ux_inode.o
# Otherwise we were called directly from the command
# line; invoke the kernel build system
else
	KERNELDIR ?= /lib/modules/$(shell uname -r)/build
	PWD := $(shell pwd)
default:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules
endif
