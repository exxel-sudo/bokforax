# Integritetspolicy för BokföraX

*Gäller BokföraX för Windows och BokföraX Mobil för iPhone. Senast ändrad 2026-10-03.*

## Kortfattat

**BokföraX samlar inte in några uppgifter om dig.** Utvecklaren får varken din bokföring, dina kvitton, din e-post eller
någon statistik om hur du använder programmen. Det finns inget konto att skapa, ingen reklam och ingen spårning.

## Var dina uppgifter finns

- **Windows-programmet** sparar bokföringen på din egen dator (mappen `%AppData%\BokforaPro`) och, om du själv väljer
  det, säkerhetskopior på en plats du anger.
- **iPhone-appen** är en följeslagare till Windows-programmet. Kvitton du fotar och översikter du ser går **bara mellan
  telefonen och din egen dator** (i samma nätverk) **eller din egen server** — aldrig till utvecklaren eller någon annan.
  Kopplingens nyckel sparas i iPhones nyckelring. Fotade kvitton som väntar på att skickas ligger kvar i appen tills de
  har tagits emot.
- **Serverläget** används bara om du själv sätter upp och kopplar till en egen BokföraX-server.

## Vad programmen kontaktar på internet

- **Windows-programmet** hämtar valutakurser från Sveriges Riksbank (`api.riksbank.se`) och Europeiska centralbanken
  (`data-api.ecb.europa.eu`). Inga uppgifter om dig eller din bokföring skickas med.
- **E-post:** om du själv ställer in din e-post skickas fakturor via **din** e-postleverantör till de mottagare du väljer,
  och kvitton hämtas från den e-postmapp du anger.
- **Webhooks och API-nycklar:** om du själv lägger upp dem skickas händelser i bokföringen till de adresser du anger,
  och de tjänster du ger en nyckel kan läsa och bokföra enligt den behörighet du väljer.
- **AI-assistenten** är avstängd från början. Slår du på den skickas din fråga (med bolagsform och momsstatus), eller
  texten från ett kvitto du väljer att tolka, till Anthropic (Claude) med **din egen** API-nyckel. Anthropics villkor
  gäller för det. Hela bokföringen skickas aldrig.
- **iPhone-appen** kontaktar bara din dator eller din server.

## Behörigheter i iPhone-appen

| Behörighet | Varför |
|---|---|
| **Kamera** | För att fota kvitton. |
| **Bilder** | För att välja ett kvitto du redan har fotat. |
| **Lokalt nätverk** | För att hitta och nå BokföraX på din dator i samma nätverk. |
| **Face ID** | För att låsa appen om du slår på det. Ansiktsdata hanteras av iPhone och når aldrig appen. |

## Dina rättigheter

Eftersom inga personuppgifter samlas in av utvecklaren finns det inget hos utvecklaren att lämna ut, rätta eller radera.
Uppgifterna i din bokföring styr du själv: du kan ta bort dem på din dator, din server eller i appen. Bokföringslagen
kan kräva att du sparar räkenskapsinformation i sju år — det ansvaret är ditt.

## Kontakt

Frågor om integritet: öppna ett ärende under [Issues](https://github.com/exxel-sudo/bokforax/issues) (skriv aldrig
personuppgifter där), eller rapportera privat enligt [SECURITY.md](SECURITY.md).

Ändras policyn uppdateras den här sidan och datumet ovan.
