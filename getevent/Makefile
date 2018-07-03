SOURCES = $(wildcard src/*.c)
HEADERS = $(wildcard inc/*.h)
OBJS 	= $(patsubst %.c, %.o, $(SOURCES))

IFLAGS 	= -I./inc

CFLAGS      = -O2 -Wall -g
LD_FLAGS	= 

BIN = getevent
$(BIN) : $(OBJS)
	$(CC) -o $@ $(OBJS) $(LD_FLAGS)

%.o:%.c
	$(CC) -c -o $@ $(CFLAGS) $(IFLAGS) $<

clean :
	rm -f src/*.o  $(BIN)