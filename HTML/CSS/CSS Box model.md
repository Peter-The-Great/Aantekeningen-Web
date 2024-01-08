Bronnen:
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model

Het CSS-boxmodel is een manier om de grootte en positie van HTML-elementen op een webpagina te definiëren. Het model bestaat uit vier delen: inhoud, padding, rand en marge. De inhoud is het gebied waar de tekst en afbeeldingen van een element worden weergegeven. De padding is de ruimte tussen de inhoud en de rand. De rand is de lijn rond de inhoud en de padding. De marge is de ruimte tussen de rand en andere elementen op de pagina.

Hier is een voorbeeld van hoe het boxmodel werkt:

CSSAI-generated code. Review and use carefully. .

```css
div {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 5px solid black;
  margin: 10px;
}
```

Dit definieert een `<div>`-element met een breedte van 200 pixels, een hoogte van 100 pixels, een padding van 20 pixels, een rand van 5 pixels en een marge van 10 pixels. De totale breedte van het element is 260 pixels (200 + 20 + 20 + 5 + 5 + 10 + 10) en de totale hoogte is 150 pixels (100 + 20 + 20 + 5 + 5 + 10 + 10).

Voorbeeld van het box model:
![](https://media.gcflearnfree.org/content/5ef2084faaf0ac46dc9c10be_06_23_2020/box_model.png)
Het boxmodel is belangrijk omdat het ontwikkelaars in staat stelt om de grootte en positie van elementen op een webpagina nauwkeurig te beheren. [Als u meer wilt weten over het boxmodel, kunt u de gratis CSS-tutorial van W3Schools bekijken](https://www.w3schools.com/Css/css_boxmodel.asp)[1](https://www.w3schools.com/Css/css_boxmodel.asp).

### Margin en Padding
Margin is the space outside of an element. It is the space between an element and the elements around it.

If you want an element to be farther away from other elements, increase the margin property.

Padding is the space inside of an element. It is the space between an element and its content.

### Example of Margin in CSS

Here is how you would give an element a margin in CSS:

```css
.element {
  margin: 10px;
}
```

### Example of Margin in HTML

And here's how you would style the element to have a margin using in-line in HTML. (Keep in mind that this is seen as a lazy practice in most cases.)

```html
<div style="margin-top:100px;">This is some text.</div>
```

### Example of Padding in CSS

Here is how you would give an element padding in CSS:

```css
.element {
  padding: 10px;
}
```

And of course, you can do this with an in-line style in HTML as well:

```html
<div style="padding-top:20px;">This is some text.</div>
```


## Box Sizing
Bron: https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing

In CSS zijn er twee verschillende waarden voor de **box-sizing** eigenschap: **content-box** en **border-box**. De standaardwaarde is **content-box**.

Met **content-box** wordt de grootte van een element bepaald door de inhoud van het element. Als u bijvoorbeeld een element heeft met een breedte van 200 pixels en een padding van 20 pixels, dan is de totale breedte van het element 240 pixels (200 pixels voor de inhoud en 20 pixels voor elke rand).

Met **border-box** wordt de grootte van een element bepaald door de inhoud, padding en rand van het element. Als u bijvoorbeeld een element heeft met een breedte van 200 pixels en een padding van 20 pixels, dan is de totale breedte van het element 200 pixels (200 pixels voor de inhoud, padding en rand).

Hier is een voorbeeld van hoe de twee waarden werken:

```css
div {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 5px solid black;
  box-sizing: content-box;
}
```

Dit definieert een `<div>`-element met een breedte van 200 pixels, een hoogte van 100 pixels, een padding van 20 pixels, een rand van 5 pixels en een box-sizing van content-box. De totale breedte van het element is 240 pixels (200 pixels voor de inhoud en 20 pixels voor elke rand).

```css
div {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 5px solid black;
  box-sizing: border-box;
}
```

Dit definieert een `<div>`-element met een breedte van 200 pixels, een hoogte van 100 pixels, een padding van 20 pixels, een rand van 5 pixels en een box-sizing van border-box. De totale breedte van het element is 200 pixels (200 pixels voor de inhoud, padding en rand).