include ../Make.inc

CFLAGS-add += -I../src -DNDEBUG -O3 -fopenmp
LDFLAGS-add += -L../src -llsoda -lm -O3 -fopenmp -Wl,-rpath=../src/

all: test

test.o: test.c
	$(CC) $(CPPFLAGS) $(CFLAGS-add) $(CFLAGS) $(fPIC) -c $< -o $@

test: test.o
	$(CC) $(LDFLAGS)  -o $@ $^ $(LDFLAGS-add)

clean:
	rm -f test.o test
