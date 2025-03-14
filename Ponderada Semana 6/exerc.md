# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

**Reposta: A**

**Justificativa:** 

No JavaScript, quando usamos `var`, a variável existe antes de ser declarada, mas ainda não tem valor. Por isso, `console.log(x);` mostra `undefined`. 

Já `let` só começa a existir depois da sua declaração. Como `console.log(y);` aparece antes da linha `let y = 10;`, o código gera um erro.

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

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

**Reposta: A**

**Justificativa:** 

O operador `||` significa "ou", mas a forma como está escrito faz com que só `b === 0` seja corretamente comparado, enquanto `a` sozinho será avaliado como verdadeiro ou falso sem verificar se é zero. 

Para corrigir, a condição correta deve ser `if (a === 0 || b === 0)`, garantindo que tanto `a` quanto `b` sejam comparados corretamente com zero.

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

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

**Reposta: A**

**Justificativa:** 

O problema no código está no switch, pois falta a instrução break; após o primeiro caso (case "eletrônico":).

O código entra no caso "eletrônico" e atribui 1000 à variável preco.
Porém, como não há break;, o código continua executando o próximo caso (case "vestuário":) e substitui preco para 200.
Depois, ele encontra break;, interrompendo a execução e retornando o valor 200.
Se houvesse um break; após preco = 1000;, a saída seria 1000. Mas, como não há, o valor final retornado é 200.

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

d) 24

**Reposta: D**

**Justificativa:** 

1. `map(x => x * 2)` multiplica cada número por 2.

2. O array original `[1, 2, 3, 4, 5]` vira `[2, 4, 6, 8, 10]`. `filter(x => x > 5)` mantém apenas os números maiores que 5.

3. O novo array será `[6, 8, 10]`. `reduce((a, b) => a + b, 0)` soma todos os valores do array. `6 + 8 + 10 = 24`.

______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

**Reposta: C**

**Justificativa:** 

O método `.splice()` modifica um array removendo ou adicionando elementos. O método começa na posição 1 (ou seja, remova a partir de "maçã") e insire "abacaxi" no seu lugar. A mesma coisa aplica para a posição 2.

______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

**Reposta: B**

**Justificativa:** 

Afirmativa 1: A herança em JavaScript permite que uma classe reutilize métodos e propriedades de outra. Isso evita repetição de código e facilita a manutenção.

Afirmativa 2: Em JavaScript, a palavra-chave `extends` é usada para criar uma classe que herda de outra.

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

a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

**Reposta: A**

**Justificativa:** 

Afirmativa 1: A classe `Funcionario` herda da classe `Pessoa` usando `extends`, o que permite que `Funcionario` acesso direto às propriedades `nome` e `idade`.

Afirmativa 2: O método `apresentar()` em `Funcionario` substitui o da classe `Pessoa`, mas usa `super.apresentar();` para chamar o método da classe pai antes de adicionar novas informações.

Afirmativa 3: O JavaScript suporta herança de classes, então essa afirmação está errada.

______
**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

**Reposta: B**

**Justificativa:** 

A asserção é verdadeira porque o conceito de polimorfismo na Programação Orientada a Objetos permite que diferentes classes respondam ao mesmo método de maneiras diferentes.

A razão é falsa porque JavaScript não tem sobrecarga de métodos.

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

**Código corrigido:**
```javascript
function somaArray(numeros) {
    let soma = 0; // Inicializa a soma corretamente

    for (let i = 0; i < numeros.length; i++) { // 'size' não existe em arrays, o correto é 'length'
        soma += 2 * numeros[i]; // Deve somar cada valor ao invés de sobrescrevê-lo
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4])); // Saída esperada: 20
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

**Exemplo prático:**
```javascript
// Classe Produto (Classe Pai)
class Produto {
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    calcularDesconto() {
        return this.preco * 0.90; // Aplica 10% de desconto
    }
}

// Classe Livro (Herda de Produto e modifica o desconto)
class Livro extends Produto {
    constructor(nome, preco, autor) {
        super(nome, preco); // Chama o construtor da classe pai
        this.autor = autor;
    }

    calcularDesconto() {
        return this.preco * 0.80; // Aplica 20% de desconto
    }
}

// Criando objetos e testando os métodos
const produto = new Produto("Cadeira", 200);
console.log(`Preço com desconto: R$ ${produto.calcularDesconto().toFixed(2)}`); // R$ 180.00

const livro = new Livro("The Cat in the Hat", 100, "Dr. Seuss");
console.log(`Preço do livro com desconto: R$ ${livro.calcularDesconto().toFixed(2)}`); // R$ 80.00
```

**Explicação:**

A classe `Produto` contém os atributos nome e preco. O método `calcularDesconto()` aplica um desconto de 10% ao preço.

A classe `Livro` (herda de `Produto`) usa `extends Produto` para herdar os atributos e métodos da classe Produto. O método `super(nome, preco);` chama o construtor da classe pai. O método `calcularDesconto()` é sobrescrito para aplicar um desconto maior (20%).