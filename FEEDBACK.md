# Synpunkter och felrapporter

Tack för att du använder BokföraX! Allt du hittar — fel, konstiga siffror, otydliga texter och idéer — gör programmet
bättre.

## Så rapporterar du

1. Öppna **Issues** i det här GitHub-repot och klicka **New issue**.
2. Välj mall:
   - **Felrapport** — något fungerar inte, visar fel eller kraschar.
   - **Förslag** — en idé, något som saknas eller något som är krångligt.
3. Fyll i fälten och skicka. Ett ärende per fel eller idé gör det lättare att följa upp.

Hittar du en **säkerhetsbrist** (någon kan komma åt bokföring, inloggningar eller filer de inte borde nå): skriv
**inte** ett vanligt ärende — följ [SECURITY.md](SECURITY.md) och rapportera privat.

## Det här behövs i en felrapport

- **Var felet syns och vilken version** — se tabellen nedan.
- **Vad du gjorde**, steg för steg, så att felet går att upprepa.
- **Vad du väntade dig** och **vad som hände** i stället (felmeddelandets text ordagrant).
- **Skärmbilder** om de hjälper — men bara med påhittade uppgifter (se nedan).
- **Felrapport eller logg** om det hjälper (se *Loggarna* nedan).

### Plattform och version

| Var | Skriv |
|---|---|
| **Windows** | BokföraX-versionen (**Hjälp → Om BokföraX**), om du installerat från **GitHub** (installationsfilen) eller från **Microsoft Store**, och Windows-versionen (till exempel Windows 11 24H2). |
| **Mac** | BokföraX-versionen (**BokföraX → Om BokföraX** i menyraden), om du installerat från **.dmg-filen** eller från **App Store**, macOS-versionen (till exempel macOS 15 Sequoia) och om Macen har Apple Silicon eller Intel. |
| **iPhone** | Appens version (**Inställningar → Om BokföraX Mobil**), iOS-versionen och om appen är kopplad till en dator eller till en egen server. |
| **Webbläsaren** | Vilken webbläsare och dess version (till exempel Safari, Chrome, Edge eller Firefox), på dator eller surfplatta, och versionen av BokföraX på datorn eller servern som du loggar in mot. |
| **Egen server** | Serverns BokföraX-version och hur den kör (Docker på Debian eller något annat). |

### Loggarna

| Var | Här finns loggen |
|---|---|
| **Windows** | **Hjälp → Öppna loggmappen** (mappen `logs` i `%AppData%\BokforaX`, Microsoft Store-versionen i `%USERPROFILE%\BokforaX`). Visades rutan *Något gick fel* finns felrapporten där som `fel-….txt`, och **Kopiera felrapport** i rutan kopierar den. |
| **Mac** | **Hjälp → Visa loggarna i Finder** (`~/Library/Logs/BokforaX`). Felrapporterna (`fel-….txt`) ligger i samma mapp. |
| **iPhone** | **Inställningar → Felsökning → Exportera loggen**. |
| **Webbläsaren** | Detaljerna om ett fel sparas i loggen på **datorn eller servern** du loggar in mot (se raden för den), och i webbläsarens konsol. |
| **Egen server** | På servern: `cd /opt/bokforapro && sudo docker compose logs --tail 200` (eller mappen där du installerat servern). |

Bifoga bara felrapporten eller ett **utdrag** ur loggen, och **läs igenom det först** — loggar kan innehålla ditt
användarnamn (i sökvägar), bolagsnamn, namn på kunder och anställda och serveradresser. Ta bort sådant innan du skickar.

## Skicka aldrig riktiga uppgifter

Ett ärende på GitHub kan läsas av andra. **Bifoga aldrig:**

- din bokföring (`bokforing.db`), mappen `backups` eller säkerhetskopior (`.zip`),
- riktiga kvitton, fakturor, kontoutdrag eller Amazon-rapporter,
- personnummer, organisationsnummer, bankkonton, adresser eller namn på dina kunder,
- lösenord, engångskoder, reservkoder eller serveradresser.

Behöver felet en fil för att kunna upprepas: gör en kopia med påhittade värden (byt namn, belopp och nummer), eller
beskriv filens upplägg (kolumner, datumformat, bank) i stället. Det enklaste är ofta att prova i ett **nytt bolag**
(**Arkiv → Nytt bolag**) med påhittade siffror och ta skärmbilden där.

## Vad händer sedan?

Ärendet läses och märks. Frågor ställs i ärendet, så håll gärna koll på det. Alla förslag kan inte genomföras, och det
finns inga garantier för när ett fel rättas — men allt läses.

## Hur dina synpunkter används

Genom att skicka en synpunkt, felrapport eller idé godkänner du att Nader får använda den fritt i BokföraX, utan
ersättning och utan att du behöver nämnas. Kodbidrag (pull requests) tas inte emot utan en separat skriftlig
överenskommelse — beskriv hellre ändringen i ett ärende. Se också [LICENS.md](LICENS.md).
