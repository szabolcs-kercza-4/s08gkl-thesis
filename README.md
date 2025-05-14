# Üzleti alkalmazás fejlesztése Microsoft Power Platformon
Készítette: Kercza Szabolcs

Ez a github repository a pályaműhöz kapcsolódő Power Platform megoldást, a Jira Service Managemment autómatozációt illetve pályaműben használt kéréseket tartalmazó Postman kollekciót tartalmazza.
## Előfeltételek
- Microsoft 365 Vállalati csomag
- Microsoft Power Automate
- Microsoft Power Apps
- Jira Service Management és hozzá egy Service Desk projekt
- Atlassian Compass

## Jira Service Management autómatizációk importálása
1. System Settings
2. Automation -> Global automation
3. ... -> Import rules
4. Kiválasztott autómatizáció JSON fájl feltöltése
## Postman asztali alkalmazás
1. Fájl -> Import
## Power Platform
1. make.powerapps.com
2. Solutions
3. Import solution
4. .zip fájl kiválasztása

## API kulcs létrehozása Jira Service Managementben
1. id.atlassian.com/manage-profile/security/api-tokens
2. Create API token

## API kulcsok elhelyezése a Power Automate Flowkban
1. make.powerautomate.com -> My Flows
2. HTTP kérésekben a Password mezőbe a generált API és az User mezőbe felhasználó emailcímének beillesztése az alábbi Flowkban:
- Sync Application Dataverse
- Sync Incidents to Dataverse
- Uptade Incident v2
- SendIncidentDataToJira
- SendTransitionUpdateToJira

## OAuth2 beállítása Azureben
1. portal.azure.com -> App registrations
2. New registration
3. Alap beállítások, majd Register
4. Az Application (client) ID) és a Directory (tenant) ID itt található
5. Manage -> Certificates & secrets -> Client secrets
6. New client secret

## Jira Service Management Automatizációk beállítása
1. Jira Service Management -> Service Desk projekt -> Project Serrings -> Automation
2. Web request URL, client_id és client_secret kicserélés az első Send web request kártyában
3. A második Send web request kártyában az URL-t az Uptdate Incident v2 trigger HTTP URL értékére kell beállítani
4. Ezeket az összes importált automatizációra meg kell csinálni
