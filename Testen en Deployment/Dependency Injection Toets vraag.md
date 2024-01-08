Hier is hoe je de Dependency Injection (DI) techniek kunt toepassen in React om de afhankelijkheid tussen de “Boek” klasse in de Domeinlaag en de “Opslag” klasse in de Infrastructuurlaag te verminderen:

1. Introduceer een interface of abstracte klasse, bijvoorbeeld `IOpslag`, die wordt gedefinieerd in de Domeinlaag. Deze interface definieert methoden die nodig zijn voor opslag, maar zonder concrete implementatiedetails.
    
    JavaScript
    
    ```javascript
    export default interface IOpslag {
        slaJsonOp(locatie: string, json: string): void;
    }
    ```
    
    AI-generated code. Review and use carefully. .
    
2. Laat de “Opslag” klasse deze interface implementeren.
    
    JavaScript
    
    ```javascript
    export default class Opslag implements IOpslag {
        slaJsonOp(locatie: string, json: string): void {
            // Implementatie details
        }
    }
    ```
    
    AI-generated code. Review and use carefully. .
    
3. In plaats van een directe afhankelijkheid van “Opslag”, zou “Boek” nu afhankelijk zijn van `IOpslag`. Injecteer deze afhankelijkheid via de constructor of een setter methode van “Boek”.
    
    ```javascript
    export default class Boek {
        private opslag: IOpslag;
        
        constructor(opslag: IOpslag) {  // Constructor injection
            this.opslag = opslag;
        }
        
        // Andere methoden en logica blijven hetzelfde
    }
    ```  

Nu kan elke klasse die `IOpslag` implementeert, worden geïnjecteerd in “Boek”, waardoor het gemakkelijk is om verschillende opslagimplementaties te gebruiken of te testen zonder dat je code hoeft te wijzigen in de “Boek” klasse.