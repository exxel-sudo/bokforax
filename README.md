# BokföraX

**Bokföring för svenska enskilda firmor och små aktiebolag** — byggd efter svenska regler: bokföringslagen, moms med
alla rutor, SIE 4 och filerna till Skatteverket.

> **Testversion.** BokföraX är under utveckling och testas nu av fler. Prova gärna och berätta vad som fungerar och vad
> som inte gör det — se [Synpunkter och felrapporter](#synpunkter-och-felrapporter). Programmets källkod är inte publik.

![Hem](bilder/hem.png)

## Vad BokföraX gör

- **En inkorg för allt** — kvitton, kontoutdrag och rapporter hamnar i Inkorgen med ett färdigt förslag. Du godkänner
  med **Enter**, ändrar med **F2**. Regler lär sig av dina val.
- **Riktig bokföring** — verifikationer i serier, rättelser i stället för radering, låsta perioder, revisionslogg,
  huvudbok och kontoplan (BAS).
- **Moms** — momsdeklarationen med alla rutor, periodisk sammanställning, omvänd moms, OSS, och filen till
  Skatteverket.
- **Fakturor** — kundfakturor med egen logotyp, kreditfakturor, leverantörsfakturor och betalningar.
- **Affiliate och e-handel** — Amazon Associates (utbetalningar per marknadsplats, valutakurser från Riksbanken) och
  import från Shopify, Stripe och PayPal.
- **Deklaration och bokslut** — NE-bilaga, SRU-filer, skatteuppskattning, bokslut och SIE 4-export till din revisor.
- **Säkerhetskopior** — dagliga kopior som kontrolleras, och återställning med ett klick.

| | |
|---|---|
| ![Inkorg](bilder/inkorg.png) | ![Verifikationer](bilder/verifikationer.png) |
| ![Moms](bilder/moms.png) | ![Affiliate](bilder/affiliate.png) |
| ![Kundfakturor](bilder/kundfakturor.png) | ![Mörkt tema](bilder/hem-morkt.png) |

## Dina uppgifter stannar hos dig

Bokföringen sparas **på din egen dator**. Ingenting skickas till BokföraX:s utvecklare — inga konton, ingen molntjänst,
ingen spårning. Det enda programmet hämtar själv från nätet är valutakurser (Riksbanken/ECB). Ta gärna säkerhetskopior
till ett USB-minne under **Inställningar → Säkerhetskopiering**.

## Kan jag lita på programmet?

Källkoden är inte publik, så här är det du behöver veta — och hur du själv kan kontrollera det.

**Vad BokföraX gör med nätet.** Programmet kontaktar självt bara två adresser: **Riksbanken** (`api.riksbank.se`) och
**Europeiska centralbanken** (`data-api.ecb.europa.eu`) för valutakurser. Inget annat — ingen inloggning, inget konto,
ingen statistik eller spårning, ingen uppdateringskoll som skickar uppgifter. Två saker sker bara om **du själv** ställer
in dem: att skicka fakturor med **din** e-post, och att koppla till en **egen** server.
*Kontrollera själv:* koppla bort datorn från internet — BokföraX fungerar fullt ut, bara utan nya valutakurser.

**Var dina uppgifter ligger.** Allt sparas på din dator i `%AppData%\BokforaPro` (namnet från tiden före BokföraX).
Säkerhetskopiorna hamnar i samma mapp, och du kan välja en extra plats, till exempel ett USB-minne. Avinstallerar du
programmet ligger bokföringen kvar.

**Skannad efter virus.** Varje installationsfil skannas med Microsoft Defender innan den läggs upp här (4.2.0: inga
fynd) och kontrolleras på VirusTotal (4.2.0: 51 av 52 rena, ett maskininlärningsfalsklarm — se nedan).

**Säkerhetsgranskad.** Programmet har granskats av flera oberoende granskningar med fokus på säkerhet (inloggningar,
filer, nätverk) inför testversionen. Alla allvarliga och medelallvarliga fynd är rättade. Hittar du en brist:
rapportera privat enligt [SECURITY.md](SECURITY.md).

**Testat.** Varje version testas automatiskt med över 2 000 tester (moms, bokföring, SIE, filer, säkerhet) innan den
släpps, och startas på riktigt innan installationsfilen byggs.

**Vem står bakom.** BokföraX utvecklas av en privatperson i Sverige, Nader, som själv använder programmet för sin
bokföring. Frågor och synpunkter tas emot under [Issues](../../issues).

## Bra att veta innan du installerar

**"Windows skyddade datorn"** — testversionen är inte kodsignerad ännu (ett signeringscertifikat köps när programmet
lämnar testfasen). Därför känner Windows inte igen utgivaren och varnar. Klicka **Mer info → Kör ändå**.

**Är filen säker?** Det är förståeligt att vara försiktig med en .exe-fil från nätet. Så här kan du kontrollera den:

- **Antivirus:** installationsfilen för 4.2.0 är skannad med Microsoft Defender (virusdefinitioner 1.459.518.0) utan
  fynd. Du kan själv högerklicka på filen → **Skanna med Microsoft Defender**.
- **VirusTotal** (ett 50-tal antivirusprogram på en gång): **51 av 52 hittar ingenting** —
  [se resultatet för 4.2.0](https://www.virustotal.com/gui/file/f5d04367fe20d6c4db36db44d3642eabdf22b3724f14cd68e2bab76f5f8ca04e). Ett enda program (Trapmine) ger en
  maskininlärningsgissning, *"Malicious.moderate.ml.score"* — ingen känd virussignatur, utan en gissning utifrån hur
  filen är byggd. Sådana falsklarm är vanliga för nya installationsprogram som inte är kodsignerade ännu.
- **Att filen är oförändrad:** kör i PowerShell `Get-FileHash .\BokforaX-Setup-4.2.0.exe` — svaret ska vara
  `F5D04367FE20D6C4DB36DB44D3642EABDF22B3724F14CD68E2BAB76F5F8CA04E` (står också under Releases).
- **Hämta bara härifrån.** BokföraX sprids inte någon annanstans.

**Inget demoläge ännu.** Det finns inget färdigt påhittat företag att prova med. Vill du testa utan dina riktiga
uppgifter: hitta på ett företag i välkomstguiden (till exempel "Testfirma") och mata in några påhittade kvitton och
fakturor. Ett demoläge kommer i en senare version.

## Installera

1. Gå till **[Releases](../../releases/latest)** och ladda ner `BokforaX-Setup-<version>.exe`.
2. Kör filen. Visar Windows **"Windows skyddade datorn"**: klicka **Mer info → Kör ändå** (se ovan).
3. Följ installationen. Första gången frågar en kort guide vad som gäller för dig (enskild firma eller aktiebolag,
   moms, vad du gör).

**Krav:** Windows 10 eller 11 (64-bitars). Inget annat behöver installeras.

**iPhone-appen** (fota kvitton, översikt i mobilen) ska komma via **App Store** — den finns inte där ännu. Just nu kan
bara Windows-programmet testas.

## Synpunkter och felrapporter

Allt är välkommet — fel, konstiga siffror, otydliga texter och idéer.

1. Öppna **[Issues](../../issues)** → **New issue**.
2. Välj **Felrapport** eller **Förslag** och fyll i fälten.

Skriv versionen (**Hjälp → Om BokföraX**) och hur felet går att upprepa. **Bifoga aldrig riktig bokföring, riktiga
kvitton, personnummer eller kontonummer** — använd påhittade uppgifter. Mer i
[FEEDBACK.md](FEEDBACK.md). En **säkerhetsbrist** rapporteras privat enligt [SECURITY.md](SECURITY.md).

## Licens

BokföraX är gratis att använda — även för din riktiga bokföring i din egen verksamhet — men får **inte säljas, hyras ut
eller spridas vidare**. Hämta alltid programmet härifrån. Villkoren på vanlig svenska: [LICENS.md](LICENS.md); det är
licenstexten i [LICENSE](LICENSE) (PolyForm Internal Use 1.0.0) som gäller.

Programmet levereras i befintligt skick, utan garantier. Ansvaret för bokföringen och deklarationerna är alltid ditt —
kontrollera siffrorna innan du skickar något till Skatteverket.

BokföraX hette tidigare BokföraPro (till och med version 4.1).
