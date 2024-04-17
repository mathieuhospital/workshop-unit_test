##
## EPITECH PROJECT, 2024
## Workshop_Unit_Tests
## File description:
## Makefile
##

NAME	=	my_str_to_word_array

TESTS_NAME =	unit_tests

CC	=	gcc

CFLAGS	=	-W -Wall -Wextra -Werror -I./includes

SRC_MAIN	=	src/src_main/main.c

SRC	=	$(shell find src/ -name '*.c' -not -name 'main.c')

OBJ	=	$(SRC:.c=.o)

OBJ_MAIN	=	$(SRC_MAIN:.c=.o)

all:	$(NAME)

$(NAME):	$(OBJ) $(OBJ_MAIN)
	$(CC) -o $(NAME) $(OBJ) $(OBJ_MAIN) $(CFLAGS)

clean:
	$(RM) $(OBJ) $(OBJ_MAIN)

fclean:	clean
	$(RM) $(NAME)

re:	fclean all

tests_run:
	$(CC) $(CFLAGS) $(SRC) $(shell find tests/ -name '*.c') -o unit_tests -lcriterion --coverage

tests_clean:
	$(RM) unit_tests $(shell rm -f $(shell find -type f -name '*.gcno'))
	$(RM) $(shell rm -f $(shell find -type f -name '*.gcda'))
	$(RM) $(shell rm -f $(shell find -type f -name '*.gcovr'))

tests_fclean: tests_clean

tests_re: tests_clean
	tests_run

.PHONY:	all clean fclean re tests_clean tests_run tests_re
