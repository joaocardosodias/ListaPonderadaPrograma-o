

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) **A saída será undefined seguido de erro** 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

Resposta: a) A saída será undefined seguido de erro


A variável x é declarada com var, que sofre hoisting, ou seja, a declaração é movida para o topo do escopo, mas a atribuição não. Portanto, console.log(x) imprime undefined.
A variável y é declarada com let, que também sofre hoisting, mas não é inicializada até a linha onde é declarada. Portanto, console.log(y) gera um erro de referência, pois y não foi inicializada.



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

a) **Substituir if (a || b === 0) por if (a === 0 || b === 0)**

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

Resposta: a) Substituir if (a || b === 0) por if (a === 0 || b === 0)


A condição if (a || b === 0) está incorreta porque a é avaliado como verdadeiro se for qualquer valor diferente de 0, null, undefined, false, NaN ou uma string vazia. Isso faz com que a função retorne "Erro: número inválido" mesmo quando a não é 0.
A correção if (a === 0 || b === 0) verifica se a ou b é igual a 0, que é o comportamento desejado.

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

a) O código imprime 1000.

b) **O código imprime 200.**

c) O código imprime 50.

d) O código gera um erro.

Resposta: b) O código imprime 200.


O switch não tem um break após o caso "eletrônico", então o código "cai" no caso "vestuário", onde preco é definido como 200 e o break é encontrado. Portanto, o valor retornado é 200.

______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

d) **24**


Resposta: d) 24


map(x => x * 2) transforma o array em [2, 4, 6, 8, 10].
filter(x => x > 5) filtra os valores maiores que 5, resultando em [6, 8, 10].
reduce((a, b) => a + b, 0) soma os valores do array filtrado: 6 + 8 + 10 = 24.



______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) **["banana", "abacaxi", "manga", "laranja"]**

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

Resposta: c) ["banana", "abacaxi", "manga", "laranja"]


O método splice(1, 2, "abacaxi", "manga") remove 2 elementos a partir do índice 1 (ou seja, "maçã" e "uva") e insere "abacaxi" e "manga" no mesmo local. O array resultante é ["banana", "abacaxi", "manga", "laranja"].
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) **As duas afirmações são verdadeiras, e a segunda justifica a primeira.**

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

Resposta: a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.


A afirmação I é verdadeira porque a herança permite reutilizar código.


A afirmação II é verdadeira porque extends é a palavra-chave usada para implementar herança em JavaScript, justificando a primeira afirmação.
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

a) **I e II são verdadeiras.**

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

Resposta: a) I e II são verdadeiras.


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.


II) O método apresentar() da classe Funcionario sobrepõe o método da classe Pessoa, mas chama o método da classe pai usando super.


III) A afirmação é falsa, pois JavaScript suporta herança de classes.
______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) **A asserção é verdadeira e a razão é falsa.**

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

Resposta: b) A asserção é verdadeira e a razão é falsa.


A asserção é verdadeira, pois o polimorfismo permite que diferentes classes respondam ao mesmo método de formas diferentes.


A razão é falsa, pois JavaScript não suporta sobrecarga de métodos diretamente. O polimorfismo é implementado através de herança e sobrescrita de métodos.

______

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
Código Atualizado:
```javascript
function somaArray(numeros) {
    let soma = 0; // Inicializa a variável soma para evitar erro de variável não definida

    for (let i = 0; i < numeros.length; i++) { // Corrige "size" para "length" e declara "i" com "let"
        soma += 2 * numeros[i]; // Acumula a soma do dobro dos números
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4])); // Saída esperada: 20
```
Explicação:
1.A variável soma foi declarada e inicializada com 0 para evitar erros.


2.O método correto para obter o tamanho do array é length, não size.


3.A variável i foi declarada com let para evitar vazamento de escopo.


4.A soma foi acumulada corretamente usando +=.


______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

Código:
```javascript
class Produto {
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    calcularDesconto() {
        return this.preco * 0.9; // Aplica 10% de desconto
    }
}

class Livro extends Produto {
    constructor(nome, preco) {
        super(nome, preco); // Chama o construtor da classe pai
    }

    calcularDesconto() {
        return this.preco * 0.8; // Aplica 20% de desconto
    }
}

// Exemplo de uso
const produto = new Produto("Caneta", 10);
console.log(produto.calcularDesconto()); // Saída: 9

const livro = new Livro("JavaScript", 50);
console.log(livro.calcularDesconto()); // Saída: 40
```
Explicação:
A classe Produto define um método calcularDesconto() que aplica 10% de desconto.


A classe Livro herda de Produto e sobrescreve o método calcularDesconto() para aplicar 20% de desconto.


A herança permite reutilizar o código da classe Produto na classe Livro, enquanto a sobrescrita de métodos permite modificar o comportamento específico da classe Livro.

