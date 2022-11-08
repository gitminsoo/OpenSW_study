

all : myapp

myapp : myapp.o func1.o func2.o 
	gcc -o myapp myapp.o func1.o func2.o

myapp.o : myapp.c funcs.h
	gcc -c myapp.c -I./ -o myapp.o

func1.o : func1.c funcs.h
	gcc -c func1.c -I./ -o func1.o

func2.o : func2.c funcs.h
	gcc -c func2.c -I./ -o func2.o


clean :
	rm -f ./*.o myapp
