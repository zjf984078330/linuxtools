# =====================================================================
# Copyright (C) 2018 zhihong Technology. All rights reserved.
#
# Brief		Makefile for building i2c-tools
# Author	wangningbin
# Date		2018-07-03
# =====================================================================
SOURCES = $(wildcard tools/*.c)
HEADERS = $(wildcard include/linux/*.h)
I2CBUSSES_SRC_FILES := tools/i2cbusses.c tools/util.c
I2CDETECT_SRC_FILES := tools/i2cdetect.c
I2CDETECT_OBJS 	= $(patsubst %.c, %.o, $(I2CBUSSES_SRC_FILES) $(I2CDETECT_SRC_FILES))

I2CDUMP_SRC_FILES := tools/i2cdump.c
I2CDUMP_OBJS 	= $(patsubst %.c, %.o, $(I2CBUSSES_SRC_FILES) $(I2CDUMP_SRC_FILES))

I2CGET_SRC_FILES := tools/i2cget.c
I2CGET_OBJS 	= $(patsubst %.c, %.o, $(I2CBUSSES_SRC_FILES) $(I2CGET_SRC_FILES))

I2CSET_SRC_FILES := tools/i2cset.c
I2CSET_OBJS 	= $(patsubst %.c, %.o, $(I2CBUSSES_SRC_FILES) $(I2CSET_SRC_FILES))




IFLAGS 	= -I./include/linux

CFLAGS      = -O2 -Wall -g
LD_FLAGS	= 

I2CDETECT = i2cdetect
I2CDUMP = i2cdump
I2CGET = i2cget
I2CSET = i2cset

start : $(I2CDETECT_OBJS) $(I2CDUMP_OBJS) $(I2CGET_OBJS) $(I2CSET_OBJS)
	$(CC) -o $(I2CDETECT) $(I2CDETECT_OBJS) $(LD_FLAGS)
	$(CC) -o $(I2CDUMP) $(I2CDUMP_OBJS) $(LD_FLAGS)
	$(CC) -o $(I2CGET) $(I2CGET_OBJS) $(LD_FLAGS)
	$(CC) -o $(I2CSET) $(I2CSET_OBJS) $(LD_FLAGS)
	
%.o:%.c
	$(CC) -c -o $@ $(CFLAGS) $(IFLAGS) $<

clean :
	rm -f tools/*.o  $(I2CDETECT) $(I2CDUMP) $(I2CGET) $(I2CSET)