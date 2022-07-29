#选择编译器
CC=gcc
CFLAGS=-g -O2 -Wall

#链接生成执行文件main，依赖main.o 和child.o
main:main.o child.o
	${CC} main.o child.o -o main

#编译生成main.o，依赖main.c和child.h
main.0:main.c child.h
	${CC} ${CFLAGS} -c main.c

#编译生成child.o，依赖child.c和child.h
child.o:child.c child.h
	${CC} ${CFLAGS} -c child.c

.PHONY :clean
#清除编译产生的中间文件
clean :
	@echo 清除编译结果
	-rm -f *.o main

