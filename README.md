# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro - correta

**A variável x é declarada como undefined pois seu valor ainda não foi atribuído. A variável y não é acessável antes da linha "let y = 10", o que define um erro.**

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log


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

a) Substituir if (a || b === 0) por if (a === 0 || b === 0) - correta

**Essa é a substituição correta, pois na verificação do enunciado, o operador "===" tem preferência ao operador "||", sendo assim, a leitura de "b===0" é realizada prioritariamente, o que sempre retornará o valor 0.**

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

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

b) O código imprime 200. - correta

**O código imprime 200 pois não existe um "break" no case "eletrônico", sendo assim, a leitura do switch é feita, porém a verificação se o tipo for eletronico é ignorada pela falta do break, o que faz a leitura continuar e parar no tipo vestuário.**

c) O código imprime 50.

d) O código gera um erro.

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

d) 24 - correta

**A saída é 24. O primeiro método ".map(x => x*2)" multiplica todos os valores do array por 2.
O segundo método ".filter(x => x>5) filtra todos os números maiores que 5.
O terceiro método ".reduce((a, b) => a+b, 0)" soma todos os elementos restantes do array, começando com 0).**
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"] - correta

**O método ".splice" remove e altera o conteúdo de uma lista. O primeiro valor do método (1) indica qual posição iniciar a troca, o segundo valor (2) indica quantos elementos serão trocados. Os nomes "abacaxi" e "manga" serão os substitutos dos elementos retirados.**

d) ["banana", "maçã", "uva", "abacaxi", "manga"]
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira. - correta

**A palavra extends é a forma como a herança é implementada na linguagem, sendo assim, ela é a justificativa da primeira.**

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.
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

a) I e II são verdadeiras. - correta

**A classe funcionário herda de pessoa corretamente ao utilizar "extends", sendo assim pode acessar os atributos nome e idade.**

**O método apresentar de funcionário sobrepõe o método apresentar de pessoa, pois os dois métodos têm o mesmo nome por isso a sobreposição. Além disso, o método apresentar da classe funcionário chama o método da classe pai usando o "super", com isso, a escrita no console do método apresentar da classe pessoa aparece primeiro.**

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa. - correta

**O conceito de polimorfismo permite que um mesmo método tenha saídas diferentes devido às classes, sendo assim o comportamento de um método muda dependendo do tipo de objeto.**

**O método de sobrecarga não é suportado por JavaScript.**

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

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
**O código correto é:**

```javascript
function somaArray(numeros) {

    var soma = 0; //a variavel soma deve ser inicializada com 0

    for (i = 0; i < numeros.length; i++) { //numeros.size não existe, o correto é numeros.length
        soma += 2 * numeros[i]; //a variavel soma deve ser incrementada com o valor do array multiplicado por 2
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

**Um exemplo prático para os descontos é:**
```javascript
class Produto { //classe pai, que contem os atributos e metodos comuns a todos os produtos
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }
    calcularDesconto() { //método que calcula o desconto
        return this.preco * 0.9;
    }
}

class Livro extends Produto { //classe filha, que herda os atributos e métodos da classe pai
    constructor(nome, preco) {
        super(nome, preco); //chama o construtor da classe pai
    }

    calcularDesconto() { //sobrescreve o método calcularDesconto da classe pai
        return this.preco * 0.8; //calcula o desconto de 20%
    }
}
```
