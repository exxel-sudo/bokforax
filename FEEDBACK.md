# Synpunkter och felrapporter

Tack för att du testar BokföraX! Allt du hittar — fel, konstiga siffror, otydliga texter och idéer — gör programmet
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

- **Version:** står under **Hjälp → Om BokföraX** (till exempel 4.1.0), och om du kör den installerade eller den
  portabla versionen.
- **Windows-version:** till exempel Windows 11 23H2.
- **Vad du gjorde**, steg för steg, så att felet går att upprepa.
- **Vad du väntade dig** och **vad som hände** i stället (felmeddelandets text ordagrant).
- **Skärmbilder** om de hjälper — men bara med påhittade uppgifter (se nedan).
- **Felrapport eller logg** om rutan *Något gick fel* visades: **Hjälp → Öppna loggmappen**. Bifoga bara filen
  `fel-….txt` eller ett utdrag ur loggen, och **läs igenom den först** — loggar kan innehålla ditt Windows-användarnamn
  (i sökvägar), bolagsnamn och serveradresser. Ta bort sådant innan du skickar.

## Skicka aldrig riktiga uppgifter

Ett ärende på GitHub kan läsas av andra. **Bifoga aldrig:**

- din bokföring (`bokforing.db`), mappen `backups` eller säkerhetskopior (`.zip`),
- riktiga kvitton, fakturor, kontoutdrag eller Amazon-rapporter,
- personnummer, organisationsnummer, bankkonton, adresser eller namn på dina kunder,
- lösenord, engångskoder eller serveradresser.

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
