# Integritetspolicy för BokföraX

*Gäller BokföraX för Windows och Mac, iPhone-appen och webbåtkomsten. Senast ändrad 2026-10-28.*

## Kortfattat

**BokföraX samlar inte in några uppgifter om dig.** Programmen skickar ingenting till BokföraX:s utvecklare — varken din
bokföring, dina kvitton, din e-post eller någon statistik om hur du använder dem. Det finns inget konto att skapa, ingen
molntjänst från oss, ingen reklam och ingen spårning. Bokföringen stannar på din egen dator eller på en egen server som
du själv har kopplat in.

Det är du (eller ditt företag) som är personuppgiftsansvarig för kunderna, leverantörerna, köparna och de anställda i
din bokföring — BokföraX:s utvecklare ser dem aldrig.

## Plattformarna

### Windows

Bokföringen, säkerhetskopiorna och loggarna sparas i `%AppData%\BokforaX` (Microsoft Store-versionen i
`%USERPROFILE%\BokforaX`, till exempel `C:\Users\Anna\BokforaX`). Mappen ligger kvar om du avinstallerar programmet,
eftersom bokföringslagen kräver att bokföringen sparas i sju år. Vill du ta bort den raderar du mappen i Utforskaren.

### Mac

Bokföringen och säkerhetskopiorna sparas i `~/Library/Application Support/BokforaX` (App Store-versionen i appens
behållare under `~/Library/Containers`), loggarna i `~/Library/Logs/BokforaX` och en cache med kvittotext och sidbilder
i `~/Library/Caches/se.bokforax.desktop`, som töms efter sju dagar.

Loggarna på Windows och Mac kan innehålla namn på kunder och anställda. De sparas i 90 dagar och lämnar aldrig datorn om
du inte själv skickar dem.

### iPhone

- Appen läser kvitton på telefonen (med Apples textigenkänning) och skickar dem **bara till din egen
  BokföraX-installation** — BokföraX på din dator (Windows eller Mac) eller din egen server. Aldrig till utvecklaren
  eller någon annan.
- Ett kvitto som inte kunnat skickas ligger krypterat i appens egen mapp tills det har skickats, och följer inte med i
  telefonens iCloud-säkerhetskopia. Kopplingens nyckel sparas i iPhones nyckelring.
- Den senast hämtade översikten sparas i telefonen så att den syns utan uppkoppling, och Apple Watch visar samma siffror.
  Widgetarna på hem- och låsskärmen visar bara siffror som appen själv har hämtat; har du Face ID-låset påslaget sparas
  inga siffror för widgetarna.
- En bild eller PDF som du delar till BokföraX från en annan app läggs i appens egen mapp tills du öppnar appen, och
  skickas sedan som ett vanligt kvitto till din egen BokföraX-installation.
- Kommentarer och frågor som du skriver i appen sparas bara i din egen BokföraX-installation.
- Har din arbetsgivare kopplat appen till dig som anställd ser du dina egna utlägg, lönebesked och semesterdagar, och du
  kan bland annat ansöka om ledighet, registrera arbetstid och stämpla in och ut i personalliggaren. En stämpling får sin
  tid av arbetsgivarens BokföraX-installation, och appen använder inte telefonens plats. Uppgifterna går bara mellan
  telefonen och arbetsgivarens BokföraX-installation, och det är arbetsgivaren som ansvarar för dem. Appen sparar inga
  lönebesked i telefonen; en PDF du öppnar ligger bara tillfälligt i appens egen mapp.

| Behörighet | Varför |
|---|---|
| **Kamera** | För att fota kvitton och skanna QR-koden när du kopplar appen till datorn. |
| **Bilder** | För att välja ett kvitto du redan har fotat. |
| **Lokalt nätverk** | För att hitta och nå BokföraX på din dator i samma nätverk. Behövs inte med en egen server. |
| **Notiser** | För påminnelser om datum att hålla och om sådant som väntar, om du tillåter det. Notiserna planeras i telefonen. |
| **Face ID** | För att låsa appen om du slår på det. Ansiktsdata hanteras av iPhone och når aldrig appen. |

### Webbåtkomsten

**Nå bokföringen via webben** (från 5.7.0) är avstängd tills du själv slår på den. Då är **din egen dator eller server
servern**: webbläsaren hämtar sidorna och bokföringen därifrån, efter inloggning med lösenord och engångskod. Ingenting
går via BokföraX:s utvecklare. Varje inloggningsförsök (tid, IP-adress och webbläsare, aldrig lösenord) sparas i
inloggningsloggen på din dator eller server.

Hur datorn nås utifrån väljer du själv: Tailscale, en publik adress via ditt eget Cloudflare- eller Tailscale-konto, eller
din egen router eller VPN. Väljer du en sådan tjänst går trafiken via den enligt dess villkor — med Cloudflare Tunnel
packas trafiken upp hos Cloudflare på vägen.

### Egen server

Serverläget används bara om du själv sätter upp och kopplar till en egen BokföraX-server. Bokföringen ligger då på den
servern, och datorerna, iPhone-appen och webbåtkomsten arbetar mot den.

## Vad programmen kontaktar på internet

Programmen hämtar på egen hand bara **valutakurser** från Sveriges Riksbank (`api.riksbank.se`) och Europeiska
centralbanken (`data-api.ecb.europa.eu`). Inga uppgifter om dig eller bokföringen skickas med. iPhone-appen kontaktar
bara din dator eller din server.

Om du själv slår på det gör programmen också följande:

- **Sök efter nya versioner:** hämtar en offentlig fil från GitHub (av från början, finns inte i butiksversionerna).
  GitHub ser din IP-adress, som vid alla webbesök.
- **Tillåt iPhone på nätverket:** datorn annonserar ”BokföraX” i det lokala nätverket (Bonjour) så att telefonen hittar
  den. Annonsen innehåller inga namn — bara att BokföraX finns och certifikatets kontrollsumma.
- **Molnbackup och andra plats:** säkerhetskopiorna läggs i en mapp som till exempel Dropbox, OneDrive, Google Drive eller
  iCloud synkar. Då krypteras de alltid med ditt lösenord innan de lämnar datorn. Molntjänsten blir mottagare av den
  krypterade filen och kan ha servrar utanför EU.
- **E-post, kopplingar och webhooks:** fakturor och lönebesked skickas med ditt eget e-postkonto, och kvitton hämtas från
  den e-postmapp du anger. Shopify, Stripe, PayPal, Zettle, SumUp och Bolagsverket hämtas med din egen nyckel. Webhooks
  och API:t skickar det du väljer till adressen du anger.

### AI-assistenten

AI-assistenten är **avstängd från början**. Slår du på den väljer du själv var frågorna går:

- **Claude (Anthropic)** eller **ChatGPT (OpenAI)** — med **din egen** API-nyckel. Frågorna och det du väljer att skicka
  (till exempel texten från ett kvitto du vill tolka) går till Anthropic respektive OpenAI i USA, enligt deras villkor och
  personuppgiftsbiträdesavtal.
- **AI på datorn** — Apple Intelligence på Macen, eller en lokal modell (Ollama eller LM Studio) på din egen dator. Ingen
  nyckel behövs, och **ingenting skickas från datorn**.

Personnummer och kontonummer döljs innan något skickas, och löner skickas aldrig. Frågar du AI i webbläsaren går frågan
till datorn eller servern med bokföringen, som frågar den AI-tjänst som är vald där — ingen nyckel finns i webbläsaren.

### Kraschrapporter från Apple och Microsoft

Har du i macOS, iOS eller Windows valt att dela analys- eller kraschdata med apputvecklare kan Apple eller Microsoft
skicka kraschrapporter utan namn till utvecklaren. Det styrs av dina systeminställningar, inte av BokföraX, och används
bara för att rätta fel.

## Dina rättigheter

Programmen skickar inga personuppgifter till utvecklaren, så det finns inget från programmen hos utvecklaren att lämna
ut, rätta eller radera. Uppgifterna i din bokföring styr du själv: du kan ta bort dem på din dator, din server eller i
appen. Bokföringslagen kan kräva att du sparar räkenskapsinformation i sju år — det ansvaret är ditt.

Webbplatsen [bokforax.se](https://bokforax.se) och synpunktsformuläret där beskrivs i webbplatsens integritetspolicy,
[bokforax.se/integritet.html](https://bokforax.se/integritet.html).

## Kontakt

Frågor om integritet: skriv till **kontakt@bokforax.se**, använd formuläret **Tyck till** på bokforax.se, eller öppna
ett ärende under [Issues](https://github.com/exxel-sudo/bokforax/issues) (skriv aldrig personuppgifter där). En
säkerhetsbrist rapporteras privat enligt [SECURITY.md](SECURITY.md).

Ändras policyn uppdateras den här sidan och datumet ovan.
