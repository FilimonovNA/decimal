FLAGS_FOR_TEST = -lcheck -lm -lpthread 
FLAGS_STANDART = -Wall -Wextra -Werror -std=c11 #-g #-fsanitize=address
ifeq ($(shell uname -s),Linux)
FLAGS_FOR_TEST  += -lsubunit -lrt
endif

all: test

test_comparison:
	gcc ./comparison/*.c *.c -o run_test
	./run_test

clean:
	rm -rf *.gcda *.gcno *.info *.a
	rm -rf run_cov
	rm -rf run_test
	rm -rf report  

check_style:
	clang-format -n ./lib/*.c ./tests/*.c
	clang-format -n *.h *.c ./tests/*.h%   