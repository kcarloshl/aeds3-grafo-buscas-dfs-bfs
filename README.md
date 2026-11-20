# Grafo com Buscas em Profundidade e Largura (AEDS III)

Trabalho da disciplina **Algoritmos e Estruturas de Dados III**, do curso de Bacharelado em Sistemas de Informação do IFMG – Campus São João Evangelista.

O programa implementa um grafo (direcionado ou não) com **matriz de adjacência**, vértices com **nome** e coordenadas, e os algoritmos de **busca em profundidade (DFS)** e **busca em largura (BFS)**, tudo por meio de um menu interativo no terminal.

## Funcionalidades

- Importar um grafo de um arquivo de texto (incluindo o nome dos vértices)
- Criar um grafo vazio com N vértices
- Exibir a matriz de adjacências
- Consultar se um vértice é adjacente a outro
- Inserir arestas (individualmente ou em conjunto) e removê-las
- Editar as coordenadas e o nome de um vértice
- Consultar o primeiro adjacente, o próximo adjacente e a lista completa de adjacentes
- Exportar o grafo para um arquivo de texto
- **Busca em Profundidade (DFS):** exibe tempo de descoberta, tempo de término e antecessor de cada vértice
- **Busca em Largura (BFS):** exibe distância, antecessor e cor de cada vértice

## Estrutura do projeto

```
.
├── src/
│   └── trabalho1AEDSIII.cpp
├── exemplos/
│   ├── grafo.txt
│   ├── grafo2.txt
│   └── grafo3.txt
├── .gitignore
└── README.md
```

## Como compilar e executar

Requisito: compilador C++ com suporte a C++11 ou superior (g++).

```bash
g++ -std=c++11 -o trabalho1AEDSIII src/trabalho1AEDSIII.cpp
./trabalho1AEDSIII        # Linux/macOS
trabalho1AEDSIII.exe      # Windows
```

## Formato do arquivo de grafo

```
direcionado=nao
10                              <- número de vértices
0 1 1 Ilha da Baleia            <- vértice, X, Y, nome (pode ter espaços)
1 50 20 Mons Agnes
...
10                              <- número de arestas
0 1 50                          <- origem, destino, peso
0 9 20
...
```

- A primeira linha é `direcionado=sim` ou `direcionado=nao`.
- O nome do vértice ocupa o resto da linha, então pode conter espaços.
- Peso `0` significa ausência de aresta.
- Em grafos não direcionados, cada aresta é gravada uma única vez ao exportar.

## Algoritmos de busca

Ambas as buscas percorrem **todos os vértices**, reiniciando a partir de qualquer vértice ainda não visitado (funciona em grafos desconexos). As cores seguem o padrão clássico: **B**ranco (não visitado), **C**inza (em processamento) e **P**reto (finalizado).

| Busca | Estrutura auxiliar | Informações exibidas |
|-------|--------------------|----------------------|
| DFS   | Recursão           | Tempo de descoberta, tempo de término, antecessor |
| BFS   | Fila (`queue`)     | Distância, antecessor, cor |

Complexidade com matriz de adjacência: **O(V²)**.

## Tecnologias

- C++ (STL: `vector`, `queue`, `fstream`, `iostream`)

## Autor

- Carlos Henrique Lima

## Disciplina

AEDS III – IFMG, Campus São João Evangelista