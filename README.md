# GlossarioPOO
Índice
========

   * [Construtor](#constructor)
   * [Instanciação](#instanciação)
   * [Getters/Setters](#getters-e-setters)
   * [Assinatura de método](#assinatura-de-metodo)
   * [Sobrecarga de método](#sobrecarga-de-metodo)
   * [Escopo de classe](#escopo-de-classe)
   * [Escopo de objeto](#escopo-de-objeto)
   *  [Palavra reservada new](#palavra-reservada-new)
   * [Palavra reservada instanciof](#palavra-reservada-instanciof)
   * [Palavra reservada this](#palavra-reservada-instanciof)
   * [Palavra reservada public/private](#palavra-reservada-public-e-private)
   * [Palavra reservada final](#palavra-reservada-final)
   * [Relacionamento de dependência](#relacionamento-de-dependencia)
   * [Relacinamento de Agregação](#relacionamento-de-agregacao)
   * [Relacionamento de Composição](#relacionamento-de-composicao)
   
Descrição
========

Glossário de conceitos da programação orientada a obejetos, atividade da aula de Programação orientada a objetos do curso Engenharia de Software - Univille.

Constructor
========
Constructors são blocos de códigos que inicializam um objeto. Um construtor tem o mesmo nome da classe a ser inicializada, e pode ter ou não ter parâmetros de inicialização. 
**Exemplo:**
```java
public class ticketMachine {
	
	private int qtdSenha;
	private int senhaAtual;
	
	
	public ticketMachine() {
		this.qtdSenha = 100;
		this.senhaAtual = 1;
	}
	
	public ticketMachine(int qtdSenha) {
		this.qtdSenha = qtdSenha;
		this.senhaAtual = 1;
	}
```
O primeiro constructor está se referindo a classe TicketMachine, mas sem usar nenhum parâmetro, então quando no arquivo Main, usar o constructor sem parâmetros para iniciar a classe, a quantidade de senhas será a definida pelo sistema. o segundo constructor está iniciando a classe TicketMachine usando como parâmetro, a a quantidade de senhas que a maquina usará, sendo assim quando se iniciar a classe no Main usando esse constructor, a quantidade de senhas deve ser informado.

Instanciação
========
Instanciar uma classe significa criar um objeto daquela classe, ou seja: objeto é o conjuto de atributos e métodos da classe. Métodos são 'Funções' que alteram o comportamento dos objetos.
**Exemplo:**
```java
public class Main {
	
	public static void main(String[] args) {
        //Instanciação da classe car
		Car porshe = new Car();
    }
}
```
Getters/Setters
========
Getters pegam um valor contido em uma váriavel definida como privada, é usando um método publico Get para conseguir acesso ao valor dessa váriavel.
Setters definem o valor de uma váriavel privada, é usado um metodo publico Set para se definir o valor de uma váriavel definida como priváda.
**Exemplo:**
```java
public String getNome() {
		return nome;
	}
public void setNome(String nome) {
		this.nome = nome;
	}

```
Usasse "This" dentro do método para informar qual váriavel se está referindo, sendo uma local e uma do método.

Assinatura de método
========
Assinatura de método é tudo que não é o corpo do método, geralmente, retorno, nome, parâmetros e também o nível de acesso (private, public...). Isso serve para se dár uma identidade ao método. Em uma linguagem onde vários métodos podem ter nomes iguais, precisa se definir qual deles é qual. Sendo assim, se usa a assinatura de método. Dois métodos não podem pertencer a mesma classe e terem suas assinaturas exatamente iguais.
**Exemplo:**
```java
int FazAlgumaCoisa() { // faz alguma coisa aqui }

int FazAlgumacoisa(int valor) { // faz alguma coisa aqui }

```

Sobrecarga de método
========
Sobrecarga de método se dá quando dois métodos ou mais contém o mesmo nome, porém com diferente retorno ou tipos de parâmetros.
```java
//Method overload, same method, different parameters.
public class methodOverloading {
	public static int calculateScore(String playerName, int score) {
		System.out.println("Player " + playerName + " Scored: " + score + " Points");
		return score * 1000;
	}
	public static int calculateScore(int score) {
		System.out.println("Player Scored: " + score + " Points");
		return score * 1000;
	}
}
```
Escopo de classe
========
No escopo de classe, um atributo ou método existe apenas na classe em que ele foi definido.
Para representar um escopo de classe no Java, se utiliza *Static*
**Exemplo:**
```java
public class Main {

    // variavel de classe
    public static int score = 5;
    
    // metodo de classe
    public static void score() {
    }
}
```

Escopo de objeto
========
Caso não seja utilizada a palavra *static*, se define como Escopo de objeto qualquer atributo ou método criado.

Palavra reservada new
========
*New*, tem por função instânciar um objeto a partir de uma classe, podendo ser instânciado por uma váriavel ou não.

Palavra reservada instanciof
========
*instanceof* compara se um objeto pertence ao mesmo tipo de determinada classe especificada. retorna-se um valor booleano na comparação.
**Exemplo:**
```java
public class cao {
    cao doberman = new cao();
    //Boolean
    boolean resultado;
    resultado = (doberman instanceof cao);
    }
```

Palavra reservada this
========
*This* é utilizado por um objeto para se referenciar a ele mesmo. Utilizado dentro de métodos para fazer referência a atributos do próprio objeto.

**Exemplo:**
```java
public String getModel() {
		return this.model;
	}
```

Palavra reservada public/private
========
Palavras usadas para se definir a visibilidade de um atríbuto ou método ou classe.
*Public* usado para definir que um atríbuto ou método ou classe é visivel para o sístema todo e para qualquer classe do sistema.
*Private* é usado para se definir que um atríbuto ou método é vísivel apenas na própria classe, assim bloquando a alteração de dados ou comportamentos por outras classes.
**Exemplo Public:**
```java
public class Account{
    //Exemplo de váriaveis publicas, acessiveis e modificaveis por diversas classes.
    public double accBalance;
    public String name;
}
```
**Exemplo Private:**
```java
public class Account {
    //Exemplos de váriaveis privadas que podem ser modificadas apenas pela classe Account.
	private double accBalance;
	private String name;
}
```


Palavra reservada final
========
*Final*, utilizada em valores constantes, ou seja, que são imutaveis, somente leitura.
Pode ser usado por uma classe que não poderá ser sobescrita ou uma váriavel que não será mudada durante o processo.

```java
//Classe final
final class Final{
    //Variavel final
    final int HorasdoDia = 24;
}

```

Relacionamento de dependência
========
Quando uma classe depende da instancia de outra classe para funcionar, é chamado de relacionamento de dependência. Sendo o objeto recebido como argumento pela classe, para funcionar.
```java
public class DVD-PLAYER
{
//Sendo DVD-MIDIA, outra classe.
 public play(DVD-MIDIA filme){
 }
}
```
Relacinamento de Agregação
========
Uma classe composta por outra classe é um relacionamento de agregação, porém na agregação, um objeto que compõe a classe pode ser utilizado por outras instancias, na agregação, com uma associação parte-todo, mesmo sem o todo, a parte pode continuar a existir.
Na agregação, outras classes podem obter a referência dos objetos que compõem a classe, usando geralmente os métodos getters.  

**Exemplo agregação:**  
![Alt text](https://i.imgur.com/GkJTUr0.gif "Exemplo agregação")

Relacionamento de Composição
========
Composição é um tipo de associação mais forte que a agregação, pois a composição é um relacionamento caracterizado como parte-todo, mas em caso de composição o todo, ele é responsável pelo ciclo de vida da parte, sendo assim a composição é aplicada quando a parte não faz sentido existir sem o todo e quando o objeto que representa o todo for destruido a parte também deverá ser destruída.   
**Exemplo Composição:**  
![Alt text](https://i.imgur.com/ABAYOZf.gif "Exemplo agregação")
