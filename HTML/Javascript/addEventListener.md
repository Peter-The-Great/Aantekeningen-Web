`addEventListener` is een methode in JavaScript die wordt gebruikt om een functie te koppelen aan een element, zodat de functie wordt uitgevoerd wanneer een bepaald type gebeurtenis optreedt. Het is een van de vele manieren waarop JavaScript kan worden gebruikt om interactieve en dynamische webpagina’s te maken.

Als je bijvoorbeeld een knop hebt op je webpagina en je wilt dat er iets gebeurt wanneer erop wordt geklikt, kun je `addEventListener` gebruiken om een functie te koppelen die wordt uitgevoerd wanneer de knop wordt ingedrukt. Hier is een voorbeeld van hoe je `addEventListener` kunt gebruiken om een functie te koppelen aan een klikgebeurtenis:

```js
const button = document.querySelector('button');

button.addEventListener('click', () => {
  console.log('De knop is ingedrukt!');
});
```

In dit voorbeeld wordt een constante `button` gedefinieerd die verwijst naar het eerste knopelement op de pagina. Vervolgens wordt `addEventListener` gebruikt om een functie te koppelen die een bericht naar de console logt wanneer de knop wordt ingedrukt.