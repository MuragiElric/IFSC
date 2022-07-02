CC = gcc
CC_FLAGS = 	-lm		\
			-O2
OUT_FILES = $(addsuffix .o,$(addprefix bin/, main $(notdir $(basename $(wildcard libs/*.c)))))

executable.exe: $(OUT_FILES)
	$(CC) $(OUT_FILES) -o executable.exe $(CC_FLAGS)

bin/main.o: main.c main.h
	$(CC) -o bin/main.o main.c -c $(CC_FLAGS)

bin/%.o: libs/%.c libs/%.h
	$(CC) -o $@ $< -c $(CC_FLAGS)

run: executable.exe
	./executable.exe

clean:
	rm bin/*.o executable.exe

