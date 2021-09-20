# Ilustração das contribuições dos artigos

What is the context? Which Research Question is it tackling? What is the method? What are the results? What are its limitations?

* Steel Surface Defect Diagnostics Using Deep Convolutional Neural Network and Class Activation Map
  * O artigo pretende resolver o problema de classificação de defeitos em superfície de aço
  * A detecção do local e o tipo da falha no aço
  * Ele tenta criar um mapa de ativação com o sistema da rede VGG-NET para obter o local da falha e o tipo da falha
  * Utiliza uma rede de aprendizado profundo, portanto necessita de bastante treino e de dados para tal

* Recognition Of Surface Defects On Steel Sheet Using Transfer Learning
  * Reconhecer defeitos no aço utilizando transferência de aprendizado
  * Tenta entender se é possível utilizar a técnica de transferência de aprendizado em uma rede neural profunda para a detecção de falhas no aço
  * Utilizou-se várias técnicas de aumento de dados, como ruído e transformações, para poder utilizar uma rede neural já consagrada e técnicas de inicialização diferenciadas para a parte que ainda será treinada da rede
  * Por ser uma rede neural, mesmo que pegue bem pesado no quesito de aumento de dados, ainda precisa de uma quantidade significativa de dados para treino, com cercade de 10 imagens por classe

* Deep Convolution Neural Network Approach for Defect Inspection of Textured Surfaces
  * Utiliza a técnica de rede neural convolucional profunda para detectar defeitos em superfícies texturizadas
  * Pergunta-se a possibilidade de utilizar, no meio de produção, técnias de rede neural para detectar os mais diversos defeitos em diferentes superfícies
  * Treinou-se uma rede neural com imagens de tecido com defeito e tecidos sem defeitos e obteve uma acurácia significativa
  * Apesar de utilizar uma rede neural, o artigo apresentou uma carência de estudo e propõe maiores estudos para poderem aplicar a técnica em um cenário real

* TLU-Net: A Deep Learning Approach for Automatic Steel Surface Defect Detection
  * Detecção automática de defeitos na superfície do aço
  * Tenta desenvolver a usabilidade da rede U-NET para a detecção de falhas na superfície de aço
  * Utiliza a arquitetura U-Net em um conjunto de dados de imagens com defeitos e imagens sem defeitos, e tenta desenvolver a diferença entre a arquitetura sendo inicializada com valores aleatórios, e valores pré-treinados com imagens da ImageNet
  * Demonstrou uma diferença considerável entre a inicialização aleatória e pré-treinada porém em defeitos mais complexos a detecção foi mais limitada

* Unsupervised Surface Defect Detection Using Deep Autoencoders and Data Augmentation
  * O contexto é a utilização de aumento de dados e utilização de autocodificadores profundos para detecção não supervisionada de falhas de superfície
  * O artigo tenta buscar a diferença entre esse método e os métodos feitos à mão para a detecção de defeitos
  * A metodologia dispõe da segmentação de uma imagem maior que passa para uma rede que extrai características e então essas características são comparadas utilizando uma rede siamesa
  * A grande limitação vêm da rede de extração de características que tem uma dimensão de entrada limitada, que faz com que a imagem semgmentada não detecte os defeitos de forma mais ampla

* Classification of surface defects on steel sheet using convolutional neural networks
  * Classificação do defeitos de superfície na superfície do aço utilizando redes neurais convolucionais
  * O artigo busca qual a eficiência de relizar a detecção de falhas na superfície do aço utilizando de redes convolucionais
  * Utiliza-se várias técnicas de aumento de dados, além do redimensionamento das dimensões de entrada para tentar encontrar o modelo mais eficiente para as detecções
  * Conseguiu encontrar que é mais fácil treinar redes neurais para imagens menores, e que a grande limitação é justamente ter imagens menores para a classificação, até por que, as vezes, com a segmentação da imagem, o modelo não consegue obter um contexto amplo, e em outros problemas, pode acabar não conseguindo ter uma classicação muito clara

* Deep Learning-Based Defect Detection System in Steel Sheet Surfaces
  * Detecção de falhas em folhas de metal, localizando e classficando as falhas
  * Busca desenvolver a utilização da rede U-NET e Deep Residual U-NET para resolver o problema de classificação, e busca quem é a melhor para tal
  * Utiliza-se imagens bastante grandes para o estudo, e várias imagens com defeitos e imagens sem defeitos, as redes conseguem segmentar as imagens, e delimitar a área com defeito, além de classificar qual o defeito
  * A acurácia da rede U-NET é menor que a da Deep Residual U-NET, com acurácias de 0,543 e 0,731 respectivamente, mas demonstrou que acurácia é limitada para a delimitação do local onde está o defeito, o que demonstra que é necessário mais estudos na área


# Resumos dos artigos

## 1. Steel Surface Defect Diagnostics Using Deep Convolutional Neural Network and Class Activation Map

O artigo propõe a utilização de uma rede neural convolucional e um mapa de ativação de classe com um sistema de visão computacional para resolver o problema de detecção de falhas nas superfície do aço. Com isso, ele realiza a comparação do trabalho das CNNs (redes neurais convolucionais) com uma técnica de extração de dados e aplicação das técnicas de aprendizado de máquina SVM (support vector machine) e regressão logística, a rede neural é baseada na rede VGG-NET, uma rede multiclasse. O conjunto de dados utilizados é o mesmo que o nosso paper, o dataset da NEU. Com o sistema proposto, quando em comparação com os modelos de machine learning, há uma discrepância significativa entre os modelos à favor do modelo de rede convolucional, este que obteve uma acurácia de 99,44% enquanto o anterior obteve uma acurácia de 88,06% - 91,94%, o que mostra a supremacia do modelo de aprendizado profundo.

[Link do issue](https://github.com/ghastcmd/one-shot-steel-surfaces/issues/1)

# 2. Recognition Of Surface Defects On Steel Sheet Using Transfer Learning

O artigo pretende utilizar a técnica da transferência de aprendizagem de um modelo já consagrado, estado da arte, o modelo VGG-16, em que se consegue obter uma taxa de acurácia treinando-se com 150 imagens por classe e 10 imagens por classe, uma taxa de 99,1% e 96,0% respectivamente, utilizando-se o mesmo dataset que o artigo que escolhemos utiliza, o dataset NEU. Tenta-se demonstrar que existem redes neurais que foram previamente treinadas com milhares de imagens diferentes, e que, essas redes treinadas podem ter suas primeiras camadas, as camadas responsáveis pela extração de atributos básicos, mantidas, e as últimas camadas, responsáveis pela classificação de imagem, serem retreinadas para os propósitos desejados. No quesito de utilizar 10 imagens por classe, foram realizados vários testes com aumento de dados e percebeu-se que essas técnicas aumentaram em cerca de 0,2, de 0,667 para 0,86 e que, no tocante à inicialização de dados, o método XAVIER obteve maiores resultados, com valores de 0,921 de acurácia, juntamente com as técnicas de aumento de dados, também fora observado a adição de ruído, que, com o ruído de 30dB, obteve-se um aumento de 0,04 de acurácia.

[Link do issue](https://github.com/ghastcmd/one-shot-steel-surfaces/issues/3)


# 3. Deep Convolution Neural Network Approach for Defect Inspection of Textured Surfaces

Existem vários tipos de falhas que um tecido pode apresentar, a proposta do artigo é de utilizar técnicas de aprendizado profundo e redes neurais convolucionais para ambos aumentar a precisão dos diagnósticos de defeitos em texturas de tecido, como também diminuir os custos do mesmo. O paper explica o processo da formulação de uma rede neural convolucional, exemplificando as camadas de extração de atributos e camadas finais de classificação. O conjunto de dados utilizados é o dataset TILDA, nele existem 150 imagens com defeitos e 1000 imagens sem defeitos, as imagens com defeitos não possuem somente a parte com o defeito, mas também partes do tecido que estão sem defeitos, introduzindo ruído na parte de treino da rede neural.
O sistema, por apresentar uma seleção de parâmetros mais simples, apresentou somente uma acurácia de cerca de 50%, o que é bem pequeno em comparação aos outros resultados obtidos em superfícies metálicas, mas que demonstra que a técnica de aprendizado profundo convolucional pode, também, ser utilizado em texturas diferentes como é o caso de tecidos.

[Link do issue](https://github.com/ghastcmd/one-shot-steel-surfaces/issues/4)


# 4. TLU-Net: A Deep Learning Approach for Automatic Steel Surface Defect Detection

O artigo realiza a transferência de aprendizado de extração paramétrica básica com as redes de estrutura U-Net (TLU-Net), que, de início, o que foi percebido é o aumento considerável de performance relativa com uma pouca quantidade de dados de treino; a rede tenta resolver dois problemas, o fato de classificar qual o tipo de defeito que fora encontrado e a localização de onde o defeito foi encontrado. Contudo, a metodologia escolhida para resolver esses problemas é a adoção da arquitetura U-Net; determinar o tipo de inicialização da rede, que são blocos de ResNet ou Densenet-121, ambos treinados com conjunto de dados ImageNet; o problema de classificação; e a função objetiva que é a junção da perda das duas classificações, segmentação conjunta e de classificação. Os resultados são significativos, com uma diferença de 8% entre a rede que foi treinada com valores aleatórios em comparação com a rede que foi treinada previamente com o conjunto de dados ImageNet. Foi encontrado também que a performance da rede em imagens é baixa em defeitos mais complexos, e que dados anteriormente aprendidos não podem ajudar nesse quesito, pois a complexidade os torna problemas mais únicos.

[Link do issue](https://github.com/ghastcmd/one-shot-steel-surfaces/issues/5)

# 5. Unsupervised Surface Defect Detection Using Deep Autoencoders and Data Augmentation

O artigo propõe a utilização de sistemas não supervisionados de auto codificação e aumento de dados para poder identificar defeitos de superfície nos meios de produção de um determinado material; o que se conseguiu encontrar é que esse método são mais eficientes que os métodos em que se realizava uma busca feita à mão por detalhes que exemplificavam os defeitos nos materiais. A metodologia dispõe da criação de um extrator de características das imagens, e então essas características são comparadas para determinar se as duas imagens são semelhantes ou não, similar ao nosso artigo escolhido, que utilizou de redes siamesas para tal.
A proposta principal segmentar as imagens maiores em um tamanho fixo, que se possa treinar na rede proposta, e de realizar o aumento de dados com rotações aleatórias e virar as imagens no eixo horizontal. E então, treinar o codificador e a rede neural somente com imagens segmentadas que não detém de falhas, e então, posteriormente na fase de teste, é feito a comparação de imagens que contém falhas e imagens que não contém falhas, para o sistema decidir quais os dados que divergem, ou seja, contém falhas.

[Link do issue](https://github.com/ghastcmd/one-shot-steel-surfaces/issues/9)

# 6. Classification of surface defects on steel sheet using convolutional neural networks

O artigo é um documento introdutório à redes neurais convolucionais e explica cada minúcia em um modo bem verboso com expressões matemáticas, o modo com o qual será conduzido o sistema de redes neurais, com uma ênfase enorme na clareza das informações, para que não haja dúvidas dos métodos que serão aplicados. Ainda, aplica-se a técnica de aumento de dados, em que se redimensiona as imagens do dataset de 200x200 para um tamanho de 40x40, também utiliza-se rotações no sentido anti-horário e inversões horizontais e verticais, ainda foram normalizados os dados para obter uma média de zero e variância unitária em todas as amostras do dataset. O paper também tem uma análise da utilização de dados para o treino e para teste, mostrando que quanto mais dados disponíveis para treino, mais rapidamente o sistema fica melhor em classificar as imagens, com uma taxa de erro de 0 para uma quantidade de treino de 1000 imagens para treino, 800 para teste, um tamanho do batch de 50 e a quantidade de épocas de 100. Também mostrou-se que o erro de classificação para um imagem de 40x40 é aproximadamente 9% menor que o erro de classificação para imagens com dimensões de 140x140, o que demonstra a necessidade de obter uma segmentação mais bem pensada para problemas de classificação com redes neurais convolucionais.

[Link do issue](https://github.com/ghastcmd/one-shot-steel-surfaces/issues/10)

# 7. Deep Learning-Based Defect Detection System in Steel Sheet Surfaces

O paper pretende resolver o problema de detecção de falhas em folhas de metal, além de localizar e classificar as falhas do metal, diferentemente do nosso artigo que pretende classificar as falhas encontradas somente; utiliza-se a rede U-NET e Deep Residual U-NET para resolver o problema. Os datasets utilizados para treino são 12568 imagens para treino e 1801 imagens para teste, e de todas as imagens para treino, 5902 são imagens com defeito e 6666 imagens não tem defeitos; são imagens grandes, com dimensões de 1600x256. As arquiteturas selecionadas conseguem segmentar a imagem e delimitar aproximadamente os locais em que existe defeito, e classifica qual tipo de defeito está presente na área delimitada. Os resultados são bem diferenciados com uma acurácia DICE de 0,543 para as redes neurais utilizando a arquitetura U-NET e uma acurácia de 0,731 para a arquitetura Deep Residual U-NET.

[Link do issue](https://github.com/ghastcmd/one-shot-steel-surfaces/issues/11)
