TARGET = ../kubridge
OBJS = kernel.o

INCDIR = ../lib ../core
CFLAGS = -G0 -Wall -O3 -std=c99
LDFLAGS = -mno-crt0 -nostartfiles

BUILD_PRX = 1

PRX_EXPORTS = ../lib/kexport.exp
$(shell psp-build-exports -s ${PRX_EXPORTS})

USE_KERNEL_LIBC = 1
LIBS = -lpspsystemctrl_kernel -lpsppower
PSPSDK=$(shell psp-config --pspsdk-path)
include $(PSPSDK)/lib/build.mak

all:
	rm -f *.o $(TARGET) $(TARGET).elf PARAM.SFO
	psp-packer.exe $(TARGET).prx
	mv $(TARGET).prx $(TARGET)
