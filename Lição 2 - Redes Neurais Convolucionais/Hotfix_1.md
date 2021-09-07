# Seção 1.2

### 1.2

> CNN é um modelo de rede neural que tem por objetivo detectar padrões, o que permite extrair características essenciais da entrada, de forma a classificá-la como um todo. Os elementos de sua arquitetura são explicados a seguir:
> Feedback:

- Sugiro iniciar o notebook de maneira mais suave, explicando o que significa a sigla CNN e porque ela é chamada assim.
- Sugiro também falar quais são as suas principais aplicações (como reconhecimento de imagens, por exemplo)
- Sugiro uma pequena menção do porque usar uma CNN em vez de uma rede neural comum. Um resumo do segundo tópico desse documento é minha sugestão: [Link](https://towardsdatascience.com/a-comprehensive-guide-to-convolutional-neural-networks-the-eli5-way-3bd2b1164a53)

### 1.2.1

> A partir de uma entrada, por exemplo uma imagem, são atribuídos diferentes pesos, em forma de matriz como mostrado acima, para cada aspecto da mesma, a fim de diferenciar cada um. São denominados "Kernels". As convoluções destes com a entrada geram filtros que permitem a extração das características para o reconhecimento da mesma.

- Eu ajustaria esse parágrafo para: “Dada uma determinada entrada, como uma imagem, por exemplo, é gerado um filtro em forma de matriz com diferentes pesos, denominado Kernel. Esse Kernel é convoluido com cada um dos dados que constituem a entrada, deslizando sobre os dados de entrada, como mostrado acima. Essa operação gera uma saída que permite a extração das características para o reconhecimento da mesma.”

### 1.2.2

> Extraem as características mais dominantes da saída da camada de convolução. O objetivo desta camada é o de diminuir o esforço computacional necessário para processar a entrada reduzindo os espaços de memória que as saídas da camada de convolução ocupam. Isto é feito através de duas principais formas: Substituindo essa saída, que é composta de vários valores para a mesma característica (representa a intensidade da característica naquele ponto), pelo maior valor entre elas (chamado de “Max Pooling”) ou pelo valor médio entre elas (chamado de “Average Pooling”).

- "(...)Substituindo essa saída, que é composta de vários valores para a mesma característica(...)". Acho importante dizer que esses “vários valores” são os resultantes da operação convolucional citada anteriormente

### 1.2.3

> Após passar pelas camadas acima, lembrando que podem ter várias de cada, sempre passando primeiro pela “Convolutional Layer” e depois pela “Pooling Layer”, depois para o próximo par de camadas, o próximo estágio é planificar a saída final dessas camadas para passar pela Camada Totalmente Conectada, que por sua vez aplica algoritmos de feedforward e backpropagation para:

- "(...)Camada Totalmente Conectada(...)". Podemos colocar (fully connected) depois do termo, já que é como ela é mais conhecida.
- Seria interessante a gente falar sobre o que é o dropout. Não é preciso entrar muito a fundo aqui, seria só pra situar o leitor que não sabe ainda para que serve essa técnica.
