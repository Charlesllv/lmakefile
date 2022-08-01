
TARGET=main

#vpath %.c ./src
#vpath %.o ./obj
vpath %.h ./inc

c_source=$(shell find . -name "*.c")
c_objects=$(patsubst %.c, %.o,${c_source})

	
CC=gcc
CFLAGS=-g -O2 -Wall -I./inc

${TARGET}:${c_objects}
	@echo link...
	${CC} ${c_objects} -o $@


.c.o: #%.c:%.o
	@echo complie $<...
	${CC} ${CFLAGS} -o $@ -c $<

.PHONY:clean
clean:
	@echo 清除编译结果
	#-rm -f %.o ${TARGET}
	${RM} ${c_objects} ${TARGET}
