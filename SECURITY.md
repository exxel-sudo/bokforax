# Säkerhet

BokföraX hanterar bokföring, kvitton och inloggningar. Hittar du en säkerhetsbrist vill vi gärna veta det — men
**rapportera den privat, aldrig i ett öppet ärende (Issues), en diskussion eller en pull request.** Ett öppet ärende kan
läsas av alla som har tillgång till repot innan bristen är rättad.

## Så rapporterar du

Använd GitHubs privata sårbarhetsrapportering: fliken **Security** i det här repot → **Report a vulnerability**.
Rapporten syns då bara för utvecklaren.

Skriv gärna:

- vilken version det gäller (**Hjälp → Om BokföraX**),
- vad bristen är och vad någon skulle kunna göra med den,
- hur den går att upprepa (steg, anrop eller en liten provfil med **påhittade** uppgifter).

Skicka aldrig riktig bokföring, riktiga kvitton, personnummer, lösenord eller inloggningstoken — inte heller i en privat
rapport.

## Vad som räknas som en säkerhetsbrist

Till exempel att någon utan rätt kan läsa eller ändra bokföring, bilagor eller inställningar; att en telefon, dator eller
länk kan få mer åtkomst än den ska (parkoppling, engångskoder, token); att en fil kan läsas eller skrivas utanför
BokföraX:s egna mappar; att serverns skydd (Apache-vhosten, fail2ban, behållaren) kan kringgås; eller att uppgifter
skickas någonstans utan att användaren valt det.

Fel i beräkningar (moms, deklarationer) är inga säkerhetsbrister — rapportera dem som en vanlig felrapport, se
[FEEDBACK.md](FEEDBACK.md).

## Vad som händer sedan

Rapporten bekräftas, bedöms och rättas så snart det går. Är bristen allvarlig får testarna veta vilken version som
rättar den.

## Versioner som stöds

Bara den senaste testversionen får säkerhetsrättningar.
