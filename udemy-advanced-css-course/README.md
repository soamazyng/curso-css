#arquivos do curso: https://www.udemy.com/advanced-css-and-sass/

#NATOURS

## box-sizing
```css
box-sizing: border-box;
```
Indica que o tamanho do box, div ou qualquer coisa vai levar em conta o tamanho definido nas bordas.

## background-image
```css
background-image: linear-gradient(
            to right bottom, 
            rgba(126, 213, 111, 0.8), 
            rgba(40,180,131, 0.8)), 
        url('hero.jpg');
```
É possível colocar dois backgrounds images no mesmo seletor, separando por vírgula sendo que o primeiro fica em cima do segundo. Foi utilizado rgba para criar a transparência.


## clip-path
```css
clip-path: polygon(0 0 , 100% 0, 100% 75vh, 0 100%);
```
Cria uma máscara com a imagem de background, exemplos bacanas: https://bennettfeely.com/clippy/


## position
### absolute
Este tipo de posição usa como referência o componente *PAI* onde este deve estar definido como *position: relative* com isso é possível posicionar o conteúdo da div utilizando o *left* e *top* por exemplo. Sendo que as informações de referência serão da div *Pai*

```css
    position: absolute;     
    top: 40px;
    left: 40px;
```

Exemplo *Pai*
```css
position: relative;
```

##transform
###translate
Esta propriedade serve para mover o elemento para os lados X e Y, desta forma, como queremos alinhar a div no centro, não basta colocar 50% para top e left, eu tenho que mudar o *EIXO* da minha div para ser no *centro* e para isso preciso utilizar o translate.
O position absolute continua funcionando para posicionar o elemento de acordo com o *pai*

```css
.text-box{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

Utilizando o valor 0 ele deixa o objeto no local que ele foi definido via css.
Utilizando o *translateX* ele define o valor do eixo na horizontal, sendo que negativo é mais para a esquerda.

```css
@keyframes moveInLeft{
  0%{
    opacity: 0;
    transform: translateX(-100px);
  }

  100%{
    opacity: 1;
    transform: translate(0);
  }
}
```

## keyframe
### animations

Para criar animações no CSS primeiro precisamos definir o nome desta animação, onde *moveInLeft* é o nome da animação.

```css
@keyframes moveInLeft{
}
```

Segundo ponto é definir o tempo que cada animação vai acontecer, isso é feito através de %, sendo que 0% é o início e 100% o final da animação, é possível criar números de % entre o 0 e o 100, por exemplo, quando chegar em 80% tem que fazer tal coisa.


```css
@keyframes moveInLeft{
  0%{
    opacity: 0;
    transform: translateX(-100px);
  }

  80%{
    transform: translateX(20px);
  }

  100%{
    opacity: 1;
    transform: translate(0);
  }
}
```

Finalmente para você utilizar a animação você deve informar o nome e qual a duração desta animação e quanto tempo você quer que espere para *começar* a animação *animation-delay: 3s;*

```css
.heading-primary-main{
  animation-name: moveInLeft;
  animation-duration: 1s;  
}
```

Define o tempo de espera para acontecer a animação

```css
  animation-delay: 3s;
```

Define a quantidade de vezes que a animação vai acontecer

```css
  animation-iteration-count: 3
```

Define como a animação vai acontecer, se vai ser mais rápido para entrar sair e etc.

```css
  animation-timing-function: ease-in
```

Short code para o animate

```css
  animation: moveInRight 1s ease-out;
```

## backface-visibility
### hidden

Define se deve ser apresentado ou não a parte de trás de um objeto, esta propriedade foi utilizada para *corrigir* o bug que acontecendo quando criamos uma animação que o objeto dá um *pequeno* salto para o *topo*. Deixando desta forma a animação mais estável.

```css
backface-visibility: hidden;
```

