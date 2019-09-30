#arquivos do curso: https://www.udemy.com/advanced-css-and-sass/

#NATOURS

## box-sizing
```css
box-sizing: border-box;
```
Indica que o tamanho vai levar em conta a borda

## background-image
```css
background-image: linear-gradient(
            to right bottom, 
            rgba(126, 213, 111, 0.8), 
            rgba(40,180,131, 0.8)), 
        url('../img/hero.jpg');
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