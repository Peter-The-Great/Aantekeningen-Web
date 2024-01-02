HTML staat voor **HyperText Markup Language**. Het is een standaard opmaaktaal die wordt gebruikt om webpagina’s te maken. HTML is de basis van alle websites en definieert de structuur van een webpagina. Het bestaat uit een reeks tags die de inhoud van de pagina beschrijven. [Met HTML kunnen ontwikkelaars tekst, afbeeldingen, video’s en andere inhoud op een webpagina plaatsen en deze opmaken met behulp van CSS](https://www.w3schools.com/html/)[1](https://www.w3schools.com/html/).

[Als u wilt leren hoe u HTML kunt gebruiken om uw eigen website te maken, kunt u beginnen met de gratis HTML-tutorial van W3Schools](https://www.w3schools.com/html/)[1](https://www.w3schools.com/html/). Deze tutorial bevat meer dan 200 voorbeelden en bijna 100 oefeningen om u te helpen HTML te leren. [U kunt ook de “Try it Yourself” -editor gebruiken om HTML-code te bewerken en het resultaat te bekijken](https://www.w3schools.com/html/)[1](https://www.w3schools.com/html/).

### Wat is DOM-manipulatie?
DOM-manipulatie is het interactief omgaan met de Document Object Model (DOM) API om het HTML-document te wijzigen dat in de webbrowser wordt weergegeven. Dit HTML-document kan worden gewijzigd/aangepast om elementen toe te voegen, elementen te verwijderen, elementen te bewerken, elementen te verplaatsen, enzovoort . De DOM is een boomstructuur van knooppunten die door de browser wordt gemaakt. Elk van deze knooppunten heeft zijn eigen eigenschappen en methoden die kunnen worden gemanipuleerd met behulp van JavaScript. Het vermogen om de DOM te manipuleren is een van de meest unieke en nuttige vaardigheden van JavaScript  ..

Hier is een eenvoudig voorbeeld van DOM-manipulatie met JavaScript:

```html
<html>
<head>
  <title>DOM Manipulation Example</title>
</head>
<body>
  <h1 id="myHeading">Hello World!</h1>
  <button onclick="changeText()">Click me!</button>

  <script>
    function changeText() {
      document.getElementById("myHeading").innerHTML = "Hello Bing!";
    }
  </script>
</body>
</html>
```

<html>
<head>
  <title>DOM Manipulation Example</title>
</head>
<body>
  <h1 id="myHeading">Hello World!</h1>
  <button onclick="changeText()">Click me!</button>

  <script>
    function changeText() {
      document.getElementById("myHeading").innerHTML = "Hello Bing!";
    }
  </script>
</body>
</html>

In dit voorbeeld hebben we een HTML-pagina met een kop en een knop. Wanneer de knop wordt ingedrukt, wordt de tekst van de kop gewijzigd van "Hello World!" naar "Hello Bing!".
Deze wijziging wordt bereikt door de changeText() functie die de innerHTML eigenschap van het element met de ID myHeading wijzigt. De document.getElementById() methode wordt gebruikt om een verwijzing naar het element te verkrijgen.
Dit is slechts een eenvoudig voorbeeld van wat er mogelijk is met DOM-manipulatie. Er zijn veel andere manieren om de DOM te manipuleren, afhankelijk van wat je probeert te bereiken. Ik hoop dat dit voorbeeld je een idee heeft gegeven van hoe DOM-manipulatie werkt!
Je kunt de stijl van een element wijzigen met behulp van DOM-manipulatie. Hier is een voorbeeld van hoe je de kleur van een element kunt wijzigen met JavaScript:

```html
<!DOCTYPE html>
<html>
<head>
  <title>DOM Manipulation Example</title>
</head>
<body>
  <h1 id="myHeading">Hello World!</h1>
  <button onclick="changeColor()">Click me!</button>

  <script>
    function changeColor() {
      document.getElementById("myHeading").style.color = "red";
    }
  </script>
</body>
</html>
```

In dit voorbeeld hebben we een HTML-pagina met een kop en een knop. Wanneer de knop wordt ingedrukt, wordt de kleur van de kop gewijzigd van zwart naar rood.
Deze wijziging wordt bereikt door de changeColor() functie die de style.color eigenschap van het element met de ID myHeading wijzigt. De document.getElementById() methode wordt gebruikt om een verwijzing naar het element te verkrijgen.

Dit is slechts een eenvoudig voorbeeld van wat er mogelijk is met DOM-manipulatie. Er zijn veel andere manieren om de stijl van een element te manipuleren, afhankelijk van wat je probeert te bereiken. Ik hoop dat dit voorbeeld je een idee heeft gegeven van hoe je de stijl van een element kunt wijzigen met behulp van JavaScript!