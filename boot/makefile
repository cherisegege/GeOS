CC	= gcc -m32 -march=i386
CFLAGS	= -I. -Wall -Wextra -nostdlib -fno-builtin -nostartfiles -nodefaultlibs
LD	= ld -m elf_i386
 
OBJFILES = boot.o kernel.o
 
all: kernel.elf
 
boot.o:boot.S
	$(CC) $(CFLAGS) -o $@ -c $<
 
kernel.o:kernel.c
	$(CC) $(CFLAGS) -o $@ -c $<
 
kernel.elf: $(OBJFILES)
	$(LD) -T linker.ld -o $@ $^
 
clean:
	$(RM) $(OBJFILES) kernel.elf
 
install:
	# $(RM) $(OBJFILES) kernel.elf
