#设置目录变量
DIR_SRC=./src
DIR_INC=./src
DIR_OBJ=./obj
DIR_BIN=./bin

#设置可执行文件
TARGET=main
BIN_TARGET=${DIR_BIN}/${TARGET}

#配置源文件与.o文件
SRC=$(wildcard ${DIR_SRC}/*.c) #获取目录下的.c文件
OBJ=$(patsubst %.c,${DIR_OBJ}/%.o,$(notdir ${SRC})) #先取./src中的.c文件的文件名再，将.c文件替换为.o文件并加入./obj目录

#设置编译器和头文件路径
CC=gcc
CFLAGS=-g -O2 -Wall -I${DIR_INC}

#链接生成可执行文件
${BIN_TARGET}:${OBJ}
	${CC} ${OBJ} -o $@
#编译
${DIR_OBJ}/%.o:${DIR_SRC}/%.c
	${CC} ${CFLAGS} -o $@ -c $<

.PHONY :clean 
clean :
	@echo 清除编译结果
	@ls
	-rm -f ${BIN_TARGET} {OBJ} #删除可执行目标和.o文件
