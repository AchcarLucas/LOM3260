---
title: Indexação e fatiamento
parent: tematwo
nav_order: 5
status: green
tags: [slicing, indexing, fatiamento, indexação, índice, índices, elemento, tupla, list, dict, string, negativo]
timestamp: 07/06/20
---

Como escolher e manipular partes de uma string ou lista usando indexação (*indexing*) e fatiamento (*slicing*)
{: .lead }

Quase todos os comandos que veremos a seguir funcionam para objetos do tipo string, lista e tupla. Quando não for o caso, deixaremos indicado.

## Indexing

**Indexing** é a maneira pela qual nos referimos a um elemento de uma lista, string ou tupla. Por exemplo, se temos uma lista `L = [1, 8, 'EEL', 5.43]`, cada um dos elementos tem por **índice** um inteiro, começando em zero e sequencialmente aumentando de uma unidade até o último elemento. O primeiro elemento da lista `L` é indicado por `L[0]`, o segundo por `L[1]`, e assim por diante. Acompanhe:
```python
L = [1, 8, 'EEL', 5.43]
nL = len(L)
for i in range(nL):
  print(L[i])
```
Esse código vai imprimir, um a um, todos os elementos de `L`. Lembre que `len(L)` fornece o tamanho (nesse caso, o número de elementos) de `L`, assim como, se `s` é uma string, `len(s)` fornece o número de caracteres de `s` (incluindo possíveis espaços em branco). Mas repare que o código acima poderia ser simplificado fazendo uso das propriedades do operador `in`, já visto anteriormente: 
```python
L = [1, 8, 'EEL', 5.43]
for x in L:
  print(x)
```
Nesse caso, nem precisamos saber o tamanho da lista!

Na lição anterior, vimos que listas são editáveis, ou seja, é possível alterar qualquer um de seus elementos. Isso é feito usando indexação. Por exemplo, usando a mesma lista `L=[1, 8, 'EEL', 5.43]`, se quisermos alterar o terceiro elemento (com índice 2, não se esqueça!) para  `Demar`, podemos simplesmente fazer `L[2] = 'Demar'`. A lista entãlo passa a ser `L=[1, 8, 'Demar', 5.43]`.

:warning: Não é possível usar indexing para alterar valores de uma string ou de uma tupla! Esses são tipos imutáveis de objetos.
{: .lead .alert .alert-warning}

É possível também adicionar e eliminar elementos de uma lista. Consulte a ajuda sobre os comandos `append` e `del` em qualquer referência sobre python. Nesse curso, não vamos precisar desses comandos, já que migraremos em breve para outros tipos de dados: os **arrays** que o módulo `numpy` fornece, muito mais poderosos que listas.

### O que são índices negativos?

Caso você queira o último elemento, a convenção é usar **índices negativos**: `L[-1]` é o último elemento de `L`, `L[-2]` o penúltimo, e assim por diante. Veja que, com isso, você não precisa necessariamente conhecer o tamanho de `L` para obter o seu último (ou qualquer outro) elemento.


## Slicing (fatiamento)

Se você entendeu como funciona o comando `range()`, vai entender o fatiamento de listas, tuplas e strings, pois são muito parecidos. A sintaxe é
```python
f = L[start:stop:step]
```
em que `L` é uma string, lista ou tupla e `f` é uma fatia de `L` (ou seja, uma parte de `L`) a partir do elemento `start` até o elemento `stop`, mas **SEM INCLUIR `stop`**, com um passo `step`.

Se `start` não é fornecido, ele é por padrão `0`, ou seja, o primeiro elemento. Se stop não é fornecido, ele é por padrão o último elemento, ou seja, `len(L)`. O `step` é opcional e, se não for fornecido, vale `1` por padrão.

Valores negativos para `start` e `stop` são aceitos, de forma parecida com a que vimos para a indexação. Um `step` negativo também é possível, assim como no caso do comando `range`.

Vejamos alguns exemplos:
```python
L = 'Eu sou uma string'

# primeira palavra (Eu)
print(L[:2])

# segunda palavra:
print(L[3:6])

# última palavra:
print(L[-6:])

# teste: os seguintes comandos imprimem?
print(L[-6::2])
print(L[:])
print(L[::])
print(L[::-1])
```

