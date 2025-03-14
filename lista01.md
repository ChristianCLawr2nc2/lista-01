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
==> a) A saída será undefined seguido de erro 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

**R)** A resposta é a letra "a", porque ao rodar o código a var é puxada para o topo do código fazendo a var X ser nomeada porém sem um valor ainda que só foi definido após o console.log assim tendo a saída undefined. Já o erro ocorre porque uma let não pode ser usada antes da linha que contem o comando y = 10.

___
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

==> b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

**R)** A "b" é a correta porque essa correção no código fará com que o if compare de verdade se (a === 0) e (b === 0) fazendo tudo fucionar com a lógica correta.

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

==> b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

**R)** A saída será o número 200 porque no switch quando você coloca um case e não escreve no final do case o "break" ele sobrescreverá o próximo emcima do anterior fazendo com que o "preco" eletrônico seja 200 e não 1000.

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

==> d) 24

**R)** A alternativa correta é a "E" porque no array a função .map multiplica cada elemento do array por 2, a .filter vai deixar apenas os números maiores que 5 no array e a . reduce vai soma-los começando do 0.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

==> c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

**R)** A resposta é a "C" porque na função .splice aplicada no array funciona da seguinte forma, (1 = elemento que inicia a substituição, 2 = n° de elementos a ser substituidos, termos que vão substituir) assim dando o array da alternativa "C".
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


==> a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

**R)** A resposta é a "A" porque a segunda afirmação diz o comando que permite que classes filhas usem métodos e propriedades herdados de classes pais.
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

==> a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

**R)** A resposta é alternativa "A".

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

==> b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

**R)** A asserção é verdadeira porque o conseito está certo já que sim objetos diferentes podem responder a mesma função. A razão está errada porque o javascript não tem suporte para o método de sobrecarga de classes nativamente.

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

**R)** 
```javascript
function somaArray(numeros) {

    let soma = 0

    for (let i = 0; i < numeros.length; i++) {
        soma += 2 * numeros[i];
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
**R)**
```javascript
class Produto {
    
    constructor(nome, preco) {
      this.nome = nome;
      this.preco = preco;
    }
  
    // Método para calcular desconto padrão (10%)
    calcularDesconto() {
      return this.preco * 0.90;
    }
  }
  
  class Livro extends Produto {
    constructor(nome, preco, autor) {
      super(nome, preco); // Chama o construtor da classe pai (Produto)
      this.autor = autor;
    }
  
    // Sobrescrevendo o método calcularDesconto() para aplicar 20%
    calcularDesconto() {
      return this.preco * 0.80;
    }
  }
  
  // Criando instâncias e testando
  const produtoGeral = new Produto("Smartphone", 2000);
  console.log(`Preço do ${produtoGeral.nome} com desconto: R$ ${produtoGeral.calcularDesconto().toFixed(2)}`);
  
  const livro = new Livro("O Senhor dos Anéis", 100, "J.R.R. Tolkien");
  console.log(`Preço do livro "${livro.nome}" com desconto: R$ ${livro.calcularDesconto().toFixed(2)}`);
```

 A classe pai(Produto) cria o constructor onde define nome e preço e depois o método de calcular o desconto de 10%, então implementa a subclasse filha(Livro), que vai herdar as definições de nome e preço mas sobrescrever a função de calcular o desconto agora para 20% que será apenas usado em Livros.
