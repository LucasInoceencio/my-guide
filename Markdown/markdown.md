# Algumas dicas e os principais recursos da linguagem Markdown

Mas você também pode dar uma conferida na documentação oficial da linguagem, clicando [aqui](https://daringfireball.net/projects/markdown/).

Então vamos nessa...

# Cabeçalhos

Abaixo vamos ver os tipos de cabeçalhos ou títulos possíveis em markdown.

```# Título 1```

```## Título 2```

```### Título 3```

```#### Título 4```

```##### Título 5```

```###### Título 6```  

# Parágrafos

Por padrão tudo o que é escrito em markdown é um parágrafo, então não é necessário utilizar nenhum tipo de marcador para informar que o texto digitado é um parágrafo. E essa sentença que acabou de ler é um parágrafo, ou seja não temos marcadores por aqui.

# Quebra de linha

Para realizar a quebra de linha no texto, basta adicionar dois espaços ao final do texto e quebrar a linha usando enter.

Se você selecionar o texto de exemplo, irá verificar que consta os dois espaços. E caso os espaços seja removidos, as frases irão ficar em uma única linha.

```
Frase 1.  
Frase 2.
```

# Enfâses no texto

## Negrito

```
**seu texto**
__seu texto__
```

Resultado:

**seu texto**

## Itálico

```
*seu texto*
_seu texto_
```

Resultado:

*seu texto*

## Negrito e itálico

```
***seu texto***
**_seu texto_**
__*seu texto**_
```

Resultado:

***seu texto***

## Riscado

```
~~seu texto~~
```

Resultado:

~~seu texto~~

## Bloco de citação

```
>Seu texto
```

Resultado:

>Seu texto como um bloco de citação!

# Linhas horizontais

Essas são as formas de fazer linhas horizontais.  
Um detalhe importante é que após o terceiro caractere o markdown "para de contar", então o mínimo é três caracteres, mas pode ter mais do que isso.

Todas as formas irão produzir exatamente a mesma linha.  

```
***
---
___
* * *
- - -
_ _ _
```

Resultado: 

***
---
___
* * *
- - -
_ _ _


# Listas não ordenadas

Essas sãos as formas de se fazer uma lista não ordenada em markdown, lembrando que todas as formas utilizadas irão gerar o mesmo resultado.

Outro detalhe importante, é que pode-se utilizar ```tab``` para fazer a identação e criação de subitens

```
* conteúdo
+ conteúdo
- conteúdo
```

Resultado:

* conteúdo
  + conteúdo
    - conteúdo

# Listas ordenadas

Para fazer uma lista ordenada basta iniciar com número e ponto.

```
1. Primeiro item
2. Segundo item
```

Resultado:

1. Primeiro item
2. Segundo item

***

Caso esteja fazendo uma lista que inicie com números, mas não deseje ordenar basta fazer como abaixo:

```
1994\. Brasil
1998\. França
2002\. Brasil
```

O caracter ```\``` é escape para que o markdown ignore a marcação.

Resultado:

1994\. Brasil  
1998\. França  
2002\. Brasil  

# Links

Essas são as formas de adicionar um link em um texto.
O texto opcional irá aparecer ao deixar o mouse sobre o link.

```
[texto do link](endereço do link "texto opcional")
[texto do link](endereço do link)	
```

Resultado:

[Veja meu guia](https://github.com/LucasInoceencio/MyGuide)  
[Veja meu guia](https://github.com/LucasInoceencio/MyGuide "Esse é meu guia de programação") 

***

Essas são as forams de adicionar um link referente a mesma página em que você está. Um exemplo é fazer um link com um título para fazer um sumário.

```
[site-url]: endereço da url
[texto][site-url]
```

Resultado:

[Meu guia]: https://github.com/LucasInoceencio/MyGuide  "Mais um texto"

[texto][]

# Imagens

Segue como adicionar uma imagem em markdown.

```
![texto da imagem](endereço da imagem)
```

# Tabelas

Abaixo segue a sintaxe de como implementar uma tabela em markdown, lembrando que a segunda linha é obrigatória para que a linguagem entenda que se trata de uma tabela.

```
| Nome | Idade |
| - | - |
| Lucas | 25 |
```

Resultado:

| Nome | Idade |
| - | - |
| Lucas Pires | 25 |

*** 

## Alinhando a tabela

Para realizar o alinha basta definir na segunda linha (aquela que é obrigatória) qual será o alinhamento. Por padrão o alinhamento é à esquerda.

```
Esquerda
| :- | :- |

Centro
| :-: | :-: |

Direita
| -: | -: |
```

Resultado com alinhamento à esquerda:

| Nome | Idade |
| :- | :- |
| Lucas Pires| 25 |

Resultado com alinhamento à direita:

| Nome | Idade |
| -: | -: |
| Lucas Pires| 25 |

Resultado com alinhamento centralizado:

| Nome | Idade |
| :-: | :-: |
| Lucas Pires| 25 |

Uma observação importante é que cada coluna pode ter o seu próprio alinhamento.

# Blocos de código

Para realizar o destaque de um código na linha, basta colocar o texto entre crases.  
Caso o seu código tenha crase, basta envolver todo o código entre duas crases.

```
Seu texto e `código`.
``const message = `My name is ${name}`;``
```

Resultado:

Seu texto e `código`.  
``const message = `My name is ${name}`;`` 

***

Basta colocar olocar \``` antes e ``` no final do seu trecho de código.

Resultado:

```
var a = 2;
var b = 2;
var soma = a + b;
```

Mas é possível utilizar highlight no seu bloco de código, para isso basta colocar a linguagem que está sendo usada logo após as três primeiras crases.

Resultado:

```javascript
var a = 2;
var b = 2;
var soma = a + b;
```

# Dicas para GitHub

Você pode fazer uma lista e adicionar checkbox marcado ou desmarcado. Veja abaixo: 

```
* [ ] Item 01
* [x] Item 02
```

Resultado:

* [ ] Item 01
* [x] Item 02

***

Além disso também é possível referenciar ou item dentro do seu texto usando apenas #.

Também é possível utilizar emojis, como esse :smile:  

```
:smile:
```

Para usar os emojis basta colocar ```:``` antes e depois do nome do emoji.


Para ver a lista com os emojis acesse esse link [aqui](https://www.webfx.com/tools/emoji-cheat-sheet/)