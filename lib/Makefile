#CFLAGS += -g -O3 -Wall -Wstrict-prototypes -I../include
#CFLAGS += -D_GNU_SOURCE -DNDEBUG
CFLAGS += -ggdb -Wall -Wstrict-prototypes -I../include
CFLAGS += -D_GNU_SOURCE 

.PHONY:clean
clean:
	rm -f *.[od]

# support for GNU Flymake
check-syntax:
	$(CC) $(CFLAGS) -fsyntax-only $(CHK_SOURCES)
