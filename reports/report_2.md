# Apresentação

## Apresentar o nosso artigo minuciosamente

### [ORIGINAL] - ONE-SHOT RECOGNITION OF MANUFACTURING DEFECTS IN STEEL SURFACES

O controle de qualidade automatizado é extremamente importante para as empresas
para manter os produtos livres de defeitos e fazer com que atinjam as exigências
dos usuários. Houve avanços na área de aprendizado profundo e visão computacional,
porém muitas das soluções têm uma abordagem intensiva em dados, o que pode tornar
o treinamento e implementação dessas soluções caras e demoradas. o artigo propõe
a aplicação de redes neurais convolucionais siamesas para fazer o reconhecimento
one-shot para tal tarefa.

O que ocorre também é que muitas cadeias de produção não possuem dados suficientes para conseguir treinar as redes neurias, com isso, o artigo propõe a utilização de redes neurais siamesas para conseguir o reconhecimento de defeitos numa folha de metal com uma única imagem, uma técnica _one-shot_, em que se usa uma técnica bastante utilizada no reconhecimento de faces em um banco de dados.

![imagem do formato da rede neural](../images/formato%20da%20rede%20neural.png)

### ONE-SHOT RECOGNITION USING SIAMESE NETWORKS

A ideia chave por trás de reconhecimento de imagem com one-shot é que dado um único
exemplo da imagem de uma classe particular, a rede deve ser capaz de reconhecer se a imagem candidata pertence à mesma classe ou não. A rede aprende a identificar as 
diferenças em features do par de imagens de entrada em treinamento. 

A rede foi treinada utilizando a função "contrastive loss", uma vez treinado, o modelo, deve ser capaz de identificar vários defeitos dado um único exemplo de cada defeito.

Se as imagens são da mesma classe a segunda parte da equação é penalizada
e o valor da perda (loss value) é diretamente proporcional ao quadrado da distancia
euclidiana. O objetivo é minimizar a perda; os pesos da rede são treinados para reduzir
a distancia entre os vetores de amostra $x_1$ e $x_2$.
Se as imagens são de classes diferentes, a primeira parte é anulada, e se y=0 e D>m (D é a distância euclidiana entre as duas entradas), o modelo não é penalizado. A penalidade é aplicada se a distancia euclidiana entre $f(x_1)$ e $f(x_2)$ é menor que a margem atribuída, m. O objetivo nesse caso é afastar $f(x_1)$ e $f(x_2)$ um do outro no espaço n dimensional e fazer a distância entre eles maior que m (a margem atribuída). A segunda parte da equação pode ser entendida como para o algoritmo aprender a diferneça entre as imagens $x_1$ e $x_2$ quando pertencem a classes diferentes.

Com isso a rede aprende não só a similiradade entre as imagens de mesma classe mas também calcula a perda para imagens de classes diferentes quando o segundo termo não é zero. Isso evita que o modelo se transforme numa função constante.

## Mostrar como o código funciona

Mostrar o código da rede siamesa

Explicar o dataset com o código

## Sumário dos resumos dos artigos em bullet-point

Apresentar o arquivo [report_artigos.md](report_artigos.md)

## Explicar os resultados obtidos do nosso paper

Explicar com código e os resultados das acurácias

## Uma suposta melhora para o artigo original baseado nas pesquisas

O artigo propõe a utilização de uma rede neural pré-treinada para a melhoria do reconhecimento de falhas utilizando a rede neural siamesa. Contudo, em nossa pesquisa, conseguimos encontrar um artigo em que utiliza-se a rede Neural VGG-16 para a extração de características na parte convolucional da rede neural utilizada no artigo. O artigo citado obteve uma acurácia de 99,1% utilizando metade do conjunto de dados utilizados no nosso artigo para a rede convolucional, e uma acurácia de 96,0% utilizando somente 10 imagens de cada classe do conjunto de dados NEU, o utilizado pelo nosso artigo. Ademais, como a rede neural siamesa é basicamente uma rede neural convolucional, tal qual é a arquitetura VGG-16, assim, acreditamos que conseguiríamos aplicar este estudo no artigo escolhido por nós, para poder aprimorar os resultados.