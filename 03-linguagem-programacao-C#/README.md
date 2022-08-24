# Linguagem de programacao C# - Base da linguagem

## Escopo de um programa

Em um programa dotnet normalmente temos a seguinte estrutura dentro de um arquivo. (Antes da versao 6 do dotnet)

1. Importacoes (Usings)
2. Namespaces (Separacao logica)
3. Classes
4. Um metodo principal.

Quando estamos escrevendo nossos codigos, dificilmente vamos escrever tudo do zero, o intuito de utilizar um framework eh justamente esse, facilitar nossa vida com implementacoes que seriam triviais no desenvolvimento de uma aplicacao. Entao, quando precisamos por exemplo escrever alguma informacao no console (Telinha preta do windows), nao precisamos criar uma integracao do 0 com esse componente do windows, a aplicacao ja nos da o suporte para isso, para isso precisamos apenas fazer o import no namespace System e utilizar o metodo Console.WriteLine("Meu texto aqui"). Vamos entender ao longo do curso a utilizar usings para utilizar funcionalidades prontas na nossa aplicacao.

Namespaces nada mais eh do que uma separacao logica em nossa aplicacao, imagina que voce tenha a necessidade de ter duas classes com o mesmo nome dentro da aplicacao, sem o uso de namespaces isso nao seria possivel, uma vez que iria dar conflitos com os nomes iguais. Porem com o uso de namespaces podemos separa os contextos da nossa aplicacao em "diretorios virtuais", e com essa funcionalidade podemos ter dois arquivos com o mesmo nome separado em namespaces diferentes, muito bom nao acham?

Vamos aprender o que realmente eh uma classe e sua importancia quando formos falar de orientacao a objetos, mas para nao deixar passar em branco, vamos simplificar a sua utilizacao. Uma classe nada mais eh do que um tipo de dados, como se fosse um int, string e etc. Mas diferentemente de um tipo int, uma classes possui estado e nenhum ou mais metodos para manipular seu estado.

E por fim temos o metodo principal, esse metodo eh a porta de entrada da nossa aplicacao, comumente chamamos esse metodo de SVM (static void main).
Basicamente toda aplicacao dotnet possui um metodo SVM.

## ![dotnet info](imagens/escopo.png)

## Namespaces e usings

### Namespaces

Quando pensamos em organizar arquivos, logo pensamos em pastas, diretorios e etc. Essa forma de organizacao eh super valida quando estamos criando nossos programas em dotnet, mas tambem podemos utilizar de um recurso super importante que sao os namespaces.

Os namespaces sao separacoes logicas, que permitem organizar melhor os nossos codigos. Com o uso de namespaces podemos ter varias classes com o mesmo nome (Nao que isso seja bom, mas podemos) em namepaces diferentes.

Veja no exemplo um mesmo arquico csharp com dois namespaces diferentes e dentro de cada namespace uma classe com o mesmo nome.

## ![dotnet info](imagens/namespaces.png)

Mas como se cria um namespace? Normalmente o nome do namespace segue a seguinte estrutura **"nome-projeto.diretorio-onde-se-encontra"**.

## ![dotnet info](imagens/namespaces2.png)

P - nome projeto | D - Nome diretorio na aplicacao.

Nas versoes anteriores ao dotnet 6, era-se obrigado a abrir e fechar chaves {} apos a definicao de um namespace. Nas versoes mais recentes (dotnet 6+) nao precisa mais criar esse tipo de estrutura, porem pode-se apenas definir um namespace por arquivo nessa nova estrutura. Essa nova forma de declaracao chama-se "file-scoped namespaces".

## ![dotnet info](imagens/namespaces3.png)

Por convencao, o ideal eh ter apenas um namespace por arquivo.

Um namespace nao limita-se a apenas um arquivo, posso ter dois arquivos com o mesmo namespace, isso eh muito comum inclusive. Quando formos contruir nossa aplicacoes vamos ver exemplos praticos da vida real com isso.

Lembra o using que vimos na sessao anterior? Quando utilizamos um using, estamos falando para a nossa classe que queremos utilizar as funcionalidades que temos dentro do namespace que declaramos.

Dentro no namespace "System" temos uma classe estatica chamada "Console" e dentro dessa classe temos um metodo estatico chamado WriteLine. Se nao utilizassemos o using na nossa classe teriamos que usar o metodo da seguinte forma: **System.Console.WriteLine("meu texto").**

### Usings

Para podemos utilizar alguns recursos do framework ou recursos que criamos nas nossas bibliotecas, temos que utilizar a palavra reservada using.

Por padrao o dotnet vem carregado com algumas funcionalidades e quando desejamos fazer uso de uma determinada funcionalidade ou recursos, utilizamos o using para que nossa aplicacao reconheca aquela funcionalidade.

Nas versoes anteriores ao dotnet 6 precisamos colocar varios usings semalhantes em quase todas as classes da nossa aplicacao, porem a partir do dotnet 6 foi implementado um recurso muito legal chamado "Global usings", onde para cada tipo de aplicacao/projeto sao importados de forma global varios namespaces que com certeza serao utilizados naquele projeto.

Normalmente as instrucoes usings sao declaradas no comeco do arquivo.

Podemos ver mais sobre global usings - [AQUI](https://docs.microsoft.com/en-us/dotnet/csharp/whats-new/csharp-10#global-using-directives)

## Palavras reservadas

Podemos escrever qualquer coisa nos nossos codigos desde que ele respeite as diretrizes da linguagem que estamos trabalhando, por exemplo: O C# ele eh case sensitive, isso significa que ele diferencia letra maiusculas de letras minusculas, vamos ver varios exemplos disso ao decorrer do treinamento.

Ou diretriz muito importantes sao as palavras reservadas da linguagem ou tambem conhecidas como keywords. As keyswords sao palavras que possuem um significado especifico para o compulador do C#. Por exemplo, nao posso declarar uma variavel com o nome de "int", porque int eh uma keyword que se refere a um tipo primitivo do C#, eu so poderia utilizar "int" se ele tivesse um prefixo "@" ou seja, "@if". Mas calma, nao precisamos decorar todas as keywords do C#, com o tempo as coisas ficam mais naturais e tambem a propria IDE nos auxilia nisso.

Podemos ver [AQUI](https://docs.microsoft.com/pt-br/dotnet/csharp/language-reference/keywords/) uma lista com as keywords do C#.

## Tipos primitivos

Tipos primitivos ou "built-in types" sao tipos base em dotnet. Por exemplo, seu eu quero represetar um numero inteiro, nao preciso criar uma classe ou uma struct para fazer isso, no dotnet existe o tipo primitivo "int32" ou "int". Seguindo o mesmo exemplo, se quero represetar uma cadeia de caracteres podemos utilizar o tipo "string". Existem varios tipos primitivos na plataforma dotnet e podemos encontrar uma referencia deles [AQUI](https://docs.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/built-in-types).

## Tipos de valor

Tipos de valor apresentam um comportamento diferente na CLR. Variaveis do tipo valor contem diretamente a instancia do seu tipo. Variaveis do tipo de valor nao alocam memoria na heap e nao acionam o coletor de lixo do dotnet.

Quando passamos o valor de uma variavel para a outra, seu valor eh copiado, ficando cada uma das variaveis com valores independentes, ou seja, se alterar o valor de uma variavel nao altera o valor da outra.

Tipos de valor nao podem receber a atribuicao de "null", a nao ser que transformemos ele em um valor anulavel com utilizando "?" depois do tipo:

```C#
int? x = null;
```

Ha duas cateorias de tipo de valor: enum e struct.

### Struct

Os tipos numericos primirivos, built-in types sao structs e contem propriedades e metodos que podemos acessar, por exemplo

```C#
byte b = byte.MaxValue;
```

Nao podemos realizar heranca com tipos de valor.

Podemos utilizar a palabvra chave "struct" para criar nossos proprios tipos, exemplo:

```C#
public struct Coordenadas
{
    public int x, y;

    public Coordenadas(int p1, int p2)
    {
        x = p1;
        y = p2;
    }
}
```

### enum

Um enum nada mais eh do que um conjunto de constantes integrais nomeadas, por exemplo: Queremos definir um conjunto de numero inteiros que expressam cores, para isso podemos fazer assim:

```C#
public enum Cores
{
    Amarelo = 1,
    Preto = 2,
    Verde = 3,
    Vermelho = 4,
    Azul = 5,
    Rosa = 6,
}
```

Mas porque utilizamos enum? Simples, usar nomes eh muito mais intuitivo do que usar numeros.

Enumeracoes herdam de System.Enum que herda de System.ValueType.

## Tipos de referencia

Tipos definidos como class, record, string, object, dynamic, delegate, matriz ou interface é um tipo de referencia.

Variaveis do tipo de referencia contem uma referencia de memoria para o valor do seu tipo. Variaveis do tipo de referencia alocam memoria na heap e acionam o coletor de lixo do dotnet.

Quando passamos o valor de uma variavel para a outra, seu valor nao eh copiado e sim a sua referencia, ou seja, se fizemos isso teremos duas variaveis apontando para o mesmo endereco de memoria da heap.

Por padrao, variaveis do tipo de referencia recebem o valor null se nao atribuirmos uma instancia de objeto ou utilizarmos o operador "new" para criar uma instancia do tipo.

```C#
string nome; // valor default null
string nome = "Willian Menezes";
```

Os tipos de referencia dao suporte completo a heranca, a nao ser que utilize o operador "selead"

## Conversao explicita e implicita

Quando estamos criando nossas aplicacoes, muitas vezes precisamos converter valores de um tipo para o outro, por exemplo: O input de uma informacao pelo usuario na nossa aplicacao, em alguns casos podem vir como "string", mas muitas vezes precisamos desse valor como um tipo "int", dessa forma precisamos realizar alguma conversao de tipo.

### Implicita

Dessa forma a conversao eh feita internamento pelo compilador do C#. Nao precisamos informar como a conversao sera feita, desde que seja possivel realizar a conversar o proprio compilador fara isso por nos, veja alguns exemplos:

```C#
int valor = 1050;

// convertendo int para double
double outroValor = valor;

Console.WriteLine(valor);
Console.WriteLine(outroValor);
```

Porem nesse mesmo exemplo o contraria nao eh permitido e o compilador nos informa isso:

```C#
double valor = 10.50;

// erro - nao podemos converter implicitamente double para int
int outroValor = valor;

Console.WriteLine(valor);
Console.WriteLine(outroValor);
```

Se quisermos fazer esse tipo de conversao, como vimos anteriormente precisaremos utilizar a conversao explicita.

```C#
double valor = 10.50;

// valor convertido, porem perdeu sua precisao
int outroValor = (int)valor;

Console.WriteLine(valor);
Console.WriteLine(outroValor);
```

Quando fizemos essa conversao, o valor do tipo double perdeu sua precisao para se transformar em um tipo int.

### Explicita

Precisamos nessa caso, explicitar a conversao que queremos fazer, ou seja, precisamos informar para o compilador que queremos transformar um tipo A em um tipo B.

No exemplo anterior tentamos fazer uma conversar implicita porem o compilador nao permitiu, vamos fazer o mesmo exemplo com uma conversao explicita.

### Observacao

Podemos tambem utilizar outras formas de conversao, como parse ou convert, veja:

```C#
int numero = int.Parse("10");
int outroNumero = Convert.ToInt32("10");
int outroNumeroQualquer = Convert.ToInt32(10.2);
```

## Operadores aritméticos

Podemos realizar operacoes aritmeticas utlizando tipos numericos com operadores aritmeticos do C#.

Esses operadores sao suportados por todos os tipos numeros e de ponto flutuante no C#.

### Operador de incremento unario

Podemos incrementar o valor de uma variavel em uma unidade utilizando o operador "++".

Podemos fazer isso de duas formas: pos-fixado e pre-fixado.

Veja os exemplos:

```C#
// Pre-fixado
double a = 1.5;
Console.WriteLine(a);   // output: 1.5
Console.WriteLine(++a); // output: 2.5
Console.WriteLine(a);   // output: 2.5

// Pos-fixado
int i = 3;
Console.WriteLine(i);   // output: 3
Console.WriteLine(i++); // output: 3
Console.WriteLine(i);   // output: 4
```

### Operador de decremento unario

Este operador segue a mesma regra do incremento unario, a unica diferenca se da pelo decremento do valor.

### Operadores de adicao e substracao

O operador de adicao, calcula a soma entre dois operandos.

```C#
Console.WriteLine(5 + 4);       // output: 9
Console.WriteLine(5 + 4.3);     // output: 9.3
Console.WriteLine(5.1m + 4.2m); // output: 9.3
```

O operador de substracao, subtrai o operado a direita do operando da esquerda.

```C#
Console.WriteLine(47 - 3);      // output: 44
Console.WriteLine(5 - 4.3);     // output: 0.7
Console.WriteLine(7.5m - 2.3m); // output: 5.2
```

Tambem podemos usar o operador de adicao para concatenar string e algumas outras operacoes que vamos aprender ao longo da jornada.

### Operador de multiplicacao

O operador de multiplicacao calcula o produto entre dois operandos.

```C#
Console.WriteLine(5 * 2);         // output: 10
Console.WriteLine(0.5 * 2.5);     // output: 1.25
Console.WriteLine(0.1m * 23.4m);  // output: 2.34
```

### Operador de divisao

O operador de divisao divide o operado a esquerda pelo operando a direita.

Divisao de numeros inteiros: Quando realizamos a divisao de numeros inteiros o resultado sempre sera um numero inteiro arredondado para zero, veja:

```C#
Console.WriteLine(13 / 5);    // output: 2
Console.WriteLine(-13 / 5);   // output: -2
Console.WriteLine(13 / -5);   // output: -2
Console.WriteLine(-13 / -5);  // output: 2
```

Mas se quisermos obter o resultado como um ponto flutuante basta utilizar um tipo de ponto flutuante no divisor ou realizar uma conversao explicita, veja:

```C#
Console.WriteLine(13 / 5.0);       // output: 2.6

int a = 13;
int b = 5;
Console.WriteLine((double)a / b);  // output: 2.6
```

### Operador de resto

Calcula o resto de uma divisao, veja:

```C#
Console.WriteLine(5 % 4);   // output: 1
Console.WriteLine(5 % 3);  // output: 2
```

## Operadores de atribuição

Um operador de atribuicao atribui o valor que esta do lado direito a uma variavel.

Por exemplo:

```C#
// estou atribuindo o valor 10 a variavel x.
int x = 10;

// estou atribuindo um conjunto de caracteres a variavel nome.
string nome = "Willian Menezes";
```

Podemos tambem utilizar a atribuicao composta de operadores aritmeticos para atribuir um valor a uma variavel.

Uma atribuicao composta, nada mais eh do que a combinacao de um operador aritmetico com o operador de atribuicao.

```C#
int a = 5;
a += 9;
Console.WriteLine(a);  // output: 14

a -= 4;
Console.WriteLine(a);  // output: 10

a *= 2;
Console.WriteLine(a);  // output: 20

a /= 4;
Console.WriteLine(a);  // output: 5

a %= 3;
Console.WriteLine(a);  // output: 2
```

## Operadores de comparação

### Igualdade e desigualdade

Os operadores de igualdade (==) e desigualdade (!=) se comportam de forma diferente para tipos de valor e referencia, vamos focar agora somente em tipos de valor.

```C#
int a = 1 + 2 + 3;
int b = 6;
Console.WriteLine(a == b);  // output: True

int a = 1 + 2 + 3;
int b = 6;
Console.WriteLine(a != b);  // output: False

char c1 = 'a';
char c2 = 'A';
Console.WriteLine(c1 == c2);  // output: False
Console.WriteLine(c1 == char.ToLower(c2));  // output: True
```

### Operador menor que <

O operador < retornará true se o operando à esquerda for menor do que o operando à direita, caso contrário, false:

```C#
Console.WriteLine(7.0 < 5.1);   // output: False
Console.WriteLine(5.1 < 5.1);   // output: False
Console.WriteLine(0.0 < 5.1);   // output: True

Console.WriteLine(double.NaN < 5.1);   // output: False
Console.WriteLine(double.NaN >= 5.1);  // output: False
```

### Operador maior que >

O operador > retornará true se o operando à esquerda for maior do que o operando à direita, caso contrário, false:

```C#
Console.WriteLine(7.0 > 5.1);   // output: True
Console.WriteLine(5.1 > 5.1);   // output: False
Console.WriteLine(0.0 > 5.1);   // output: False

Console.WriteLine(double.NaN > 5.1);   // output: False
Console.WriteLine(double.NaN <= 5.1);  // output: False
```

### Operador menor ou igual a <=

O operador <= retornará true se o operando à esquerda for menor ou igual ao operando à direita, caso contrário, false:

```C#
Console.WriteLine(7.0 <= 5.1);   // output: False
Console.WriteLine(5.1 <= 5.1);   // output: True
Console.WriteLine(0.0 <= 5.1);   // output: True

Console.WriteLine(double.NaN > 5.1);   // output: False
Console.WriteLine(double.NaN <= 5.1);  // output: False
```

### Operador maior ou igual >=

O operador >= retornará true se o operando à esquerda for maior ou igual ao operando à direita, caso contrário, false:

```C#
Console.WriteLine(7.0 >= 5.1);   // output: True
Console.WriteLine(5.1 >= 5.1);   // output: True
Console.WriteLine(0.0 >= 5.1);   // output: False

Console.WriteLine(double.NaN < 5.1);   // output: False
Console.WriteLine(double.NaN >= 5.1);  // output: False
```

## Operadores lógicos

### Operador AND lógico condicional &&

Quando queremos avaliar o AND logico entre dois operandos. Sabemos que o operador "&&" sera avaliado como true somente se os dois operandos forem true, veja:

```C#
int x = 10;
int y = 20;

bool resultado = x >= 10 && y <= 20; // True

bool outroResultado = x < 10 && y <= 20; // False
```

No segundo exemplo o operando a direita nao eh avaliado, porque o primeiro operando retornou false, logo o resultado no "&&" sera false.

### Operador OR lógico condicional ||

Quando queremos avaliar o OR logico entre dois operandos. Sabemos que o operador "||" sera avaliado como true somente se um dos dois operandos forem true, veja:

```C#
int x = 10;
int y = 20;

bool resultado = x >= 10 || y > 20; // True

bool outroResultado = x < 10 || y > 20; // False
```

No primeiro exemplo o operando a direita nao eh avaliado, porque o primeiro operando retornou true, logo o resultado no "||" sera true.

### Operador de negação lógica !

O prefixo unário ! calcula a negação lógica de seu operando. Ou seja, ele produz true, se o operando for avaliado como false, e false, se o operando for avaliado como true:

```C#
bool passed = false;
Console.WriteLine(!passed);  // output: True
Console.WriteLine(!true);    // output: False
```

## Estrutura condicional

# Referencias

- [Documentacao Oficial .NET - Using ](https://docs.microsoft.com/pt-br/dotnet/csharp/language-reference/keywords/using-statement)
- [Documentacao Oficial .NET - Namespaces ](https://docs.microsoft.com/pt-br/dotnet/csharp/language-reference/keywords/namespace)
- [Documentacao Oficial .NET - Keywords ](https://docs.microsoft.com/pt-br/dotnet/csharp/language-reference/keywords/)
- [Documentacao Oficial .NET - Tipos em C# ](https://docs.microsoft.com/pt-br/dotnet/csharp/fundamentals/types/)
- [Documentacao Oficial .NET - Conversoes explicitas e implicitas ](https://docs.microsoft.com/pt-br/dotnet/csharp/programming-guide/types/casting-and-type-conversions)
- [Documentacao Oficial .NET - Conversoes explicitas e implicitas (Tabela)](https://docs.microsoft.com/pt-br/dotnet/csharp/language-reference/builtin-types/numeric-conversions#implicit-numeric-conversions)
