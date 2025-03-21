# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
*a) A saída será undefined seguido de erro*
 
O valor de x será imprimido como indefinido pois foi declarada com var, o que permite que a variável, mesmo que definida após o console.log, seja lida como indefinida. Já o valor de y imprime erro pois foi declarado utilizando let, o que não permite acesso ao valor da variável quando declarada após o console.log.

______
**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

*b) Substituir if (a || b === 0) por if (a === 0 && b === 0)*

O uso do operador lógico ||, quando qualquer um dos valores fosse igual a zero, independentemente do outro, resultaria em "Erro: número inválido" ao rodar o código, enquanto o operador && permite que a saída seja "Erro: número inválido" somente quando ambos os números forem 0.

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

*b) O código imprime 200.*

O código executa o caso para "eletrônico", atribuindo valor 1000. Porém, já que não há break, é mudado para o próximo caso, atribuindo o valor de 200, e então sim é executado o break, imprimindo 200.

______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```

*d) 24*

O código multiplica todos os elementos da lista por 2, então elimina todos os valores acima de 5 e soma os elementos sobrando, resultando em 24.

______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

*c) ["banana", "abacaxi", "manga", "laranja"]*

A lista declarada tem seus elementos 1 e 2 ("maçã" e "uva") cortados e substituídos pelos declarados ("abacaxi" e "manga"), resultado em ["banana", "abacaxi", "manga", "laranja"].

______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.

*b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.*

Apesar das duas informações serem verdadeiras, a seunda não justifica a primeira, pois extends não é a única forma de herança.

______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

*a) I e II são verdadeiras.*

A classe Funcionario herda da classe Pessoa, enquanto o método super(nome, idade) chama o construtor da classe pai, iniciando os atributos nome e idade. O método apresentar() na classe Funcionario sobrepõe o método da classe pai, então a linha super.apresentar() chama o método original da classe Pessoa. O JavaScript moderno suporta classes e herança de classes.

______
**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

b) A asserção é verdadeira e a razão é falsa.

O conceito de polimorfismo na POO permite que que objetos de classes diferentes respondam à mesma mensagem diferentemente, de acordo com seus atributos. Porém, não pode ser implementado pelo método de sobrecarga de métodos, já que considera apenas a última declaração lida associada ao nome.

_____

# Questões dissertativas

9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

Código revisado e comentado:

```javascript
//define a função
function somaArray(numeros) {

    //define o inicio da soma
    let soma = 0;

    //define o intervalo, até onde a soma vai e que o vamor de i aumenta em 1
    for (let i = 0; i < numeros.length; i++) {
        //define a soma dos elementos do array após multiplicá-los por 2
        soma += 2*numeros[i];
    }
    //retorna o valor de soma
    return soma;
}
//define os elementos do array a serem inicializados e impressos
console.log(somaArray([1, 2, 3, 4]));
```

______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

```javascript
class Produto {
    //criar os atributos de Produto
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }
  
    calcularDesconto() {
        // aplica um desconto fixo de 10% no preço do produto
        const desconto = this.preco * 0.10;
        return this.preco - desconto;
    }

    
    precificar() {
        console.log(`Produto: ${this.nome}, Preço: ${this.idade} .`);
      }
  }
  
  class Livro extends Produto {
    //cria os atributos de livro
    constructor(nome, preco) {
        //chama o construtor da classe pai
        super(nome, preco);
        this.autor = autor;
    }
  
    calcularDesconto() {
        //sobrescreve o método da classe pai para aplicar 20% de desconto
        const desconto = this.preco * 0.20;
        return this.preco - desconto;
    }

    precificar() {
        console.log(`Livro: ${this.nome}, Preço: ${this.idade} .`);
      }
  }
```
Nesse contexto, a herança permite que a classe Livro herde todos os métodos e propriedades da classe Produto por meio de extends. Para implementar a modificação do método na classe livro, seria necessário criar instâncias na classe, permitindo a diferente atribuição ou polimorfismos.