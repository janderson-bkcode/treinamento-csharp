# Fundamentos de orientacao a objetos

Ja sabemos e orientacao objetos eh um paradigma de programacao baseado no conceitos de objetos.

Sabemos tambem que existem diversos paradigmas como o funcional, imperativo, orientado a objetos e entre outros.

O principal intuito de se ter criado a orientacao a objetos era de aproximar nossos programas das coisas do mundo real, por isso chamamos de "objeto", algo generico o suficiente para representar qualquer coisa do mundo real.

## Classes e objetos

Antes de comecarmos a entender os "Pilares da orientacao a objetos", vamos dar um passo atras e entender primeiramente o que eh essa tal de "classe" e o tal do "objeto".

Para entender melhor vamos modelar um carro e aplicar os conceitos acima.

Imagina que queremos comprar um carro  e vamos fazer uma lista com todas as caracteristicas que desejamos que esse carro tenha, a minha lista ficaria mais ou menos assim: 

Carro: 

- Possuir 4 rodas
- Possuir 4 portas
- Cambio automatico
- Ter a cor preta

Essas sao algumas das caracteristicas que desejo no carro, sabemos que o carro vem por "padrao" com algumas funcionalidades como: 

- Acelerar
- Freiar
- Businar
- Aparelho multimidia e etc

Beleza, escolhemos como o nosso carro precisar ser para atender a minha necessidade.

O que acabamos de fazer aqui foi criar a nossa classe, ou seja, um conjunto de caracteristicas e comportamentos que definem o carro que queremos. 

Beleza, mas o que seria esse objeto? O carro em si, fisico, com todas as caractertisticas e pronto para andar.

Mas como podemos criar isso em um programa, e como a parte fisica se comporta?

Para criar uma classe que represente um carro em C#, podemos fazer assim: 

```C#
public class Carro {

    public int QuantidadeRodas {get; set;}
    public int QuantidadePortas {get; set;}
    public bool PossuiCambioAutomatico {get; set;}
    public Cor Cor {get; set;}

    public void Acelerar(){
        // ..... implementacao
    }

    public void Businar(){
        // ..... implementacao
    }
}

public enum Cor {
    Preto,
    Verde,
    Azul,
    Amarelo
}
```

Pronto, acabamos de criar nossa classe "Carro", ou seja, uma estrutura de dados que representa um carro.

Mas entao, o que seria o objeto? Ja que eh impossivel criar um carro real pelo computador? 

Precisamos agora abstrair o conceito, estamos criando um programa de computador e queremos representar uma regra de negocio com o carro.

Entao, quando estamos criando um "objeto", estamos criando um carro na memoria do nosso computador.

Por exemplo, quero criar um carro no nosso programa com a cor azul, como podemos fazer isso? 

```C#
var carroAzul = new Carro();
carroAzul.Cor = Cor.Azul;
```

Dessa forma, criamos um objeto na memoria do nosso computador e atribuimos a esse objeto a cor azul.

## Atributos e metodos

Ainda utilizando o exemplo anterior, vamos entender o que sao atributos e metodos.

### Atributos

Os atributos sao as caracteristicas do nosso carro, como por exemplo a cor, rodas, se possui piloto automatico e etc.

Atributos se assemelham com "Variaveis", porem eles possuem algumas outras caracteristicas que vamos aprender a frente.


### Metodos

Metodos nada mais eh do que o comportamento do nosso objeto, por exemplo, acelerar, freiar, businar e etc.

Um metodo se assemelha com uma funcao, porem, um metodo pertence a uma classe.

## Pilates da orientacao a objetos

Os pilares da orientacao a objetos sao: Abstracao, Encapsulamento, Heranca e Polimorfismo.

### Abstracao

Abstracao nada mais eh do que a capacidade de extrair informacoes do problema que estamos querendo resolver. 

Imaginem que estamos criando um programa para um e-commerce, podemos abstrair desse contexto os produtos, vendas, frete, pagamentos e entre outras coisas. Ou seja, estamos abstraindo um problema do mundo real e criando uma solucao para isso, trazendo apenas as informacoes que importam para o contexto do nosso problema.

Podemos abstrair na criacao de nossas classes, na criacao dos nossos metodos, atributos e entre outras coisas.

O conceito de abstracao abrange varias areas da tecnologia e aprender a usar isso ao nosso favor eh de grande importancia para nossa carreira.

### Encapsulamento

Quando projetamos as nossas classes, eh de estrema importancia garantir que as informacoes que estao naquela classe corresponda ao cenario que estamos utilizando, ou seja, o "estado" da nossa classe tem que ser preservado.

Precisamos garantir que quem utilizar essa classe, consiga ver apenas o necessario e tambem manipular apenas o necessario.

Mas como garantir todas essa "restricao" de acesso e modificacao? Simples, encapsulando.

O encapsulamento basicamente consiste restringir ou nao a manipulacao informacoes de dentro da nossa classe.

E como podemos fazer isso em C#? Utilizando os modificadores de acesso.

Em C# possuimos varios modificadores de acesso, alguns deles sao: 

- Private
    - Mantem a informacao visivel somente para a classe em que ela foi declarava, somente essa classe pode visualizar e alterar.

- Public
    - Toda a informacao fica disponivel para quem utilizar a classe, podendo ler e alterar a informacao.

- Protected
    - Toda a informacao fica disponivel para a classe e para quem herdar desta mesma classe, podendo ler e alterar a informacao.

- Internal
    - Toda a informacao fica disponivel para quem utilizar a classe dentro do mesmo assembly/projeto, podendo ler e alterar a informacao.

Esses modificadores podem ser utilizados em classes, metodos, atributos, enum e etc.

Em classes ainda podemos combinar alguns moficadores, mas nao vamos abordar isso pode agora, fica como curiosidade.

### Heranca



### Polimorfismo


# Referencias

- []()