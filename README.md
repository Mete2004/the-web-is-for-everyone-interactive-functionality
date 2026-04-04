# Interactive Functionality

Ontwerp en maak voor een opdrachtgever een interactieve toepassing die voor iedereen toegankelijk is

De instructie vind je in: [INSTRUCTIONS.md](https://github.com/fdnd-task/the-web-is-for-everyone-interactive-functionality/blob/main/docs/INSTRUCTIONS.md)


## Inhoudsopgave

  * [Beschrijving](#beschrijving)
  * [Gebruik](#gebruik)
  * [Kenmerken](#kenmerken)
  * [Installatie](#installatie)
  * [Bronnen](#bronnen)
  * [Licentie](#licentie)

## Beschrijving
<!-- Bij Beschrijving staat kort beschreven wat voor project het is en wat je hebt gemaakt -->
<!-- Voeg een mooie poster visual of video toe 📸 -->
<!-- Voeg een link toe naar GitHub Pages 🌐-->
De Buurtcampuskrant is een website waarop nieuwsartikelen van de Buurtcampus worden weergegeven. Een soort digitale versie van de krant. Bezoekers kunnen via het navigatiemenu in de header eenvoudig tussen verschillende pagina’s navigeren tussen districten waar artikelen gefilterd worden weergegeven. Vervolgens kan de gebruiker filteren op doelgroepen via de buttons die worden weergegeven op de district pagina's. Daarnaast kan een gebruiker een individueel artikel openen, lezen.

De website heeft een simpel en duidelijk ontwerp zodat bezoekers direct begrijpen wat ze kunnen doen op de site. Knoppen en navigatie zijn duidelijk zichtbaar en maken gebruik van feedforward zodat een gebruiker vooraf begrijpt wat er gebeurt na een actie.



## Gebruik
<!-- Bij Gebruik staat de user story, hoe het werkt en wat je er mee kan. -->
Bezoekers kunnen via het menu in de header navigeren tussen vier verschillende pagina’s waar nieuwsartikelen worden weergegeven.
Op de website kan een gebruiker:

- via het navigatiemenu tussen pagina’s wisselen

- door verschillende nieuwsartikelen bladeren

- door verschillende districten filteren

- door verschillende doelgroepen filteren

- een artikel openen, volledig lezen, reageren en alle reacties bekijken

Voor mobiele schermen is een hamburger menu geïmplementeerd. Wanneer de gebruiker op de knop klikt, klapt het menu uit en worden de navigatielinks zichtbaar.
De website is opgebouwd volgens het mobile first principe met een one column layout. Hierdoor blijven artikelen goed leesbaar op kleinere schermen.

### User story 
#### Comment functionaliteit

<img width="467" height="742" alt="image" src="https://github.com/user-attachments/assets/cc20374a-cecc-41e7-90f7-28f096a450d3" />

## Kenmerken
<!-- Bij Kenmerken staat welke technieken zijn gebruikt en hoe. Wat is de HTML structuur? Wat zijn de belangrijkste dingen in CSS? Wat is er met JS gedaan en hoe? Misschien heb je iets met NodeJS gedaan, of heb je een framework of library gebruikt? -->

In deze applicatie heb ik gebruik gemaakt van Node.js, Express, Liquid, Directus en client-side JavaScript.

**Node.js & Express** = server-side routes en data ophalen

**Directus** = externe database (API)

**Liquid** = data renderen in HTML

**Client-side JavaScript** = interactie (filter/zoeken)

De server haalt data op via Directus en stuurt dit door naar Liquid templates.



### Hoe werkt de applicatie

1. Browser doet request

2. Express route (app.get) vangt dit op

3. Server haalt data op met fetch()

4. res.json() parsed de data

5. Data wordt doorgestuurd naar Liquid

6. Liquid rendert HTML

### UI-stack states

#### Empty-state:

_Geen reactie aanwezig._

Hoe werkt de code:

- Comments worden gefilterd op basis van ``req.params.id``
- Met ``filteredComments.length`` wordt gekeken of er reacties zijn
- Als dit 0 is, dan ``hasComments = false``
- In Liquid wordt dan een melding getoond
<img width="370" height="401" alt="Image" src="https://github.com/user-attachments/assets/9fb3b77d-5696-40b7-9f7b-75c0881819bd" />

#### Succes-state:

_Succesvolle actie, de reactie is geplaatst._

Hoe werkt de code:

- In de route wordt ``req.query.success`` uit de URL gehaald
- Als deze ``true`` is, wordt ``success`` meegestuurd naar Liquid
- In Liquid wordt dan een succesmelding getoond
<img width="366" height="448" alt="Image" src="https://github.com/user-attachments/assets/ef3b23fd-2c13-4093-993d-e4a560923697" />

#### Error-state:

Er ging iets mis bij het plaatsen van een reactite.

Hoe werkt de code:

In de route wordt ``req.query.error`` uit de URL gehaald
Als deze ``true`` is, dan wordt ``error`` meegestuurd naar Liquid
In Liquid wordt een foutmelding getoond

<img width="372" height="620" alt="Image" src="https://github.com/user-attachments/assets/d4ebd864-b9c5-44ce-9114-379e09f4f807" />

## Installatie
<!-- Bij Installatie staat hoe een andere developer aan jouw repo kan werken -->
Om dit project lokaal te gebruiken:

1. Fork deze repository

2. Clone de repository

3. Voer NPM install uit in de terminal van je code editor

4. Voer NPM start toe om de website live te bekijken (NPM start na elke wijziging in de server.js)

## Bronnen

## Licentie

This project is licensed under the terms of the [MIT license](./LICENSE).
