# karatsuba-readme
Karatsuba / Readme
[![NPM](https://img.shields.io/npm/l/react)](https://github.com/UrsulaF/karatsuba-readme/blob/main/LICENSE)
## Sobre o projeto 
Essa é uma aplicação na linguagem Python do algoritmo de Karatsuba, o qual é um método de multiplicação de eficiência relevante para números com muitos algarismos, acima de 2 casas decimais. O projeto consiste em receber a entrada de dois números e retornar sua multiplicação, sendo eles com mais de 2 casas decimais, aplicado o algotirimo de Karatsuba, além de trazer o tempo de execução do algoritmo. 


## Tecnologias utilizadas
- Python 

## Como executar o projeto
- Abra o arquivo em um jupiter notebook
- Insira dois valores números um em X e um em Y na linha 18 e 19 respectivamente 
- Rode o código

## Sobre o código
import time  // Importando a biblioteca de tempo 
initial_time = time.time() // Computa o horário em que a ação foi inciada
import math // Importando a biblioteca math 

def karat(x,y):  // definindo a função karat de y e x, variaveis do problema
    if x <= 100  or y<=100:  // adicionando a primeira condição, onde x e y menores que 100 retorna a multiplicação dos valores sem utilizar karatsuba
        return x*y
    else:
        n = max(len(str(x)),len(str(y)))  // contabilizamos as casas decimais de x e y
        n2 = n // 2  // criamos uma variavel que é a metade do número de casas, assim podemos começar a dividir em blocos o karatsuba

        a = x // 10**(n2)  // Definindo o bloco a, com a variavel x
        b = x % 10**(n2) // Definindo bloco b, com a variavel x
        c = y // 10**(n2) // Definindo bloco c, com a variavel y
        d = y % 10**(n2)  // Definindo bloco d, com a variavel y

        z0 = karat(b,d) // chamamos a função karat agora utilizando os blocos definindo uma nova variavel Z, para relacionar os blocos entre si sem repetirmos e gerando um grau de complexidade maior as variaveis a, b, c e d. 
        z1 = karat((a+b),(c+d))
        z2 = karat(a,c)

        return (z2 * 10**(2*n2)) + ((z1 - z2 - z0) * 10**(n2)) + (z0) // retornamos o resultado do karatsuba 
  x = 99999999999  // inserir aqui o primeiro número a ser multiplicado
  y = 99999999999  // inserir aqui o segundo número a ser multiplicado  
  res = karat(x,y)
  print(res)   
  print(" tempo e execução é de %s segundos " % (time.time() - initial_time)) // retorno do tempo de execução do algoritimo de karatsuba.


# Referências 
https://www.ime.usp.br/~pf/analise_de_algoritmos/aulas/karatsuba.html
https://brilliant.org/wiki/karatsuba-algorithm/
https://www.geeksforgeeks.org/karatsuba-algorithm-for-fast-multiplication-using-divide-and-conquer-algorithm/
Canal: Professor Rudini Sampaio - Projeto e Análise de Algoritmos - UFC - Algoritmo de Karatsuba (para multiplicação de números grandes) 

