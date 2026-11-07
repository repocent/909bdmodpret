# 909 / Kick Lab — circuit studies

Een onafhankelijke verzameling DIY-kickprojecten, geïnspireerd door de Roland TR-909. Dit project brengt interactieve stripboard-layouts, componentenlijsten, een eigen netlijst en browsergebaseerde klankstudies samen.

> **Let op:** de kickgeluiden zijn Web Audio-modellen, geen simulaties van de getoonde schakelingen en geen opnames van een TR-909. De tekeningen en BOM's zijn documentatie om mee te beginnen, niet gevalideerde productiegegevens. Controleer componentwaarden, aansluitingen, polariteit en netten voordat je iets bouwt of bestelt.

## Projecten

- **[`index.html`](index.html)** — portfolio-achtige startpagina.
- **[`kick-stripboards.html`](kick-stripboards.html)** — vier kickstudies met interactieve stripboard-layouts, componentenlijsten en downloadopties voor SVG en CSV. Het eigen dual-ring-ontwerp toont ook een uit de stripboard-layout afgeleide netlijst.
- **[`Kick-drum_stripboards_stepsequencer.html`](Kick-drum_stripboards_stepsequencer.html)** — dezelfde vier studies met een 16-staps sequencer.
- **[`Nein Oh Nein Kick V1.0 (3).html`](Nein%20Oh%20Nein%20Kick%20V1.0%20(3).html)** — het oorspronkelijke project met scans, schema/layoutreferenties en klankdemo.

## De pagina's gebruiken

Open een HTML-pagina in een moderne browser. Klik op **TRIG** of gebruik de spatiebalk om een kick te horen; pas de beschikbare regelaars aan om de klankmodellen te verkennen. Op de stripboardpagina kun je onderdelen selecteren en de layout, BOM en aansluitinformatie bekijken. Audio start doorgaans pas na een gebruikersactie.

Lokaal serveren kan zonder buildstap of dependencies:

```sh
python3 -m http.server 8000
```

Open daarna <http://localhost:8000/>.

## SVG en BOM uit de stripboardpagina halen

Gebruik [`kick-stripboards.html`](kick-stripboards.html), niet alleen de sequencerpagina:

1. Open de pagina lokaal of via GitHub Pages.
2. Selecteer een van de vier projecttabs.
3. Onder de stripboard-tekening staan downloadknoppen. Kies **Stripboard (SVG)** voor de vectorweergave en **Bomlijst (CSV)** voor de onderdelenlijst. **Layout + bomlijst (HTML, printbaar)** bewaart ook een printbare referentie.
4. De knop **Alle bomlijsten (CSV)** verzamelt de lijsten van alle vier de varianten.
5. Open de CSV in een spreadsheet of teksteditor en controleer waarden en referenties. De CSV is een stuklijst, geen KiCad-netlist.

De SVG-export is bedoeld als zelfstandige visuele referentie. Scans/achtergrondbeelden worden bij export weggelaten. De SVG beschrijft niet automatisch elektrische symbolen, footprints, pin-to-pin verbindingen of PCB-koperbanen.

## Van SVG en BOM naar een KiCad-project

De exports zijn startmateriaal voor handmatige reconstructie; er is geen automatische HTML-naar-KiCad-conversie en er worden geen KiCad-schema's of PCB-bestanden meegeleverd.

1. **Kies één ontwerp en bewaar de bronnen.** Maak een aparte map voor de SVG, BOM-CSV, relevante scan/schema en je KiCad-project. Vermeld in je projectnotities welke HTML-tab en revisie je als bron hebt gebruikt.
2. **Behandel de SVG als plaatsingsreferentie.** Open de SVG in een vectorviewer. Je kunt hem in KiCad's PCB Editor als grafische referentie importeren (de menu-optie voor graphics verschilt per KiCad-versie), of buiten KiCad openhouden. Controleer de schaal; de tekening is geen gevalideerde footprint- of boormaat-tekening. Gebruik hem niet als koperlaag of productiebestand.
3. **Maak het elektrische schema opnieuw.** Start KiCad Project Manager en maak een nieuw project. In Schematic Editor plaats je de passende KiCad-symbolen, vul je waarden en referenties in op basis van de BOM, en teken je verbindingen na uit de oorspronkelijke schakeling en/of netinformatie. Ken connectoren toe voor voeding, trigger en uitgang waar van toepassing. De BOM alleen bevat geen verbindingen.
4. **Controleer alle verbindingen.** Voor de eigen dual-ring-kick staat een netlijst die uit de stripboard-layout is afgeleid; gebruik die als controlehulp, niet als vervanging voor het schema. Voor de scan-gebaseerde ontwerpen zijn posities en strip/kolom-aanduidingen deels visueel afgeleid. Vergelijk met de oorspronkelijke scan/schema en verifieer waarden, pinout, sneden, jumpers en voedingsrails.
5. **Koppel footprints en ontwerp de PCB.** Wijs in KiCad geschikte footprints toe voor de werkelijk gekozen onderdelen. Ontwerp vervolgens een nieuwe PCB op basis van een gekozen maakmethode (bijvoorbeeld geëtste PCB of perfboard-adapter). Een stripboard-SVG is geen gerouteerde PCB-layout: de horizontale strips, gaten en sneden moeten bewust als elektrisch ontwerp worden nagemaakt.
6. **Voer KiCad-controles uit en laat het ontwerp nakijken.** Gebruik ERC voor het schema en DRC voor de PCB, inspecteer de footprint-/pinmapping, polariteit, stroom- en spanningsratings en vergelijkende meetresultaten. ERC/DRC bewijzen niet dat de oorspronkelijke schakeling correct is of dat een ongebouwd ontwerp werkt.

### Belangrijke beperkingen per ontwerp

- De **Nein Oh Nein**, **TR-909** en **TR-909 met mods**-layouts zijn gebaseerd op een scan-/referentielayout. De componentlocaties en strip-/kolomposities zijn niet allemaal uit een geverifieerde elektrische netlist afgeleid.
- De **dual-ring-kick** is expliciet als eigen ontwerp en ongebouwd gemarkeerd. De getoonde netlijst wordt uit de stripboard-geometrie berekend; vergelijk die met een zelfstandig nagetekend schema en controleer hem voordat je bouwt.
- De mod-regelaars in het browsermodel voegen niet vanzelf fysieke modificaties toe aan de getoonde TR-909-layout. Voor exacte mod-schakelingen en waarden is aanvullend schemaonderzoek nodig.
- De BOM bevat componenttypen/waarden, maar kan externe potmeters, schakelaars, connectoren of voedingsdetails als aparte/onvolledige regels tonen. Controleer de bronpagina per ontwerp.

## GitHub Pages

Dit is een statische site zonder buildstap. Stel in de repository-instellingen GitHub Pages in op de gewenste publicatiebron. De HTML-bestanden kunnen direct worden geserveerd.
