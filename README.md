# Agente de Otimização de Entregas — Grupo 13

Agente inteligente para encontrar a melhor rota de entrega para um
motoboy na região de Aldeota, Fortaleza, utilizando algoritmos de
busca em grafos e dados reais do OpenStreetMap.

## Sobre o projeto

Este projeto foi desenvolvido para a disciplina MDC050 — Inteligência
Artificial, da turma ENGCDM2B.

O objetivo é modelar o problema de entrega como um problema de busca
em espaço de estados e comparar diferentes algoritmos de busca para
encontrar rotas entre restaurantes e clientes.

### Equipe

- Vitor Carvalho de Santana
- Henri de Macedo Bezerra — líder
- Pedro Augusto Machado Cardoso

## Objetivo

Encontrar uma rota de menor distância entre um restaurante e um cliente
em uma rede viária real da região de Aldeota, em Fortaleza.

O agente utiliza um grafo direcionado baseado em dados do OpenStreetMap,
respeitando o sentido das vias.

## Tecnologias utilizadas

- Python
- NetworkX
- OSMnx
- NumPy
- Pandas
- Matplotlib
- OpenStreetMap

## Algoritmos

Foram implementados e comparados três algoritmos:

### Busca em Largura — BFS

A BFS minimiza o número de cruzamentos percorridos, mas não considera
a distância das vias.

### Busca de Custo Uniforme — UCS

A UCS expande o estado com menor custo acumulado e encontra a rota de
menor distância quando os custos das arestas são positivos.

### A*

O A* utiliza uma heurística baseada na distância geodésica entre o
cruzamento atual e o destino.

A heurística utilizada é baseada na fórmula de Haversine.

## Área de estudo

A primeira etapa utiliza a região de Aldeota, em Fortaleza, Ceará.

O grafo é obtido a partir do OpenStreetMap utilizando a biblioteca OSMnx.

Foram utilizados três tamanhos de mapa:

1. Pequeno — vias principais da Aldeota;
2. Médio — todas as vias trafegáveis da Aldeota;
3. Grande — região com raio de aproximadamente 3 km a partir do
   centro da Aldeota.

## Experimentos

Para cada tamanho de mapa foram realizadas 20 entregas:

- 5 restaurantes;
- 4 clientes aleatórios por restaurante;
- 3 algoritmos de busca;
- semente aleatória fixa igual a 13.

Foram avaliadas:

- distância da rota;
- número de nós expandidos;
- tempo de execução.

## Resultados

Os experimentos mostraram que UCS e A* encontraram a mesma distância
de rota, enquanto o A* apresentou uma quantidade significativamente
menor de nós expandidos.

A BFS, por outro lado, minimiza o número de cruzamentos e pode produzir
rotas maiores em distância.

## Estrutura do projeto

```text
├── notebooks/
├── src/
├── data/
├── results/
└── docs/
