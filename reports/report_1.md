# Links de vídeo pesquisados relacionados ao artigo

[C4W4L02 One Shot Learning](https://www.youtube.com/watch?v=96b_weTZb2w)

O video explica o paradigma da aprendizagem de máquina **One Shot**, que é basicamente conseguir aprender padrões de valores novos com apenas uma única entrada. Em resumo, utilizando-se uma foto, o que esse paradigma exemplifica é realizar uma aquisição do entendimento dos padrões que formam uma imagem, consegue rapidamente entender os valores paramétricos que tornam uma imagem única, dentro do dataset previamente adquirido. Com isso, o sistema que adere ao paradigma **One Shot**, consegue, com uma única imagem, diferenciar se ela já foi previamente vista pelo sistema, ou não. Ele consegue esse feito, com o simples fato de trainar um sistema de redes neurais, com um input de duas imagens por vez, e diz o quanto que essas duas imagens são diferentes entre si, com isso, caso leia uma foto do rosto de uma pessoa, e caso essa pessoa esteja registrada no sistema, ela apresentará um fator de diferença entre as imagens muito baixas.

[C4W4L03 Siamese Network](https://www.youtube.com/watch?v=6jfw8MuKwpI)

A arquitetura siamesa de redes neurais é basicamente duas redes convolucionais que contém uma função de perda que computa a diferença de atributos obtidos pelas duas redes convolucionais. O que ocorre é que cada rede convolucional, com as entradas de imagens, uma para cada uma das duas redes neurais, extrai os atributos principais das imagens, com o uso das camadas convolucionais que extraem os parâmetros com o aprendizado de máquina, e com o último vetor achatado da rede, realiza-se a diferença modular entre os vetores para obter a distância de similaridades entre as duas imagens, e, com isso, utiliza-se uma função de perda que treina a rede neural caso tenha calculado uma similaridade da rede quando as fotos são diferentes e vice-versa.

