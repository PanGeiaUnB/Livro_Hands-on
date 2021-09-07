# Seção 1

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

# Seção 2

### 2.1

> Com a seleção da arquitetura da rede, e observando o seu funcionamento, o próximo passo é melhorar o seu desempenho. Para isso, é necessário verificar alguns aspectos das redes. É possível fazer a distinção entre dois tipos de parâmetros, os chamados de parâmetros do modelo e hiperparâmetros. Os parâmetros são estimados pelo modelo a partir do dataset que lhe é fornecido. Os hiperparâmetros não são estimados pelo modelo. O objetivo dos hiperparâmetros é estimar os parâmetros do modelo, por exemplo os pesos da rede neural. A partir disso é possível compreender que na medida em que esses parâmetros são ajustados, ocorre um treinamento melhor da rede, proporcionando dessa forma resultados melhores. Alguns exemplos dos hiperparâmetros são: learning rate, o número de épocas, batch size.

- "(...)O objetivo dos hiperparâmetros é estimar os parâmetros do modelo(...)" Acho que essa frase ficou ambígua, sugiro dizer que os hiperparâmetros são configurações que o programador ajusta pra possibilitar que a rede entenda os parâmetros que ajustam os dados de entrada e de saída.

### 2.2

> ![overfitting](https://miro.medium.com/max/700/1*Rhc8L0_Nuw374xMb05UnzA.png)

- Essa imagem é muito ilustrativa, mas acho que devemos fazer uma nota sobre o eixo x. Isso porque ele pode se confundir com a questão do grau polinomial, já que isso não está sendo usado aqui. Ou podemos escolher outra imagem, ou podemos dizer no texto que o eixo x pode ser diferentes variáveis, como o numero de parâmetros da rede, o número de épocas de treinamento ou a complexidade do modelo (nesse caso representado como o grau dos polinômios envolvidos no algoritmo de classificação).

### 2.3

- Nessa seção, é necessário tirar a parte em que conceituamos o que são cada um dos datasets, porque já fizemos isso na lição 1. Entretanto, a última parte, em que apresentamos como o treinamento é feito, acho bom deixa, para reforçar cada um desses conceitos.
- Está havendo confusão entre dataset de validação e teste. Isso é meio confuso na literatura mesmo, mas o meio mais técnico chama de dataset de validação aquele que é passado durante o treinamento pra verificar a evolução da acurácia e do custo durante o processo, quanto o de teste seria o último, aquele em que o modelo será testado pra mensurar a sua capacidade final de atuação.

### 2.4

> A seguir, será dado um exemplo de como realizar a divisão do dataset. Para isso, será utilizado um dataset clássico para as CNN's, o MNIST.

- O “A seguir” faz parecer que a implementação vem logo em sequência. Sugiro mudar para: “Na seção tal, …”

# Seção 3

### 3.1.1

> A função é calculada pela equação 1 / (1 + e-x) e tem um formato de “S”.

- Sugiro colocar essa equação em formato latex, como nas outras lições.

### 3.1.2

> A função tanh é calculada pela equação (e<sup>x</sup> - e<sup>-x</sup>) / (e<sup>x</sup> + e<sup>-x</sup>)

- Sugiro colocar essa equação em formato latex, como nas outras lições.

### 3.1.3

> Ao utilizar essas funções no treinamento de redes com muitas camadas (ou deep neural networks) o gradiente diminui drásticamente ao passo que ele é propagado de volta na rede durante o backpropagation. O erro pode se tornar tão pequeno ao alcançar as camadas próximas à camada de input do modelo que seu efeito se torna praticamente desprezável, causando o "desligamento" de alguns nós.

- Desprezável é Desprezível. Sugiro passar o texto por um corretor de texto pra pegar esses erros de digitação.

### 3.2.3

> Antes de trinar uma rede neural, os pesos da rede devem ser inicializados com valores randômicos pequenos.

- Sugiro passar o texto por um corretor de texto pra pegar esses erros de digitação.

### 3.4

> Todas as funções vistas até aqui tratavam exclusivamente das camadas escondidas. Agora, apresentaremos uma função para a camada de output, onde obtemos a previsão do modelo.
> Existem várias funções que podem ser utilizadas na camada de output, como funções lineares, sigmoide, max, argmax, dentre outras. Porém iremos usar e explicar apenas a função **softmax**, por ser uma das mais utilizadas para problemas de classificação de imagens.

- Apesar da lição entrar em um problema de classificação, sugiro deixar claro que em problemas de regressão ela não serve, porque o leitor pode entender que ela é uma função de ativação usada para a camada de saída de quase todos os problemas.

### 3.4.1

> Podemos descrevê-la por meio da função **e<sup>x</sup> / sum(e<sup>x</sup>)**

- Sugiro colocar essa equação em formato latex, como nas outras lições.

```
from numpy import exp

# softmax activation function
def softmax(x):
	return exp(x) / exp(x).sum()

# define input data
inputs = [1.0, 3.0, 2.0]
# calculate outputs
outputs = softmax(inputs)
# report the probabilities
print("Probabilidades:")
print(outputs)
# report the sum of the probabilities
print("\nSoma das probabilidades:")
print(outputs.sum())
```

- Sugiro passar os comentários para português, por uniformização e no print, sugiro colocar um campo: “vetor original = [1, 3, 2]” pra facilitar o entendimento.

# Seção 5

```
data = ImageFolder('data/Data', transform=transform) # Obtendo as imagens a partir do Drive e aplicando a transformação
print('Total de imagens no dataset:', len(data))
```

- Ajustar esse comentario, ja que as imagens não sao mais puxadas do drive

```
def testar_gpu():
	train_on_gpu = torch.cuda.is_available()
	if train_on_gpu:
		device = torch.device('cuda')
		print("Treinando na GPU")
	else:
		device = torch.device('cpu')
		print("GPU indisponível, treinando na CPU")
	return device

device = testar_gpu()
```

- Seria interessante uma breve explicação sobre o que essa célula faz, explicando o porque de a gente treinar na CPU. De maneira bem resumida mesmo.

# Sugestões gerais:

- Na parte de execução de código (seção 5), é preciso escrever entre as células de código, explicando rapidamente o que cada célula vai fazer. Não é necessário re-explicar conceitos, mas é importante situar o leitor sobre o que está sendo feito.
- Além disso, é necessário explicar o problema, o que estamos classificando. Em nenhum momento explicamos que é uma classificação de animais e quais são as classes possíveis.
- Seria interessante fazer uma função de teste, em que o leitor subia a imagem de um animal para verificar a atuação da rede.
