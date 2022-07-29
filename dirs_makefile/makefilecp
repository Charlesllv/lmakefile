# 设置目录变量
DIR_SRC=./src
DIR_INC=./inc
DIR_OBJ=./obj
DIR_BIN=./bin

# 设置可执行文件
TARGET=main
BIN_TARGET=${DIR_BIN}/${TARGET}

# 配置源文件和 .o 文件
SRC=$(wildcard ${DIR_SRC}/*.c)
OBJ=$(patsubst %.c, ${DIR_OBJ}/%.o, $(notdir ${SRC}))

# 设置编译器和头文件路径(-I指定.h文件路径)
CC=gcc
CFLAGS=-g -O2 -Wall -I${DIR_INC}

# 链接生成可执行文件
${BIN_TARGET}:${OBJ}
	${CC} ${OBJ} -o $@

# 编译，使用 % 进行匹配
${DIR_OBJ}/%.o:${DIR_SRC}/%.c
	${CC} ${CFLAGS} -o $@ -c $<

.PHONY : clean
# 清除可执行文件和编译文件
clean : 
	@echo 清除编译结果
	-rm -f ${BIN_TARGET} ${OBJ}


