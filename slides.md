# SOLID

Princípios de design de software orientado-a-objetos

Daniel Teixeira &mdash; Caiena Software <!-- .element: data-footer="1" -->

Note:
Apresentação

Quem conhece SOLID?

Construção de programas/sistemas OO

"Especificamente, para o Design (next) desses sistemas"



# Design

Note:
O que significa design de software?

Tradução pra design?

Qual a definição formal?

"Sem uma definição clara, fica difícil responder (next)"



# Design <!-- .element: data-header="1" -->

O que é um bom design?

Note:
Como avaliar um design como bom ou ruim?

Qual critérios levar em consideração nessa avaliação?

Desgin bom é difícil definir, porém...

"(next) Às vezes, é bem fácil identificar um design ruim"



# Design <!-- .element: data-header="1" -->

![Engineering fail](/images/engineering-fail.jpg)

Note:
É difícil definir objetivamente

É necessário um contexto para poder ter critérios

O contexto é construção de software orientado-a-objetos



# Design em OO <!-- .element: data-header="1" -->

Abstração <!-- .element: class="fragment" -->

Encapsulamento <!-- .element: class="fragment" -->

Reuso <!-- .element: class="fragment" -->

Note:
No contexto de OO, design visa manter os conceitos: Abstração, Encapsulamento e
Reuso

Manter a estrutura do software para ser: Flexível, Fácil manutenção e Reutilizável



## Design ágil em OO <!-- .element: data-header="1" -->

#### Aceitar mudanças <!-- .element: class="fragment" -->

Note:
Tudo isso, para que o software possa aceitar mudanças

Nós, como engenheiros de softwares, não podemos negar o fato que o código muda

Aliás, foi pra isso que criamos orientação-a-objetos, para poder escrever
softwares que possam ser alterados (de maneira mais simples e segura)

E foi nesse contexto que surgiu o desenvolvimento ágil



### O Grande Incêndio de Londres <!-- .element: data-header="1" -->

![The Great Fire of London](/images/Great_Fire_London.jpg)

1666 <!-- .element: data-footer="1" -->

Note:
Em 1666, aconteceu o grande incêndio de londres

Um incêndio de 5 dias, que começou na padaria de Thomas Farriner, queimou cerca
de 4/5 de Londres



### Design de Londres

![Wren's Plan](/images/wren-plan.jpg)

Christopher Wren


### Design de Londres

![Evelyn's Plan](/images/evelyn-plan.jpg)

John Evelyn


### Design de Londres

![Hooke's Plan](/images/hooke-plan.jpg)

Robert Hooke



# Qual foi o Design escolhido?



# NENHUM!



## Reconstruída incrementalmente

Note:
Foi reconstruída a partir das necessidades

> Sem design pré-definido

> Construído incrementalmente

(next)



## Primeiro projeto ágil

Note:
Ou seja, projetos ágeis, são construídos incrementalmente

Sem uma definição fechada previamente definida

Atendendo a alterações de definições no percurso do desenvolvimento



## Design ágil em OO <!-- .element: data-header="1" -->

* Evolução incremental do design

* Design feito para o código atual

* *Design não é uma etapa, é um processo contínuo* 

Note:
Nesse sentido, o design ágil é aplicado de forma incremental

Buscando manter os conceitos do paradigma de programação

A partir do código que se tem HOJE

Sem pensar muito em alterações futuras



## Design ágil em OO <!-- .element: data-header="1" -->

>  Poor dependency managment leads to code that is hard to change, fragile, and
>  non-reusable.

<small>Robert C. Martin - The principles of OOD <br />
http://butunclebob.com/ArticleS.UncleBob.PrinciplesOfOod</small> <!-- .element: data-footer="1" -->

Note:
Em OO, para que um software aceite alterações mantendo os conceitos do
paradigma, precisamos gerenciar as dependências dos objetos

Entenda como dependência: as relações entre as entidades do sistema

Nosso design volta-se principalmente para as dependências

O SOLID apresenta princípios que ajudam a aplicar um design OO bom



### Carro depende de Motor <!-- .element: data-header="1" -->
<br /><br />
![Dependência](/images/associacao.png)

_**Carro** pode chamar métodos em objetos de **Motor**_

Note:
Em UML, utilizamos uma seta de traços para desenhar uma dependência

A direção da seta, indica quem depende do que

Isso significa que objetos do tipo Carro conhecem objetos Motor

Alterações no Motor podem resultar em alterações no Carro



### Carro depende de Motor <!-- .element: data-header="1" -->

![Herança](/images/heranca.png) <!-- .element: style="float: left; margin-right: 30px;" -->
<br />

<!-- .element: style="text-align: left" --> _**Carro** herda de **Veiculo**_

<!-- .element: style="text-align: left" --> _**Carro** depende da implementação de **Veiculo**_

Note:
Esse é outro tipo de dependência

Carro depende da implementação de Veiculo



## Dependências <!-- .element: data-header="1" -->
<br />
![Uma dependencia](/images/uma-dependencia.png)

Note:
Se houver alteração em A, quem é afetado?

Se houver alteração em Base, quem é afetado?



## Dependências <!-- .element: data-header="1" -->
<br />
![Várias dependencia](/images/varias-dependencias.png)

Note:
Se houver alteração em X, quem é afetado?

Se houver alteração em A, quem é afetado?



## Dependências <!-- .element: data-header="1" -->
<br /><br />
![Dependencias aninhadas](/images/dependencias-aninhadas.png)
<br /><br /><br /><br />

Note:
Se houver alteração em B, quem é afetado?

Se houver alteração em G, quem é afetado?



# SOLID <!-- .element: data-header="1" -->
_Design smells_
<br /><br />

* Rigidez                    &mdash; Difícil de alterar
* Fragilidade                &mdash; Fácil de quebrar
* Imobilidade                &mdash; Difícil reuso
* Viscosidade                &mdash; Difícil de fazer certo
* Complexidade desnecessária &mdash; Overdesign
* Repetição desnecessária    &mdash; Non-DRY
* Opacidade                  &mdash; Expressividade desorganizada

Note:
A forma como essas dependências são declaradas, pode levar a esses _design smell_

Geralmente, esses sintomas de design ruim surgem por não praticar os princípios
de design

O SOLID ajuda a resolver esses pontos de design ruim



![SRP](images/srp.jpg)

Uma classe deveria ter apenas um motivo para ser alterada

Note:
A definição desse princípio foi evoluindo com tempo

Inicialmente, ele era definido como: "Uma classe deve fazer apenas uma coisa e
fazer isso bem"

Essa definição estava muito mais próximo do que é coesão (relação funcional dos
elementos de um módulo)

A definição por motivos a ser alterada, deixa o princípio mais próximo de como
ele resolve os Design Smells como Fragilidade.



# SRP <!-- .element: data-header="1" -->

![Jogo](/images/srp-jogo.png)

Note:
Considerando um jogo de Truco, em que a cada jogada (ou rodada) você pode fazer
pontuações diferentes (1, 3, 6, etc...)

A classe JogoTruco calcula quantos pontos aquela jogada rendeu e renderiza na
tela a pontual acumulada

Essa classe acumula responsabilidades diferentes

Se for preciso mudar o cálculo de pontuação, é possível que essa alteração afete
a renderização de pontuação



# SRP <!-- .element: data-header="1" -->

![Jogo x Tela x Pontuacao](/images/srp-classes.png)

Note:
Nessa abordagem, as alterações que sejam necessárias em pontuação, altera apenas
a classe de Pontuacao



![OCP](/images/ocp.jpg)

Entidades de software (classes, módulos, funções, etc) deveriam ser abertos para
extensão porém fechado para modificação



# OCP <!-- .element: data-header="1" -->

![Jogo x Tela](/images/ocp-jogo-tela.png)

Note:
A Classe JogoTruco não é aberta/fechada

Se for necessário mudar a forma de renderização, será necessário mudar as
referências de "Tela" para a nova forma

A JogoTruco tem uma dependência explícita de Tela, ou seja, é necessário que o
jogo de truco tenha uma tela!

Esse tipo de dependência pode ser alterada para



# OCP <!-- .element: data-header="1" -->

![Jogo x Renderizador x Tela](/images/ocp-jogo-render-tela.png)

Note:
Dessa forma, para existir um jogo de truco, é necessario um objeto que renderize
o jogo. Seja com interface gráfica ou interface de texto ou impressora, etc.



![LSP](images/lsp.jpg)

Subtipos devem ser substitutos para os seus tipos base



# LSP <!-- .element: data-header="1" -->

![Jogadas](/images/lsp-jogadas-pontuacao.png)

Note:
Independente do tipo de jogada, a pontuação consegue calcular os pontos.

Considerando que o contrato seja que a Jogada retorne pontuação positiva

A classe JogadaTrucada deve atender ao contrato de Pontuacao
(retornar um valor positivo)



# LSP <!-- .element: data-header="1" -->
<br />
Design by Contract
![Jogadas Com Contrato](/images/lsp-jogadas-pontuacao-contrato.png)

Note:
Para uma classe atender um contrato, ela não pode requerer mais do que a sua
classe base, e não pode oferecer menos que a sua classe base



![ISP](/images/isp.jpg)

Clientes não deveriam ser forçados a depender de métodos que eles não usam



# ISP <!-- .element: data-header="1" -->
<br />
![Porta](/images/isp-porta.png)

Note:
Interfaces são criadas a partir dos clientes

Definimos interfaces para permitir que nossas classes sejam extensíveis



# ISP <!-- .element: data-header="1" -->
<br />
![Porta Automatica](/images/isp-porta-temp.png)

Note:
Não faz sentido que uma interface tenha declarações de dois tipos de clientes

Fica melhor separar as interfaces para cada dominio especifico de cada cliente



![DIP](/images/dip.jpg)

Abstrações não deveriam depender de detalhes.<br />
Detalhes deveriam depender apenas de abstrações



# DIP <!-- .element: data-header="1" -->

![Abajur x Botao](/images/dip-botao.png)

Note:
Nesse caso, o abajur funciona especificamente com um botão

O abajur depende do botão

A seta sai do abajur em direção ao botão



# DIP <!-- .element: data-header="1" -->

![Abajur x Interruptor x Botao](/images/dip-interruptor.png)

Note:
Inversão de dependência significa mudar a seta de dependência

Agora há uma seta saindo do botão e indo em direção ao abajur

Botão agora implementa uma interface específica de um cliente



# SOLID <!-- .element: data-header="1" -->

* **S** ingle-Responsibility Principle
* **O** pen/Closed Principle
* **L** iskov Substitution Principle
* **I** nterface Segregation Principle
* **D** ependency inversion Principle



# Obrigado!

<small data-footer>
  _Slides disponíveis em < http://github.com/danieltdt/apresentacao-solid >_
</small>
