Experimento de Ordenação
========================

Programa de teste com Bubble e Quick Sort
------------------------------------------

.. code-block:: python
   :linenos:

   import random
   import time
   import copy

   def bubble_sort(vetor):
       v = vetor[:]
       n = len(v)
       comparacoes = 0
       trocas = 0
       for i in range(n - 1):
           trocou = False
           for j in range(n - 1 - i):
               comparacoes += 1
               if v[j] > v[j + 1]:
                   v[j], v[j + 1] = v[j + 1], v[j]
                   trocas += 1
                   trocou = True
           if not trocou:
               break
       return v, comparacoes, trocas


   def quick_sort(vetor):
       v = vetor[:]
       contadores = {"comparacoes": 0, "trocas": 0}

       def particionar(inicio, fim):
           pivo = v[fim]
           i = inicio - 1
           for j in range(inicio, fim):
               contadores["comparacoes"] += 1
               if v[j] <= pivo:
                   i += 1
                   v[i], v[j] = v[j], v[i]
                   contadores["trocas"] += 1
           v[i + 1], v[fim] = v[fim], v[i + 1]
           contadores["trocas"] += 1
           return i + 1

       def _quick_sort(inicio, fim):
           if inicio < fim:
               p = particionar(inicio, fim)
               _quick_sort(inicio, p - 1)
               _quick_sort(p + 1, fim)

       _quick_sort(0, len(v) - 1)
       return v, contadores["comparacoes"], contadores["trocas"]


   random.seed(42)
   tamanhos = [10, 20, 1000]
   resultados = []

   for n in tamanhos:
       array_original = [random.randint(1, 10000) for _ in range(n)]
       copia1 = copy.deepcopy(array_original)   # cópia para o Bubble Sort
       copia2 = copy.deepcopy(array_original)   # cópia para o Quick Sort

       inicio_b = time.perf_counter()
       ordenado_b, comp_b, troc_b = bubble_sort(copia1)
       tempo_b = time.perf_counter() - inicio_b

       inicio_q = time.perf_counter()
       ordenado_q, comp_q, troc_q = quick_sort(copia2)
       tempo_q = time.perf_counter() - inicio_q

       # Garante que ambos os algoritmos chegaram ao mesmo resultado
       assert ordenado_b == ordenado_q == sorted(array_original)

       resultados.append({
           "tamanho": n,
           "bubble_comp": comp_b, "bubble_troc": troc_b, "bubble_tempo": tempo_b,
           "quick_comp": comp_q, "quick_troc": troc_q, "quick_tempo": tempo_q,
       })

   for r in resultados:
       print(r)

Perguntas sobre o programa:
---------------------------

**a)** Qual algoritmo realizou menos operações para 10 elementos?

**b)** O comportamento permaneceu igual para 20 elementos?

**c)** O que aconteceu quando o tamanho aumentou para 1.000 elementos?

**d)** Qual algoritmo apresentou maior crescimento da quantidade de operações?

**e)** Os resultados experimentais são coerentes com as complexidades teóricas estudadas?

**f)** Em qual situação você escolheria Bubble Sort?

**g)** Em qual situação você escolheria Quick Sort?
