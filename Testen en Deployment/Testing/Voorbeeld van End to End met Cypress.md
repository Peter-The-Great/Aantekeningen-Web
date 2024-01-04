Hier is een voorbeeld van hoe je end-to-end tests kunt schrijven voor een React-applicatie met behulp van Cypress:

```javascript
describe('End-to-end testen met Cypress', () => {
  it('Test de login functionaliteit', () => {
    cy.visit('/login')
    cy.get('input[name="username"]').type('johndoe')
    cy.get('input[name="password"]').type('password123')
    cy.get('button[type="submit"]').click()
    cy.url().should('include', '/dashboard')
  })

  it('Test de navigatie functionaliteit', () => {
    cy.visit('/dashboard')
    cy.get('a[href="/profile"]').click()
    cy.url().should('include', '/profile')
    cy.get('a[href="/dashboard"]').click()
    cy.url().should('include', '/dashboard')
  })
})
```

In dit voorbeeld worden twee end-to-end tests uitgevoerd. De eerste test controleert of de login-functionaliteit correct werkt. De tweede test controleert of de navigatie-functionaliteit correct werkt.

In de eerste test wordt de login-pagina bezocht, worden de gebruikersnaam en het wachtwoord ingevoerd en wordt er op de knop ‘Inloggen’ geklikt. Vervolgens wordt gecontroleerd of de URL de tekst ‘/dashboard’ bevat om te controleren of de gebruiker correct is ingelogd.

In de tweede test wordt de dashboard-pagina bezocht, wordt er op de link ‘Profiel’ geklikt en wordt gecontroleerd of de URL de tekst ‘/profile’ bevat. Vervolgens wordt er op de link ‘Dashboard’ geklikt en wordt gecontroleerd of de URL de tekst ‘/dashboard’ bevat.


## Meer over Cypress
Cypress is een testtool die het mogelijk maakt om tests te schrijven, uit te voeren, te debuggen en te debuggen voor je webapplicaties in de browser. Je kunt Cypress gemakkelijk installeren, integreren met elke CI-provider en de functies gebruiken om de prestaties en zichtbaarheid van je testsuite te optimaliseren.

Cypress kan worden gebruikt om alle soorten tests te schrijven, zoals end-to-end tests, componenttests, integratietests en unit tests. Cypress kan alles testen wat in een browser wordt uitgevoerd.

Bronnen:
https://www.cypress.io/
https://docs.cypress.io/