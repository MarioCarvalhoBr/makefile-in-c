############################# Test Makefile ##########################

# Definição de variáveis
CC=gcc
CFLAGS=-W -Wall -ansi -pedantic
EXEC=test
OBJ=test.o

## all: É o nome das regras a serem executadas.
all: $(EXEC)
	@echo "Compilação executada"

## test: test.o: Pode ser interpretado com arquivo_de_destino: arquivo_de_origem
test: $(OBJ)
	# O compilador faz a ligação entre os dois objetos
	@echo "Linkando os arquivos"
	$(CC) -o $@ $^

## Comando final para compilação
%.o: %.c
	@echo "Compilando os arquivos"
	$(CC) -o $@ -c $< $(CFLAGS)

## Resolve comflitos
.PHONY: clean mrproper

## clean: Apaga os arquivos intermediários. Escrever no console make clean
clean: 
	rm -rf *.o
	@echo "Apagando arquivos temporários" 

## mrproper: Apaga tudo o que deve ser modificado. Escrever no console make mrproper
mrproper: clean
	rm -rf $(EXEC)
	@echo "Limpadando arquivos gerados"

## Sempre identar com o botão TAB e não com espaços.
############################# Makefile ##########################