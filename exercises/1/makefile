CC = gcc
cflags = -Wall -g

main: bar.o main.o
	$(CC) bar.o main.o $(cflags) -o main

bar.o: bar.h bar.c
	$(CC) -c bar.c $(cflags)

main.o: main.c bar.h
	$(CC) -c main.c $(cflags)

# -------------------------------------

math: math_lib.o useLib.o libmath.a
	$(CC) math_lib.o useLib.o libmath.a $(cflags) -o math

libmath.a: math_lib.o
	ar cd libmath.a math_lib.o

math_lib.o: math_lib.c
	$(CC) -c math_lib.c $(cflags)

useLib.o: useLib.c
	$(CC) -c useLib.c $(cflags)

clean:
	rm *.o main math *.a
