# Program��o Orientada a Objetos


#####Aviso!
Esse � um guia r�pido sobre o paradigma de orienta��o a objetos, ent�o pode (e provavelmente vai) faltar informa��o ou detalhamento em determinados aspectos. No entanto, para aqueles com d�vidas sobre o uso de orienta��o a objetos em Python ou sobre a orienta��o a objetos em si, esse guia pode ser de alguma ajuda.
Para um melhor aprendizado sobre programa��o orientada a objetos, cheque as refer�ncias.
#####Programa��o Estruturada
O paradigma de programa��o estruturado enfatisa o uso de subrotinas, la�os de repeti��o, condicionais e estruturas em bloco na solu��o de problemas.
Basicamente, as subrotinas s�o escritas e aplicadas a um determinado tipo de informa��o. Por exemplo:

```python
def acharletra(string, letra):
	cont = 0
	for char in string:
		if char == letra:
			return cont
		else:
			cont += 1
	return -1
```
Dados uma string e um caractere, o c�digo acima encontra a primeira ocorr�ncia do caractere na string e retorna o �ndice dessa ocorr�ncia. Por exemplo:

```python
st = "Isac � lindo"
print(acharletra(st, '�'))
>>> 5
```

Apesar de ser uma fun��o �til, podemos observar que ela n�o term utilidade para, por exemplo, um objeto n�o iter�vel, como um inteiro, um float, um booleano...
Se imaginarmos os tipos de dados como objetos palp�veis da vida real, temos que o controle das funcionalidades desses objetos est�o sempre separados deles. � como ter, por exemplo, um *microondas* e, separadamente, um bot�o ou interrupetor que o liga, mas que n�o faz parte do *microondas*.
A programa��o orientada a objetos tenta aproximar a programa��o da vida real nesse aspecto.
#####Programa��o Orientada a Objetos
Na programa��o orientada a objetos, as fun��es que os objetos podem cumprir est�o acopladas a eles, s�o chamadas de m�todos.
No exemplo anterior, por exemplo, uma vari�vel do tipo *microondas* teria um m�todo respons�vel pelo seu ligamento, outro m�todo respons�vel pelo desligamento, outro respons�vel pelo controle do contador, da pot�ncia... e assim sucessivamente. Na programa��o orientada a objetos, as funcionalidades dos tipos de objetos s�o seus m�todos.
Assim como funcionalidades, objetos da vida real tamb�m possuem caracter�sticas, podendo essas serem, ou n�o, mut�veis. Um objeto do tipo microondas, por exemplo, poderia ter as caracter�ticas volume, peso, capacidade... em programa��o orientada a objetos, essas caracter�sticas tamb�m est�o acopladas ao objeto e s�o chamadas de atributos.

#####Caracter�sticas da POO
As caracter�sticas principais da programa��o orientada a objetos s�o a **Abstra��o**, **Heran�a**, **Polimorfismo** e **Encapsulamento**.

**Abstra��o**:� utilizada para a defini��o de entidades do mundo real. Sendo onde s�o criadas as classes. Essas entidades s�o consideradas tudo que � real, tendo como considera��o as suas caracter�sticas e a��es.
Em Python, a palavra _class_ � reservada a cria��o de Classes (objetos).

| Entidade | Caracter�sticas | A��es |
|:--------|:---------------|:-----|
| carro   | tamanho, cor, peso, altura | acelerar, parar, ligar, dirigir |
| elevador | tamanho, peso m�ximo | subir, descer, escolher andar |
| conta banc�ria | saldo, limite, n�mero | depositar, sacar, ver extrato |


```python
class Conta:
	def __init__(self, saldo, limite, num):
		self.saldo = saldo
		self.lim = limite
		self.num = num
	
	def depositar(self, valor):
		if self.saldo + valor < self.lim:
			self.saldo += valor
		else:
			print("Sua conta n�o tem limite suficiente")
	
	def sacar(self, valor):
		if self.saldo >= valor:
			self.saldo -= valor
		else:
			print("Voc� n�o tem saldo suficiente")
	
	def ver_extrato(self):
		print(self.saldo)
```

Por exemplo, acima, a abstra��o do objeto Conta Banc�ria.

**Heran�a**: O significado de heran�a � similar ao significado usado no mundo real, onde filhos herdam certas caracter�sticas dos pais. Em programa��o orientada a objetos, um objeto pode herdar atributos e m�todos de um outro objeto, sendo a classe herdeira chamada subclasse e a classe pai chamada superclasse.
Uma das grandes vantagens da heran�a � a reutiliza��o de c�digo, ideal para quando h� classes que compartilham de um mesmo atributo ou m�todo.

![Hierarquia de Classes](https://img-21.ccm2.net/TFkixX1LWid1t6x1h3AancR9t-I=/56fc4b0ee402409cad1d4294085ab1f7/ccm-encyclopedia/poo-images-animaux2.gif)
######No esquema de classe acima, Animal � a superclasse da qual Herb�voro e Carn�voro herdam caracter�sticas. A classe herbivoro herda caracter�sticas de ambas, Herb�voro e Carn�voro.

Em Python 3, todos os objetos herdam caracter�sticas da classe built-in object.

**Polimorfismo**: Polimorfismo est� relacionado com heran�a, de modo que representa a possibilidade de sobrescritura de m�todos e atributos.
Duas classes distintas podem ter m�todos que compartilham o mesmo nome, mas que funcionam de maneira diferente, ou possuem par�metros diferentes.

**Encapsulamento**: � a ideia de esconder do usu�rio determinadas ideias ou detalhes internos, tornando partes do sistema o mais independente poss�vel. Imagine, por exemplo, um controle remoto de televis�o. Quando um usu�rio assistindo TV pressiona o bot�o de mudan�a de canal, n�o importa para o usu�rio o processo que faz com que a televis�o troque de canal, apenas que ela execute a sua fun��o com sucesso. Esse � um exemplo de encapsulamento.

#Objetos em Python - Guia Rel�mpago

Para declarar um novo objeto em Python, usa-se a palavra reservada _Class_ seguida pelo nome da classe.
Caso a classe que voc� est� declarando herde caracter�sticas de uma ou mais classes j� existentes, ap�s declarar o nome da classe, entre par�ntesis, voc� deve declarar as classes da qual ela herda caracter�sticas.

```python
class Coisa():
```
Ou ainda:

```python
class OutraCoisa(Coisa):
```

A primeira classe � uma superclasse, n�o herda caracter�sticas de nenhuma outra classe. J� a classe OutraCoisa herda caracter�sticas da classe Coisa, sendo ent�o uma subclasse desta.

O momento de instancia��o de uma vari�vel � o momento em que a vari�vel passa a existir. Se essa vari�vel for um objeto, essa instancia��o acontece atrav�s de um m�todo especial (dunder methods, magic methods). M�todos especiais s�o m�todos com caracter�sticas especificas de Python, eles s�o marcados por dois underlines antes e depois do nome.
O m�todo especial que controla o momento de instancia��o de uma vari�vel � o init.

```python
class Funcionario():
	def __init__ (self, nome, idade, cpf, matricula):
		self.nome = nome
		self.idade = idade
		self.cpf = cpf
		self.matricula = matricula
```