TARGET = ../ME.mp4a.6134706D
OBJS = acodec.o
OBJS+= ../lib/mpegbase.o ../lib/sceMpeg.o ../lib/OpenTubeCtx.o
INCDIR = ../lib ../core ../mp4
CFLAGS = -G0 -Wall -Os -std=c99
LDFLAGS = -mno-crt0 -nostartfiles

BUILD_PRX = 1

PRX_EXPORTS = ../lib/export.exp


USE_PSPSDK_LIBC = 1
LIBS = -lpspaudio -lpspaudiocodec
PSPSDK=$(shell psp-config --pspsdk-path)
include $(PSPSDK)/lib/build.mak

all:
	rm -f *.o $(TARGET) $(TARGET).elf PARAM.SFO
	psp-packer.exe $(TARGET).prx
	mv $(TARGET).prx $(TARGET)
