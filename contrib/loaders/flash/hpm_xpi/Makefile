# SPDX-License-Identifier: BSD-3-Clause
#
BIN2C = ../../../../src/helper/bin2char.sh

OBJS=hpm_xpi_flash.inc

CROSS_COMPILE ?= riscv32-elf-
CC=$(CROSS_COMPILE)gcc
OBJCOPY=$(CROSS_COMPILE)objcopy
OBJDUMP=$(CROSS_COMPILE)objdump
LD=$(CROSS_COMPILE)ld


all: $(OBJS)

hpm_xpi_flash.inc: hpm_xpi_flash.bin
	$(BIN2C) < $< > $@

clean:
	-rm -f *.o *.elf *.lst *.pdf *.inc

.PHONY:	all clean

.INTERMEDIATE: $(patsubst %.S,%.o,$(SRCS)) $(patsubst %.S,%.elf,$(SRCS)) $(patsubst %.S,%.bin,$(SRCS))
