# Avaliação prática: Clusterização de Vinhos com PCA e K-Means


**Importação das bibliotecas necessárias:**   
   - Panda: para manipulação e estruturação dos dados em formato de DataFrame.
   - matplotlib.pyplot: Visualização gráfica dos resultados.
   - scikit-learn: Carregamento do conjuntos de dados, pré-processamento (StandardScaler), redução de dimensionalidade (PCA) e algoritmo de agrupamento (KMeans).
   - seaborn: Interface mais estética e de alto nível para o matplotlib.
     
**1. Carregar e Preparar os Dados**

   - O dataset Wine é carregado. Esse dataset contém atributos químicos de diferentes vinhos, oriundos de três cultivares distintas (variáveis de classe).
   - Guardamos a matriz de características (atributos preditores), composta por 13 variáveis numéricas na variável **X**.
   - E os rótulos verdadeiros das classes (0, 1 ou 2), que correspondem às categorias reais dos vinhos na variável **y_true**.
   
O método StandardScaler transforma os dados de modo que cada variável tenha média 0 e desvio padrão 1.
Essa etapa é fundamental antes da aplicação do PCA e do K-Means, pois ambos são sensíveis à escala dos atributos.

**2. Aplicar o PCA**
  - O Principal Component Analysis — PCA é uma técnica de redução de dimensionalidade.
  - O objetivo é projetar os dados em um novo espaço de menor dimensão (neste caso, duas dimensões), preservando a maior variância possível.
  - Ao manter apenas os dois primeiros componentes, preserva-se a maior parte da variabilidade original, mas em um espaço bidimensional que facilita a visualização gráfica e a interpretação.
  - O calculo da variância indica a proporção da informação original mantida nessa nova representação reduzida.
    
**3. Aplicar o K-Means nos Dados Reduzidos**
  - Com os dados já reduzidos a duas dimensões, aplica-se o algoritmo K-Means, que é um método de aprendizado não supervisionado utilizado para clusterização para agrupar observações semelhantes entre si com base em medidas de distância
  - O algoritmo é configurado para identificar três grupos, pois o conjunto de dados original contém três classes de vinhos.
  - O K-Means inicializa três centróides, associa cada ponto de dado ao centróide mais próximo e recalcula repetidamente as posições dos centróides até que as distâncias dentro de cada grupo sejam minimizadas.
  - O resultado é um rótulo de cluster atribuído a cada amostra, representando o grupo ao qual ela pertence.

**4. Visualizar os Resultados**

  -  O primeiro gráfico exibe os clusters encontrados pelo K-Means no espaço das duas componentes principais, com cores distintas para cada grupo e marcações especiais para os centróides, indicando o ponto médio de cada cluster.
  -  O segundo gráfico mostra as classes reais dos vinhos (provenientes dos rótulos originais) representadas nas mesmas duas dimensões obtidas pelo PCA.
  -  A visualização comparativa permite avaliar visualmente o desempenho do algoritmo de clusterização e verificar o quanto os agrupamentos formados de maneira não supervisionada se aproximam das categorias reais dos vinhos.

A combinação de PCA e K-Means é amplamente utilizada, pois permite identificar padrões e estruturas ocultas em conjuntos de dados complexos de forma eficiente e interpretável.
