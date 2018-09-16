# Makefile in C/C++

# Exemplo de teste
### Passo a passo para usar o porjeto de teste.

## 1 - Baixando o projeto
Operação para baixar o projeto. É importante ter o Git instalado.
```bash
    $ git clone https://github.com/MarioDeAraujoCarvalho/makefile-in-c.git
```
## 2 º - Localizar a pasta e entrar
Procure a pasta no gerenciador de arquivos
```bash
    $ cd example
```
## 3 º - Executar o MAKE
Faz todo o processo de criação dos arquivos a serem executados
```bash
    $ make
    $ ./test
```
## 3 º - Executar o clean
Apaga os arquivos intermediários.
```bash
    $ make clean
```
## 4 º - Executar o mrproper
Apaga tudo o que deve ser modificado
```bash
    $ make mrproper
```
# Criando o seu próprio Makefile
### Descrição da utilização do Makefile na linguagem C/C++

<pre>
############################# Test Makefile ##########################

# Definição de variáveis
CC=gcc
CFLAGS=-W -Wall -ansi -pedantic
EXEC=test
OBJ=test.o

## all: É o nome das regras a serem executadas.
all: $(EXEC)
	@echo "Compilação executada"

## Pode ser interpretado com arquivo_de_destino: arquivo_de_origem
test: $(OBJ)
	@echo "Linkando os arquivos"
	$(CC) -o $@ $^

## Comando final para compilação
%.o: %.c
	@echo "Compilando os arquivos"
	$(CC) -o $@ -c $(CFLAGS)

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
</pre>