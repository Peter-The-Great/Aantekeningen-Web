De term "eenrichtingsgegevensstroom" in React verwijst naar de manier waarop gegevens doorgegeven worden in een React-applicatie, van boven naar beneden in de componenthiërarchie.

In React wordt de gegevensstroom als volgt georganiseerd:

1. **Boven-naar-beneden**: Gegevens worden doorgegeven van een bovenliggende (ouder) component naar een onderliggende (kind) component via `props` (eigenschappen).
   
   Bijvoorbeeld:
   ```javascript
   // Bovenliggende component
   const ParentComponent = () => {
     const data = "Dit is gegevens van de oudercomponent";
     return <ChildComponent data={data} />;
   };

   // Onderliggende component
   const ChildComponent = ({ data }) => {
     return <p>{data}</p>;
   };
   ```

2. **Props**: De eigenschappen (`props`) worden doorgegeven van boven naar beneden in de componenthiërarchie. Een onderliggende component ontvangt gegevens van een bovenliggende component via deze `props`.

3. **Eénrichtingsstroom**: De gegevensstroom is éénrichtingsverkeer, wat betekent dat de gegevens normaal gesproken niet rechtstreeks van een onderliggende naar een bovenliggende component worden doorgegeven. Ze gaan alleen van boven naar beneden, van ouder naar kind.

Deze gestructureerde manier van gegevens doorgeven zorgt voor een betere voorspelbaarheid en eenvoudiger gegevensbeheer in de applicatie. Hierdoor is het eenvoudiger om wijzigingen in gegevens te volgen en de applicatie gemakkelijker te debuggen, omdat de gegevensstroom een duidelijke richting volgt en de componenten geïsoleerd blijven van elkaars interne logica.