# Soluções para o Problema da Mochila Binária

## Comparação entre Estratégia Gulosa e Transformar para Conquistar

Este repositório é um **fork** de um projeto acadêmico que implementa e compara duas abordagens para o **Problema da Mochila Binária (0–1 Knapsack)**:

1. **Estratégia gulosa clássica sem pré-ordenação** (busca iterativa pelo melhor custo-benefício a cada passo)
2. **Estratégia Transformar para Conquistar (TC)** com **ordenação inicial** dos itens por custo-benefício usando **Quick Sort**

O objetivo deste fork é **registrar minha participação no desenvolvimento**, organizar a documentação do projeto e manter uma versão pública vinculada ao meu perfil.

---

## Autores

* Gabriel Lenser
* Luiz E. O. de Oliveira
* Pedro H. O. Berti
* Colegiado de Ciência da Computação – UNIOESTE (Campus Cascavel)

---

## Resumo do Projeto

O trabalho avalia empiricamente o desempenho de duas estratégias para resolver o problema da mochila binária em instâncias de diferentes tamanhos. Foram implementados algoritmos em **linguagem C** e executados testes em **15 instâncias**, variando de **10 a 5000 itens**.

Resultados gerais observados no estudo:

* A abordagem **gulosa sem pré-ordenação** apresenta complexidade **O(n²)** e tempos que crescem conforme o número de itens.
* A abordagem **Transformar para Conquistar (TC)**, utilizando **Quick Sort** na fase inicial, apresenta complexidade **O(n log n)** e manteve **tempos muito baixos e estáveis** mesmo em instâncias grandes.

---

## Problema da Mochila Binária

Dado:

* Uma capacidade máxima `C`
* `n` itens, cada um com **valor** `v[i]` e **peso** `w[i]`

Objetivo:

* Maximizar a soma dos valores dos itens escolhidos
* Sem ultrapassar a capacidade máxima da mochila
* Cada item pode ser escolhido **no máximo uma vez** (0 ou 1)

---

## Estratégias Implementadas

### Modo 1 — Guloso sem pré-ordenação (O(n²))

A cada iteração, o algoritmo percorre todos os itens ainda não processados e seleciona o item com maior razão `valor/peso`.
Como essa busca é repetida várias vezes sem ordenar previamente, a implementação resulta em comportamento quadrático.

### Modo 2 — Transformar para Conquistar (O(n log n))

O problema é “transformado” com uma etapa de pré-processamento:

1. Ordena os itens por `valor/peso` em ordem decrescente usando **Quick Sort**
2. Percorre os itens ordenados e seleciona sequencialmente os que cabem na capacidade restante

A complexidade é dominada pela ordenação: **O(n log n)**.

---

## Metodologia dos Testes

* Linguagem: **C**
* Compilação: **GCC** (sem flags de otimização)
* Execuções: **6 vezes por configuração**, com **a primeira descartada**
* Resultado final: **média das 5 execuções restantes**
* Instâncias testadas: 15 arquivos (Mochila10 até Mochila5000)

Formato das instâncias de entrada:

1. Capacidade da mochila
2. Lista de valores (benefícios)
3. Lista de pesos (custos)


---

## Resultados

Os testes mostraram que:

* A estratégia **Transformar para Conquistar (modo 2)** foi **mais rápida em todas as instâncias testadas**.
* A diferença cresce conforme o número de itens aumenta, confirmando a vantagem prática de uma abordagem **O(n log n)** sobre uma **O(n²)** para instâncias maiores.


---

## Minha Participação

Participei do trabalho no contexto acadêmico, contribuindo com etapas de implementação e análise, incluindo:

* desenvolvimento/validação dos algoritmos
* organização de testes e medições de tempo
* análise assintótica e comparação de desempenho
* documentação do estudo e resultados

Este fork tem como objetivo documentar oficialmente minha participação e manter o projeto acessível no meu perfil.

---

## Referências

Abidin, S. (2017). *Greedy approach for optimizing 0-1 knapsack problem.*
Brun, A. L. (2025). *Transformar para conquistar. Aula 14 – Projeto e Análise de Algoritmos.*
Durmuş, B. et al. (2019). *Comparison of classic and greedy heuristic algorithm results in integer programming: Knapsack problems.*
Folador, J. P. et al. (2014). *Aplicativo para análise comparativa do comportamento de algoritmos de ordenação.*
Pradhan, T. et al. (2014). *Solving the 0–1 knapsack problem using genetic algorithm and rough set theory.*
Wang, Y. (2023). *Review on greedy algorithm.*


