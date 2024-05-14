CC = gcc -std=c11
FLAGS = -Wall -Wextra -Werror
LIBS = --coverage -lcheck -lm -lpthread -lsubunit 
NAME = s21_string

all: gcov_report

clean:
	rm -rf *.o *.a *.gcno *.html *.gcda
	rm -rf ./report/
	rm -rf report.info

clang_test:
	clang-format -n -style=Google *.c *.h

s21_string.a:
	${CC} ${FLAGS} ${NAME}/*.c s21_sprintf/s21_sprintf.c s21_sscanf/s21_sscanf.c
	ar rc ${NAME}.a *.o
	ranlib ${NAME}.a

test:
	${CC} ${FLAGS} -o ${NAME}.o s21_string_test.c ${NAME}/*.c ${LIBS}
	 ./${NAME}.o

test_sharp:
	${CC} ${FLAGS} -o test_sharp.o s21_sharp_tests.c ${NAME}/*.c ${LIBS}
	 ./test_sharp.o 

test_sprintf:
	${CC} ${FLAGS} -o test_sprintf.o s21_sprintf/*.c ${NAME}/*.c ${LIBS}
	 ./test_sprintf.o

test_sscanf:
	${CC} ${FLAGS} -o test_sscanf.o s21_sscanf/*.c ${NAME}/*.c ${LIBS}
	 ./test_sscanf.o

gcov_report: clean test test_sharp test_sprintf test_sscanf
	gcov -o report.info -c -d .
	lcov -t "${NAME}" -o report.info -c -q -d .
	genhtml -o report report.info
	open ./report/index.html