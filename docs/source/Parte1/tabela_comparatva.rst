Tabela Comparativa
-------------------

.. note::
  Comparação entre Bubble e Quick Sort

.. list-table::
   :width: 100%
   :widths: auto
   :header-rows: 1

   * - Característica
     - Bubble Sort
     - Quick Sort
   * - Princípio de funcionamento
     - Compara elementos adjacentes e os troca de posição quando estão fora de ordem, repetindo passagens até que o vetor esteja ordenado
     - Estratégia de divisão e conquista: escolhe um pivô, particiona o vetor em elementos menores e maiores que ele, e aplica o processo recursivamente às partições
   * - Melhor caso
     - O(n) — vetor já ordenado (com otimização de parada antecipada)
     - O(n log n) — pivô sempre divide o vetor em partições equilibradas
   * - Caso médio
     - O(n²)
     - O(n log n)
   * - Pior caso
     - O(n²) — vetor ordenado em ordem inversa
     - O(n²) — pivô sistematicamente é o menor ou maior elemento (ex: vetor já ordenado com escolha ingênua de pivô)
   * - Uso de memória
     - O(1) — ordenação in-place, sem estruturas auxiliares
     - O(log n) — espaço adicional devido à pilha de recursão (in-place, mas não livre de overhead)
   * - Vantagem principal
     - Simplicidade de implementação e compreensão
     - Excelente desempenho médio (O(n log n)), sendo um dos algoritmos mais rápidos na prática
   * - Limitação principal
     - Desempenho quadrático, inviável para grandes volumes de dados
     - Pior caso O(n²), dependente da estratégia de escolha do pivô
   * - Aplicação recomendada
     - Fins didáticos, vetores muito pequenos ou quase ordenados
     - Aplicações de propósito geral com grandes volumes de dados, onde desempenho médio é prioridade
