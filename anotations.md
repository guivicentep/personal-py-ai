# Tipos de aprendizado
  - Supervisionado: Modelos são treinados usando um conjunto de dados rotulado, aprendendo a mapear entradas para as saídas esperadas
  - Não supervisionado: Modelos exploram dados não rotulados para identificar padrões ou estruturas subjacentes, como agrupamentos, associações ou redução de dimensionalidade
  - Semi supervisionado: Combina dados rotulados e não rotulados para melhorar o desempenho do modelo, geralmente utilizando a estrutura não rotulada para aprimorar o aprendizado supervisionado
  - Por reforço: Agentes aprendem a tomar ações em um ambiente para maximizar algum tipo de recompensa acumulativa, através de tentativa e erro

# Tipos de algoritmo
  - Supervisionados: 
    - Regressão
    - Classificação
  - Não supervisionados
    - Agrupamento
    - Redução da Dimensionalidade
    - Associação
  - Por reforço
    - Valor
    - Política
    - Ator crítico
  - Aprendizado profundo:
    - Redes convolucionais
    - Redes recorrentes
    - GANs
    - Transformers
  - Computação natural:
    - Genéticos
    - Sistemas Imunológicos Artificiais
    - Otimização por colônias ou enxame
    - Computação quântica

# A maldição da dimensionalidade
  - Denominada pelo matemático Bellman em 1957. Diz que a quantidade de dados que você precisa, para alcançar o conhecimento desejado, impacta exponencialmente o número de atributos necessários. Em resumo refere-se a uma série de desafios que surgem ao trabalhar com dados de alta dimensão. A dimensão de um conjunto de dados corresponde ao número de características existentes em um conjunto de dados. Podemos lidar com isso de 2 principais maneiras, a primeira seria a seleção de features, que seria que, com base nas características do seu conjunto de dados, apresentar as features mais importantes, ou seja, aquelas que vão auxiliar mais na hora de realizar a tarefa que desejamos. E temos também a redução da dimensionalidade, que basicamente é, com base no conjunto de dados, aplicar um algoritmo que combina 2 ou mais features, que vai representar todas as selecionadas.

# Engenharia e seleção de Features
  - A engenharia de features é uma etapa fundamental no processo de desenvolvimento de modelos de machine learning. Refere-se ao processo de selecionar, extrair, transformar ou criar novas variáveis (features) a partir dos dados brutos para melhorar o desempenho dos modelos. Uma boa engenharia de features pode tornar um modelo mais preciso, eficiente e interpretável. A engenharia de features é um processo iterativo. Os especialistas de IA/ML geralmente começam com um conjunto inicial de features e então testam diferentes combinações de features para determinar a melhor configuração para o modelo
  - Seleção: Processo de selecionar um subconjunto de features extraídas. A pontuação de importância da feature e a matriz de correlação podem ser fatores na seleção das features mais relevantes para o treinamento do modelo.
  - Transformação: Pode incluir normalizações, codificação de variáveis categóricas ou transformações matemáticas. ALém disso tratar features ausentes ou features que não são válidas
  - Criação: Criar novas features a partir dos dados existentes, usando técnicas como combinação de variáveis, decomposições e cálculos matemáticos
  - Extração: Reduzir a quantidade de dados a ser processada usando técnicas de redução de dimensionalidade. Diferente de um processo de transformação, é utilizado um modelo de ML para este processo

# Overfitting e Underfitting
  - Underfiting: Ocorre quando um modelo de aprendizado de máquina é muito simples para aprender a relação entre as variáveis nos dados de treinamento. Isso pode resultar em um modelo que não é capaz de fazer previsões precisas para dados novos.
  - Overfitting: Ocorre quando um modelo de aprendizado de máquina aprende a relação entre as variáveis nos dados de treinamento com muito detalhe, incluindo o ruído nos dados. Isso pode resultar em um modelo que é capaz de fazer previsões precisas para os dados de treinamento, mas não é capaz de generalizar para dados novos.
  - Como lidar?
    - Regularização
    - Ensemble de Modelos
    - Redução de Dimensionalidade
    - Validação Cruzada

# Trade-off entre Viés e Variância
 - O Trade-off entre viés e variância descreve a relação entre a capacidade de um modelo de aprender a partir de dados e sua capacidade de generalizar para dados novos. 
 - Viés e o erro sistemático que um modelo comete a partir de dados. Ele ocorre quando o modelo não é capaz de aprender a relação real entre as variáveis
 - Variância é a variabilidade dos resultados de um modelo ao ser aplicado a diferentes conjuntos de dados. Ele ocorre quando o modelo é muito complexo ou quando os dados de treinamento são insuficientes

# Validação de Modelos
 - Hold-out: Separar, de forma aleatória, uma parcela dos dados para testar o modelo, e utilizar o restante para treinamento. Ou seja, os testes são feitos com dados que o modelo não viu anteriormente. Ideal para conjuntos pequenos e quando há restrição no tempo de treinamento.
 - K-Fold: Na validação cruzada, o dataset é dividido aleatoriamente em "K" grupos e a cada iteração, um grupo é selecionado como conjunto de teste (validação) e os demais para treinamento. No final, teremos a métrica de cada iteração e quando estamos satisfeitos com a performance, aplicamos no conjunto final de testes. Ideal para grandes conjuntos e necessidade de mais precisão.
 - Stratified K-Fold: Segue o mesmo conceito do K-Fold, mas aplicado a problemas de classificação, onde queremos manter a distribuição dos dados entre as classes em cada Fold, tanto no treinamento quanto na Validação e Teste. Ideal para datasets desbalanceados.

# Ensemble de modelos
 - É uma técnica de aprendizado de máquina que combina as previsões de vários modelos para melhorar o desempenho geral. Essa técnica é baseada no princípio de que a combinação de modelos pode ajudar a reduzir o viés e a variância, o que pode levar a previsões mais precisas. 
 - Essas técnicas são frequentemente usadas em competições de aprendizado de máquina, onde a combinação de modelos pode dar uma vantagem crítica. No entanto, vale a pena notar que os ensembles podem aumentar a complexidade e o tempo de treinamento, potanto, é sempre bom considerar o trade-off entre performance e complexidade
 - Tipos de ensemble:
  - Bagging (Boostrap Aggregating): Treina vários modelos em subconjuntos aleatórios dos dados de treinamento. O modelo final é a combinação das previsões de todos os modelos treinados. Ex: Random Forest
  - Boosting: Treina modelos sequencialmente, onde cada novo modelo tenta corrigir os erros do modelo anterior. Ex: LightGBM e XGBoost
  - Stacking: Combina as previsões de vários modelos usando um modelo de meta-aprendizado. O modelo de meta-aprendizado é treinado para aprender como combinar as previsões dos modelos base.
  - Voting: Combina as previsões de vários modelos usando um processo de votação. O modelo final é o que recebe mais votos.