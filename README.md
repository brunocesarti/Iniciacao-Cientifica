# Iniciação Científica

# Extração e classificação de movimentos motores: Uma abordagem utilizando aprendizagem de máquina profunda

## Temos como objetivo neste trabalho, desenvolver um estudo para mapeamento da postura da coluna de dos seres humanos baseados na tecnologia de inteligência artificial utilizando a ferramenta proposta por [Mathis](https://www.nature.com/articles/s41593-018-0209-y). Desta forma, utilizando o [DeepLabCut](http://www.mackenziemathislab.org/deeplabcut) poderemos inferir dados sobre a característica de posicionamento geográfico de qualquer objeto em estudo, de uma forma não invasiva, evitando inclusive influenciar nos resultados. Esperando ao fim deste trabalho poder gerar uma aplicação para obtenção da postura da coluna de um ser humano.

[Apresentação do projeto no  XXIX Seminário de Iniciação Científica:](https://youtu.be/c-_Khguj6xo)

[![Apresentação do projeto no  XXIX Seminário de Iniciação Científica](https://user-images.githubusercontent.com/12937320/132610941-ba253596-5ed9-4f69-9531-0690dc0d26fb.jpeg)](https://youtu.be/c-_Khguj6xo)


Link para documentação em Wiki: https://github.com/brunocesarti/Iniciacao-Cientifica/wiki

## Sumário

[Home](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki)

[Fluxo de desenvolvimento](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Fluxo-de-desenvolvimento)

[Manual de instalação pelo docker](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Manual-de-instala%C3%A7%C3%A3o-pelo-docker)

[Instalação do docker e cuda](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Instala%C3%A7%C3%A3o-do-docker-e--cuda)

[Gerando um Contêiner do docker](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Gerando-um-Cont%C3%AAiner-do-docker)

[Usando a GUI do Project Manager](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Usando-a-GUI-do-Project-Manager)

[Criando um ambiente com o Anaconda](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Criando-um-ambiente-com-o-Anaconda)

[Executando a ferramenta DeepLabCut](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Executando-a-ferramenta-DeepLabCut)

[Primeiro projeto no DeepLabCut Teste 1](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Primeiro-projeto-no-DeepLabCut---Teste-1)

[Segundo projeto no DeepLabCut Teste 2](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Segundo-projeto-no-DeepLabCut---Teste-2)

[Terceiro projeto no DeepLabCut Teste 3](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Terceiro-projeto-no-DeepLabCut---Teste-3)

[Projeto usando DeepLabCut no Google Colab com Drive para treinamento](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Projeto-usando-DeepLabCut-no-Google-Colab-com-Drive-para-treinamento)

[Criando novo projeto triângulo red](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Criando-novo--projeto---tri%C3%A2ngulo-red)

[Criando novo projeto triângulo invisível](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Criando-novo-projeto---tri%C3%A2ngulo-invis%C3%ADvel)

[DeepLabCut Toolbox demo for post processing triângulo invisível](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/DeepLabCut-Toolbox---demo-for-post-processing---tri%C3%A2ngulo-invis%C3%ADvel)

[Criando novo projeto para análise da postura](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Criando-novo-projeto-para-an%C3%A1lise-da-postura)

[Conclusão](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Conclus%C3%A3o)

[Trabalhos Futuros](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Trabalhos-Futuros)

[Referências](https://github.com/brunocesarti/Iniciacao-Cientifica/wiki/Refer%C3%AAncias)

## Prévia do trabalho desenvolvido:

Observe que existe uma relação simétrica entre os pontos de interesse, existindo um alinhamento entre os pares e triplas de pontos [ orelha, ombro ], [ queixo, cervical ], [ ombro, queixo], [ cervical, orelha, nariz ] todos em uma perspectiva 2D no plano [ x, y ].
Na imagem abaixo segue uma visualização de uma projeção feita no paint de como relacionar os pontos (tanto na imagem, como no vídeo a ser processado, são filmagem da minha própria pessoa e autoria):

![Imagem 201](https://github.com/brunocesarti/Iniciacao-Cientifica/blob/main/Imagens%20IC/Imagem%20201.png?raw=true)

Observe o alinhamento entre os pontos, cervical, orelha e nariz, em uma visualização 2D.

![Imagem 202](https://github.com/brunocesarti/Iniciacao-Cientifica/blob/main/Imagens%20IC/Imagem%20202.png?raw=true)

![Imagem 222](https://github.com/brunocesarti/Iniciacao-Cientifica/blob/main/Imagens%20IC/Imagem%20222.png?raw=true)

![Imagem 223](https://github.com/brunocesarti/Iniciacao-Cientifica/blob/main/Imagens%20IC/Imagem%20223.png?raw=true)

![Imagem 224](https://github.com/brunocesarti/Iniciacao-Cientifica/blob/main/Imagens%20IC/Imagem%20224.png?raw=true)

A base foi gerada com sucesso com coordenadas de 5124 imagens:

![Imagem 230](https://github.com/brunocesarti/Iniciacao-Cientifica/blob/main/Imagens%20IC/Imagem%20230.png?raw=true)

Base de dados da postura cervical gerada com sucesso no formato csv. Para adequar a base ao padrão a ser publicado, vamos converter os dados para um arquivo xlsx com uma coluna adicional indicando se cada amostra está correta ou não quanto a postura da cervical, o que nos indica, finalizando a classificação da base.

**Considerações para classificação:**

**Duração do vídeo [s]:** 170,78, gravado com 30,0 fps!

**Nº total de quadros:** 5124 encontrados com (antes do corte) 

**Dimensões de quadro:** 640 352

Para gerar nossa base de dados, exportamos o arquivo para o formato xlsx do excel, e realizamos a classificação segundo o mapeamento no vídeo gerado pela saída do DeepLabcut.

![Imagem 231](https://github.com/brunocesarti/Iniciacao-Cientifica/blob/main/Imagens%20IC/Imagem%20231.png?raw=true)

Informações sobre a base gerada:

Descrição: 
Base de dados da coluna cervical gerada com o uso da ferramenta DeepLabCut. Os dados foram coletados em 1 pessoa, analisando variação de movimento da coluna cervical, com a postura sentada realizando a ação de utilizar o notebook.

Quanto à coleta, foram mapeadas as coordenadas [x, y] em 5 pontos,  que chamamos de marcadores ( orelha, nariz, queixo, cervical, ombro) em um vídeo de 2 minutos e 50 segundos.  

Na classificação, 1 indica postura certa, 2 indica postura errada. A classificação foi realizada com base no vídeo mapeado pela ferramenta DeepLabCut.

**Características do conjunto de dados:** Sequencial

**Características do atributo:** Inteiro, Real

**Tarefas associadas:** Classificação

**Número de Instâncias:** 5124

**Número de atributos:** 10

**Área:** Computação

**Data Coleta:** 13/07/2021
