**Doel**: Het lokaliseren van het effect van een wijziging in zo min mogelijk subsystemen waardoor
het onderhoud wordt geminimaliseerd.

Probleemsituaties waarin toepasbaar:
• als een wijziging in de software zich niet voort mag planten
• als gedeelten van het systeem uitwisselbaar moeten zijn
• als onderdelen moeten worden hergebruikt
• voor hiërarchisch te ordenen systemen (op basis van stabiliteit)

Oplossing:
• Splits het systeem in een aantal lagen met toenemende stabiliteit. Een laag heeft geen toegang tot hogere lagen.
• 2 soorten: een gesloten archictectuur en een open architectuur

Gevolgen:
• Minder onderhoud: een wijziging in een laag plant zich niet voort in het gehele systeem
• Herbruikbaarheid: de afzonderlijke lagen gebruiken andere applicaties

## Wat bedoelen ze?

Deze dia gaat over het gebruik van **lagen** in React om de **onderhoud baarheid** van een applicatie te verbeteren. Het doel is om het effect van een wijziging in zo min mogelijk subsystemen te lokaliseren, waardoor het onderhoud wordt geminimaliseerd. Dit is vooral handig in situaties waarin een wijziging in de software zich niet mag voortplanten, gedeelten van het systeem uitwisselbaar moeten zijn, onderdelen moeten worden hergebruikt of voor hiërarchisch te ordenen systemen (op basis van stabiliteit) [1](https://www.freecodecamp.org/news/how-to-create-a-three-layer-application-with-react-8621741baca0/).

De oplossing is om het systeem in een aantal lagen met toenemende stabiliteit te splitsen. Een laag heeft geen toegang tot hogere lagen. [Er zijn twee soorten lagen: een gesloten architectuur en een open architectuur](https://www.freecodecamp.org/news/how-to-create-a-three-layer-application-with-react-8621741baca0/) [1](https://www.freecodecamp.org/news/how-to-create-a-three-layer-application-with-react-8621741baca0/).

De gevolgen van het gebruik van lagen in React zijn dat er minder onderhoud nodig is omdat een wijziging in een laag zich niet voortplant in het gehele systeem [1](https://www.freecodecamp.org/news/how-to-create-a-three-layer-application-with-react-8621741baca0/).