# Orientação a Objestos com Python para iniciantes

Estes conteúdo é baseado nas aulas dos professores, [Andrey Masiero](https://github.com/amasiero) e [Fabio Versolatto](https://www.linkedin.com/in/fabio-versolatto-a9740ba4/?originalSubdomain=br).

## Requerido
Para executar os exemplos utilizados neste repositório você precisa ter o **Python** instalado localmente na sua maquína ou você pode executa-los através do site: [repl.it](https://repl.it)

## O que é Orientação a Objetos?
A **Programação Orientada a Objetos** é um padrão de desenvolvimento de software, voltada para a segurança do software e o reaproveitamento do código, onde teremos a estruturação do código por meio de **classes, métodos e atributos**, que são utilizados para abstrair objetos do mundo real, mas veremos mais deles logo a frente.

## Classe no Python
Para declararmos uma classe no python utilizamos a palavra reservada **class** seguido do nome dela, lembrando que por convenção os nome das classes devem comerça com a primeira letra **Maiúscula**, caso o nome seja composto seguimos o mesmo modelo deixando a primeira letra de cada palavra **Maiúscula**.

Exemplo 1:
```python
# Classe com nome simples
class Veiculo:
```
No exemplo acima temo a classe veículo, lembrando que o nome da classe sempre deve começar com letra **Maiúscula**.

Exemplo 2:
```python
# Classe com nome composto
class CalcularVelocidade:
```
No exemplo acima temo a classe calcular velocidade, lembrando que cada palavra do nome da classe deve começar com a primeira letra **Maiúscula**.

## Atributos 
No python temos algums tipos de atributos, mas neste guia de estudo iremos focar, no **privado** e o **público**, mas não se preocupe iremos ver cada um deles separadamente. Mas você deve está se perguntando **"O que é atributos?"**, atributos nada mais é que as caracteristicas do objeto do mundo real, no nosso exemplo a classe veículo, possue alguns atributos que iremos adicionar a classe dele.

Exemplo 1:
```python
# adicionando atributos publicos para veiculo
class Veiculo:
  cor = None      # este é um atributo de cor que a grande maioria dos veiculos possuem
  tipo = None     # este é um atributo de tipo que pode ser (Terrestre, Náutico, Aéreo)
```

O atributos declarado na classe acima são do tipo público e estamos atribuíndo a eles a palavra **None** já que o python não nos permite criar atributos ou varíaveis sem atribuir um valor a elas, agora iremos mostrar os mesmo sendo do tipo privado.

Exemplo 2:
```python
# adicionando atributos privados para veiculo
class Veiculo:
  __cor = None      # este é um atributo de cor que a grande maioria dos veiculos possuem
  __tipo = None     # este é um atributo de tipo que pode ser (Terrestre, Náutico, Aéreo)
```
Note que os atributos agora estão acompanhado de dois underline, antes do nome deles, assim estamos idetenficando esses atributos como privado em nosso código, e estamos atribuíndo a eles a palavra **None** já que o python não nos permite criar atributos ou varíaveis sem atribuir um valor a elas.

## Métodos
Metodos são a forma com que as classe se relaciona com outras classes, para definirmos um methodo usamos a palavra reservada **def** seguinda do nome do método, ainda utilizando a classe veículo iremos criar dois métodos, um privado e outro público.

Exemplo 1:
```python
# adicionando metodos publicos para veiculo
class Veiculo:
  cor = None      # este é um atributo de cor que a grande maioria dos veiculos possuem
  tipo = None     # este é um atributo de tipo que pode ser (Terrestre, Náutico, Aéreo)

  def ligar(self):
    print('Veículo ligado...')

  def __ignicaoDoMotor(self): # O que é esse bentido self?
    print('Girando ignição')

```
Note que é bem parecido com a criação de funções no python, caso você ainda não saiba criar funções no python recomendo que leio o primeiro post desse guia de estudo clicando neste link: [Pytho para Iniciantes](https://medium.com/@alexandredossantossoares/python-para-iniciantes-6394d6a86f50), note que a única diferença entre uma função normal no python e um método é a palavra **self** que está dentro dos parenteses do método.

**O que é o self?**
O **self** por via de regra o python utiliza o a palavra **self** como primeiro parâmetro do método, e também existe vantagens em utilizar o **self** como ele podemos, invocar métodos de classes herdadas, mas iremos falar de herença mais pra frente, mas por via de regra **SEMPRE USE O self COMO PRIMEIRO PARÂMETRO DO MÉTODO** .


## Herança
Herança como o proprio nome diz é algo que herdamos de outra pessoas ou classes, isso mesmo por meio da herança podemos nos beneficiar que métodos e atributos que estão disponíveis em outra classe, para demostrar o conceito de herança iremos utilizar como exemplo uma nova classe chamada de pessoa.


Exemplo 1:
```python
# criando a classe pessoa 
class Pessoa:
  nome = None
  idade = None
  sexo = None
  dataNascimento = None
```

Na classe acima declaremos os atributos mais comuns de uma pessoa, agora mais imagina que nosso sistema terá uma classe chamada funcionário, que também é uma pessoa então teriamos que reescrever todos os atributos da classe pessoa para funcionário mas com a herança podemos herda esses atributos.

Exemplo 1: Sem utilizar herança 
```python
# criando a classe funcionário sem herança 
class Funcionario:
  nome = None
  idade = None
  sexo = None
  dataNascimento = None
  funcao = None
  dataAdmissao = None
  numeroCracha = None
```

Exemplo 2: Utilizando herança 
```python
# criando a classe funcionário sem herança 
class Funcionario(Pessoa):
  funcao = None
  dataAdmissao = None
  numeroCracha = None
```

Note que só tivemos que escrever aquilo que realmente precisavamos na classe, é para herda os atributos tivemos apenas que colocar os pararentes depois do nome da classe e passar o nome da classe que queremos herda.

*Caso você esteja utilizando as classes acima em documentos separado na classe funcionário você precisará **importar** a classe **pessoa** para fazer esse importe basta adicionar a linha de codigo abaixo no começo do arquivo funcioanrio

```python
from pessoa import Pessoa
```

O importe funciona com uma regrinha básica, primeiro a palavra reservada **from** seguinda do **nome do arquivo** depois **import** **nome da classe**


## Instância da Classe
A instância da classe nada mais é que a utilização dela, no código, no exemplo abaixo iremos mostrar com utilizar uma classe.

Exemplo 1:
```python
# criando a classe pessoa 
class Pessoa:
  nome = None
  idade = None
  sexo = None
  dataNascimento = None


joao = Pessoa()
joao.nome = "João da Silva"
joao.idade = 25
joao.sexo = "M"
joao.dataNascimento = "25/05/1994"

print(joao.nome)            # saída "João da Silva"
print(joao.idade)           # saída 25
print(joao.sexo)            # saída "M"
print(joao.dataNascimento)  # saída "25/05/1993"

```


## Contribuir
Caso você tenha interesse, faça um fork do projeto e ajude-nos a mater esse guia para iniciantes

## Autor
[Alexandre dos Santos Soares](https://github.com/alexandrejuk)