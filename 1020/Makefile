OBJ_FILES = obj/func1.o obj/func2.o

all : bin/myapp

bin/myapp : lib/libmyfuncs.so lib/libmyfuncs.so.1 src/myapp.c include/funcs.h
	gcc -o bin/myapp src/myapp.c -L./lib/ -lmyfuncs -I./include/


lib/libmyfuncs.so : lib/libmyfuncs.so.1.0
	ln -s libmyfuncs.so.1.0 lib/libmyfuncs.so

lib/libmyfuncs.so.1 : lib/libmyfuncs.so.1.0
	ln -s libmyfuncs.so.1.0 lib/libmyfuncs.so.1

lib/libmyfuncs.so.1.0 : $(OBJ_FILES)
	ld -shared -soname=libmyfuncs.so.1 obj/*.o -o lib/libmyfuncs.so.1.0 -lc

obj/%.o : src/%.c include/funcs.h
	gcc -fPIC -c $< -o $@ -I./include/

clean :
	rm -rf lib/* obj/* bin/*
