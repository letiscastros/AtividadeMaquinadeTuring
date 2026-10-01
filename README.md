# Atividade Remota - Inteligência Artificial, Linguagens Formais e Automatos

Tema: Máquinas de Turing

## Sobre o projeto

Atividade remota baseada no vídeo [Akitando #86 — O Computador de Turing e Von Neumann: Por que calculadoras não são computadores?](https://akitaonrails.com/2020/10/23/akitando-86-o-computador-de-turing-e-von-neumann-por-que-calculadoras-nao-sao-computadores/).

Foi criada e simulada uma Máquina de Turing que reconhece palavras da forma **0ⁿ1ⁿ**, ou seja, palavras com a mesma quantidade de 0s e 1s, com todos os 0s antes dos 1s.

## Arquivos

- `Atividade_Maquinas_de_Turing.pdf`: documento com as respostas, a descrição da máquina, as capturas de tela e os resultados dos testes.
- `atividade.yaml`: código da máquina para o simulador.

## Como a máquina funciona

A cada rodada, a máquina apaga o primeiro 0 da esquerda e o último 1 da direita. Se a fita ficar vazia, a palavra é aceita. Se sobrar um símbolo sem par, ou os símbolos estiverem fora de ordem, não há transição possível e a palavra é rejeitada.

| Estado | Função |
|---|---|
| q0 | Apaga o 0 da esquerda e vai para q1. Se encontra branco, aceita. |
| q1 | Percorre a palavra para a direita até o fim e recua para q2. |
| q2 | Apaga o 1 da direita e vai para q3. |
| q3 | Volta para a esquerda até o início e retorna a q0. |
| accept | Estado de aceitação. |

## Como executar

1. Acesse o simulador: <https://turingmachine.io/>
2. Cole o conteúdo de `atividade.yaml` no editor.
3. Troque a linha `input` pela palavra desejada.
4. Clique em **Load Machine** e execute com **Run** ou **Step**.

## Testes realizados

| Teste | Entrada | Resultado esperado | Resultado obtido |
|---|---|---|---|
| 1 | 0011 | ACEITA | ACEITA |
| 2 | 000111 | ACEITA | ACEITA |
| 3 | 00111 | REJEITA | REJEITA |

Por Letícia Castro de Souza
