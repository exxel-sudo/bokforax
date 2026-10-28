# Säkerhet

BokföraX hanterar bokföring, kvitton och inloggningar. Hittar du en säkerhetsbrist vill vi gärna veta det — men
**rapportera den privat, aldrig i ett öppet ärende (Issues), en diskussion eller en pull request.** Ett öppet ärende kan
läsas av alla som har tillgång till repot innan bristen är rättad.

## Så rapporterar du

Använd GitHubs privata sårbarhetsrapportering: fliken **Security** i det här repot → **Report a vulnerability**.
Rapporten syns då bara för utvecklaren.

Skriv gärna:

- vilken version det gäller (**Hjälp → Om BokföraX** i Windows och i webbläsaren, **BokföraX → Om BokföraX** på Macen,
  **Inställningar → Om BokföraX Mobil** på iPhone) och var programmet kommer ifrån (GitHub, Microsoft Store eller
  App Store),
- om bristen gäller Windows-programmet, Mac-programmet, iPhone-appen, webbåtkomsten eller en egen BokföraX-server,
- vad bristen är och vad någon skulle kunna göra med den,
- hur den går att upprepa (steg, anrop eller en liten provfil med **påhittade** uppgifter).

Skicka aldrig riktig bokföring, riktiga kvitton, personnummer, lösenord eller inloggningstoken — inte heller i en privat
rapport.

## Vad som räknas som en säkerhetsbrist

Till exempel att någon utan rätt kan läsa eller ändra bokföring, bilagor eller inställningar; att en telefon, dator,
webbläsare eller länk kan få mer åtkomst än den ska (parkoppling, engångskoder, token, webbinloggningen och
tvåstegsverifieringen); att en fil kan läsas eller skrivas utanför BokföraX:s egna mappar; att serverns skydd
(Apache-vhosten, fail2ban, behållaren) kan kringgås; eller att uppgifter skickas någonstans utan att användaren valt det.

Fel i beräkningar (moms, deklarationer) är inga säkerhetsbrister — rapportera dem som en vanlig felrapport, se
[FEEDBACK.md](FEEDBACK.md).

## Vad som händer sedan

Rapporten bekräftas, bedöms och rättas så snart det går. Är bristen allvarlig står det i release-texten vilken version
som rättar den.

## Versioner som stöds

Säkerhetsrättningar kommer i den **senaste versionen** — av Windows-programmet (från GitHub eller Microsoft Store),
Mac-programmet och iPhone-appen. En äldre version rättas inte, så uppdatera när en ny version finns. Microsoft Store och
App Store granskar varje version, så där kan den komma senare än under [Releases](../../releases/latest).

Webbåtkomsten är en del av programmet på din dator eller din server och uppdateras med det.

## Uppdatera i rätt ordning

Har du en **egen BokföraX-server**: uppdatera **servern först**, sedan **datorerna** (Windows och Mac) och sist
**iPhone-appen**. En nyare app fungerar mot en äldre server, men det som är nytt och går via servern — också
säkerhetsrättningar i servern — gäller först när servern har den nya versionen.
