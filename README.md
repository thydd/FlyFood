# 🚁 Algoritmo de Força Bruta com Backtracking para o Problema da Menor Rota

Este projeto implementa um algoritmo de **backtracking** otimizado com **memoização** para encontrar a menor rota que visita todos os pontos de interesse a partir de uma origem, retornando ao ponto inicial. As distâncias são calculadas usando a **distância de Manhattan**, ideal para ambientes com movimentação em grade (como mapas de drones ou robôs em malhas retangulares).

## 🗺️ Entrada

A entrada do algoritmo é um arquivo chamado `matriz.txt`, contendo uma matriz representando o ambiente:

- `'R'`: ponto de origem.
- `'0'`: célula vazia (sem interesse).
- Letras ou números diferentes de zero: pontos a serem visitados.

### Exemplo de `matriz.txt`:

```
4 4
R 0 0 A
0 0 B 0
C 0 0 0
0 0 D 0
```

Nesse exemplo, o ponto de origem está no canto superior esquerdo e há 4 pontos de interesse: A, B, C e D.

## 🧮 Funcionamento

O algoritmo usa **backtracking** para explorar todas as permutações possíveis de visita aos pontos, com **poda de caminhos subótimos** baseada em:

- Distância atual comparada à melhor distância encontrada.
- Estados já visitados com menor custo (memoização).

### Distância utilizada:
A distância entre dois pontos `x = (x1, y1)` e `y = (x2, y2)` é:
```
|x1 - x2| + |y1 - y2|
```

## ⚙️ Estrutura Principal

- `ler_matriz(arquivo)`: Lê o arquivo e retorna a posição da origem e dos pontos de interesse.
- `distancia(x, y)`: Calcula a distância de Manhattan.
- `backtracking(...)`: Função recursiva que percorre todas as combinações de caminhos.
- `menor_rota()`: Função principal que executa a busca e imprime o melhor caminho encontrado.

## 🧠 Saída

Ao final da execução, será impresso:

```
[sequência de pontos visitados]
Distância em Dronômetros: [valor mínimo encontrado]
```

### Exemplo de saída:

```
A B D C 
Distância em Dronômetros: 18
```

## ▶️ Como executar

Tenha o Python 3 instalado. Salve a matriz no arquivo `matriz.txt` e execute:

```bash
python nome_do_arquivo.py
```

## 🚀 Melhorias possíveis

- Implementar heurísticas como A* ou algoritmos aproximativos para instâncias maiores.
- Adicionar suporte para obstáculos ou zonas proibidas.
- Visualização gráfica do trajeto.

## 📄 Licença

Código livre para fins acadêmicos e educacionais.