Quick Sort
-----------

O Quick Sort é um algoritmo de ordenação baseado na estratégia de "dividir para conquistar", ele seleciona um elemento como **pivô**, particiona o vetor de modo que os elementos menores que o pivô fiquem à sua esquerda e os maiores fiquem à sua direita, e então aplica recursivamente o mesmo processo às duas partições resultantes.

Exemplo de Pseudocódigo
~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python
   :linenos:

   def bubble_sort(vetor):
       n = len(vetor)
       comparacoes = 0
       trocas = 0

       for i in range(n - 1):
           trocou = False

           for j in range(n - 1 - i):
               comparacoes += 1

               if vetor[j] > vetor[j + 1]:
                   vetor[j], vetor[j + 1] = vetor[j + 1], vetor[j]
                   trocas += 1
                   trocou = True

           # Se não houve troca nesta passagem, o vetor já está ordenado
           if not trocou:
               break

       return vetor, comparacoes, trocas


   # Exemplo de uso
   if __name__ == "__main__":
       dados = [5, 3, 8, 1, 9, 2]

       ordenado, num_comparacoes, num_trocas = bubble_sort(dados)

       print("Vetor ordenado:", ordenado)
       print("Número de comparações:", num_comparacoes)
       print("Número de trocas:", num_trocas)

Lógica de Ordenação
~~~~~~~~~~~~~~~~~~~~

- Escolhe um elemento do vetor como pivô (pode ser o primeiro, o último, o elemento central ou um valor aleatório, dependendo da estratégia adotada);
- Particiona o vetor: percorre os elementos, colocando os menores que o pivô de um lado e os maiores do outro;
- Posiciona o pivô em sua posição final correta (entre as duas partições);
- Aplica recursivamente o mesmo processo às sublistas à esquerda e à direita do pivô;
- A recursão termina quando as sublistas possuem 0 ou 1 elemento, que já estão, por definição, ordenadas.

Complexidade Melhor Caso
~~~~~~~~~~~~~~~~~~~~~~~~

**O(n log n)** — ocorre quando o pivô escolhido divide consistentemente o vetor em duas partições de tamanhos aproximadamente iguais a cada partição.

Complexidade Médio Caso
~~~~~~~~~~~~~~~~~~~~~~~~

**O(n log n)** — na prática, mesmo com escolhas de pivô não ideais, o algoritmo tende a se comportar de forma próxima ao caso ideal, o que o torna, em média, um dos algoritmos de ordenação mais rápidos.

Complexidade Pior Caso
~~~~~~~~~~~~~~~~~~~~~~

**O(n²)** — ocorre quando o pivô escolhido é sistematicamente o menor ou o maior elemento da partição (por exemplo, ao ordenar um vetor já ordenado usando sempre o primeiro elemento como pivô), gerando partições extremamente desbalanceadas.

Vantagens e Limitações:
~~~~~~~~~~~~~~~~~~~~~~

Vantagens:
  - Excelente desempenho médio, geralmente superior a outros algoritmos O(n log n) na prática, devido a fatores como localidade de referência e baixo overhead por comparação;
  - Ordenação in-place (não exige memória auxiliar significativa, ao contrário do Merge Sort);
  - Amplamente utilizado e otimizado em bibliotecas padrão de diversas linguagens.

Limitações:





Sobre o uso do algoritmo:
~~~~~~~~~~~~~~~~~~~~~~~~~

