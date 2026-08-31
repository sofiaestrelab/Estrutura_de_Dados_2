Bubble Sort e Quick Sort
=========================

Bubble Sort
-----------

O Bubble Sort é um algoritmo de ordenação simples que organiza os elementos de uma lista comparando pares de elementos vizinhos e trocando-os de posição quando estão fora de ordem. 
A cada passagem completa pela lista, o maior (ou menor, dependendo do critério) elemento **flutua** gradualmente até sua posição correta, de forma semelhante a uma bolha subindo à superfície.

Exemplo Código
~~~~~~~~~~~~~~

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

- Compara o elemento na posição i com o elemento na posição i+1;
- Se estiverem fora de ordem, realiza a troca (swap);
- Repete esse processo até o fim do vetor, completando uma "passagem";
- Repete as passagens até que nenhuma troca seja necessária, indicando que o vetor está ordenado;
- Uma otimização comum é usar uma flag (ex: trocou = False) para encerrar o algoritmo antecipadamente caso uma passagem completa não realize nenhuma troca.

Complexidade Melhor Caso
~~~~~~~~~~~~~~~~~~~~~~~~

Complexidade Médio Caso
~~~~~~~~~~~~~~~~~~~~~~~~

Complexidade Pior Caso
~~~~~~~~~~~~~~~~~~~~~~

