#
# UFRGS - Compiladores B - Marcelo Johann - 2009/2 - Etapa 1
#
# Makefile for three compiler calls
# Read the comments on Makefile2. All of them apply here too.
# But now the hash table is compiled in a separate gcc call
# Therefore, there must be a header of it to be included in scanner.l
#

etapa2: lex.yy.c main.o hash.o y.tab.c
	gcc -Wall -o etapa2 lex.yy.c main.o hash.o

main.o: main.c
	gcc -c main.c

hash.o: hash.c
	gcc -c hash.c

lex.yy.c: scanner.l y.tab.o
	flex --header-file=lex.yy.h scanner.l

y.tab.c: parser.y
	yacc -d parser.y

clean:
	rm *.o lex.yy.c y.tab.c y.tab.h etapa2
