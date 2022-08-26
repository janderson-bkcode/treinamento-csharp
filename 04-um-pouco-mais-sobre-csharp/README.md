# Um pouco mais sobre C#

Neste capitulo vamos entender sobre alguns outros recursos muito importantes dentro do dotnet e C#.

Vamos entender o que sao e como utilizar array, vamos entender o que sao tipo genericos e como utiliza-los na pratica e tambem vamos brincar com listas, list, lambda e etc.

## Array

Uma array nada mais eh do que uma estrutura de dados que contem um conjunto de elementos representados pelo mesmo tipo de dado, onde podemos acessar cada um desses elementos atraves de um indice (um numero inteiro).

Um array de uma dimensao eh conhecido como vetor e um array com mais de uma dimensao eh conhecido como matriz.

Vamos entender alguns conceitos gerais sobre arrays.

- O tamanho de um array (Quantidade de elementos que ele suporta) sao estabelecidos na sua criacao.

- O valores padroes dos campos de um array eh definido de acordo com o tipo que utilizamos para cria-la, para tipos reference type o valor padrao eh null e para value types o valor padrao do tipo declarado eh assumido.

- O primeiro elemento de um array pode ser acessado atraves do indice 0.

- Um array/matriz eh um tipo de referencia.

Vamos entender como criar alguns arrays: 

```C#
int[] valores; // declarando um array de qualquer tamanho
valores = new int[5]; // atribuindo uma instancia de array com 5 elementos
valores = new int[50]; // atribuindo uma instancia de array com 50 elementos

valores[0] = 999; // atribuindo valor na primeira posicao do array
valores[1] = 1000;// atribuindo valor na segunda posicao do array
```

Podemos instanciar/criar um array de algumas formas, vejamos algumas a seguir: 

```C#
// declarando e depois instanciando um array
int[] valores; 
valores = new int[5]; 

// definindo seu tamanho
int[] valores = new int[5]; 

// definindo seu tamanho e inicianlizando os elementos
int[] valores = new int[3] { 1, 2, 3 };

// inicianlizando os elementos sem informar o tamanho
int[] valores = new int[] { 1, 2, 3 };

// inicianlizando os elementos sem utilizar o new
int[] valores = { 1, 2, 3 };
```

### Percorrendo os elementos de um array

Agora imagine que o nosso array tem um tamanho de 1000 elementos, e que para cada elemento desse temos que adicionar uma unidade ao seu valor, como poderiamos resolver isso? Vejamos uma solucao "inocente e trabalhosa" : 

```C#
int[] milElementos = new int[1000] {1, 2, 3 ......etc}

milElementos[0] = milElementos[0] + 1;
milElementos[1] = milElementos[1] + 1;
milElementos[2] = milElementos[2] + 1;
milElementos[3] = milElementos[3] + 1;

// ...... etc
```

Imagina fazer isso para os mil elementos? Muito trabalho.

Vamos resolver isso de uma forma mais elegante, lembra dos lacos de repeticao? Bora utiliza-los para resolver esse problema.

```C#
int[] milElementos = new int[1000] {1, 2, 3 ......etc}

for (int i = 0; i < milElementos.Length; i++)
{
    milElementos[i] = milElementos[i] + 1;
}
```

Conseguir enxergar a solucao? Muito mais simples nao? 

Percorremos cada indice do array com o nosso indice do laco "for", se olhar com carinho vai ver que o limite de execucao do for corresponde ao tamanho do nosso array e a cada nova iteracao avancamos um indice e somamos o valor +1.

Tambem podemos percorrer arrays com o While, Do e com o Foreach. Mas por enquanto vamos apenas utilizar o for e com o tempos vamos treinando utilizaer as outras estruturas de dados na pratica.


# Referencias

- [Documentacao Oficial .NET - Matrizes](https://docs.microsoft.com/pt-br/dotnet/csharp/programming-guide/arrays/)