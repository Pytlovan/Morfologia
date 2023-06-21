# Morfologia
O presente código realizado em python, com o auxílio do google colab, tem por objetivo demonstrar a utilização de algumas das operações morfológicas mais importantes quando se trabalha no contexto de processamento de imagens. O código foi desenvolvido pelo professor Felipe Viel, que ministra suas aulas na UNIVALI para os alunos de Introdução à Ciência da Computação do primeiro semestre, e foi requisitado que os alunos comentassem o código de forma a entenderem como funciona o código e ter um primeiro contato com a linguagem Python de programação, com as bibliotecas do numpy e opencv (cv2).

O código utiliza 3 imagens para o processamento no geral, todas em preto e branco para facilitar o uso das operações:
1. Letra j minúscula em cursivo, limpa; <br>
2. Letra j minúscula em cursivo, com ruídos; <br> 
3. Letra j minúscula em cursivo, com furos; <br>

As imagens encontram-se em anexo.

Com a imagem limpa, são demonstrados o funcionamento das operações de **erosão**, que agem no afinamento de um objeto na imagem, e operações de **dilatação**, que enlargam o contorno do objeto. Podem ser observados nas imagens 2 e 3 ao final do código. Ambas as operações utilizam de um elemento de estruturação (kernel) que é normalmente uma matriz de 1's, onde ela realiza um processo iterativo sobre toda a imagem e avalia os contornos de um elemento. Quando encontrado um elemento dentro da matriz que é totalmente preenchido (no caso o branco do j cursivo), não realiza-se nenhuma operação. Porém quando há um contorno, realiza-se a operação de erosão ou dilatação correspondente, representando uma alteração da imagem original de acordo com a operação requisitada.

Para o tratamento dos ruídos das imagens com ruídos e com furos, foram utilizadas operações de **abertura** e **fechamento** respectivamente. O intuito dessas operações é uma combinação das operações de erosão e dilatação, que quando trabalhadas em conjunto acabam por reduzir o nível de ruídos da imagem. 

Para a abertura, é realizada primeiramente uma operação de erosão, de modo a tentar diminuir o nível de ruídos, além de claro afinar os elementos principais da imagem, e em sequência, como é esperado que os ruídos estejam de menor tamanho, realiza-se uma operação de dilatação para retornar os elementos principais aos seus tamanhos originais, e como os resíduos encontram-se diminuídos, a dilatação não será tão impactante nos ruídos, fazendo assim com que o nível de ruídos na imagem diminua.

Para o fechamento, é realizada primeiramente uma operação de dilatação, para "tampar" os buracos dentro do "j", além de dilatar o objeto principal, e em sequência realiza-se a operação de erosão para retornar o elemento ao seu tamanho original.

A última operação abordada no exemplo foi a de **gradiente**, que no caso retorna apenas o contorno da imagem. O gradiente funciona também com erosão e dilatação, exceto que elas são aplicadas não sequencialmente, mas sim individualmente. Com o resultado da dilatação e da erosão, realiza-se a computação da diferença entre as duas, e essa diferença é utilizada para gerar o contorno da imagem.

Nos comentários do código estão melhor exemplificados como são utilizadas as funções e os métodos de processamento de imagem.

![j](https://github.com/Pytlovan/Morfologia/assets/111884654/70adea19-45fe-481e-b618-0e53bd9f14c2)
![j_ruido](https://github.com/Pytlovan/Morfologia/assets/111884654/bda49bb9-47f5-4d03-862f-c73cd63312fa)
![j_furos](https://github.com/Pytlovan/Morfologia/assets/111884654/5c3da955-b295-45ce-826c-c669733c4dbe)
