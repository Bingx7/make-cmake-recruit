CC = gcc
CFLAGS = -Wall -Wextra -Iinclude

calculator: main.o calculator.o logger.o
	gcc main.o calculator.o logger.o -o calculator

main.o: src/main.c include/calculator.h include/logger.h
	gcc -c src/main.c -Iinclude -o main.o

calculator.o: src/calculator.c include/calculator.h
	gcc -c src/calculator.c -Iinclude -o calculator.o
	

logger.o: src/logger.c include/logger.h
	gcc -c src/logger.c -Iinclude -o logger.o

.PHONY: clean
clean:
	rm -f ./*.o calculator
