---
layout: post
title:  "Dokumentgodkännandeautomatisering"
categories: Automatisering, Programmering, Python, PDF
comments: true
---
På min arbetsplats jobbar vi mycket med dokumenthantering, det vill säga vi hanterar dokument.
Det som inte finns dokumenterat kan man inte med bestämdhet hävda att det gäller.

Ett dokument i det här fallet kan vara en regelrätt rapport eller beskrivning, en ritning,
ett kopplingsschema, eller något annat som är nedskrivet eller avbildat och som kan framställas
på pappersformat.

Inte allt för sällan händer det att vi får dokument, exempelvis översiktsritningar, framtagna
av underleverantörer för vårt godkännande. Vi skall alltså granska och godkänna dokumentet
eller dokumenten i fråga.
<br>
I de fall då dokumenten är direkt redigerbara innebär det inget problem att gå in och ändra
t.ex. från "In&nbsp;Preparation" till "Released" eller "Approved". Vanligare är dock att
dokument från underleverantörer är någon form av specialdokument, så som t.ex. ritningar som
överlämnas i PDF-format och som därför inte direkt kan editeras.

PDF-dokument godkänns i stället genom att man "vattenmärker" eller "stämplar" dokumenten genom
att lägga på en bild på de positioner som skall uppdateras och sparar det som en ny PDF.
För att kunna göra ändringar i PDF-filer krävs att man antingen har en fullversion av
Adobe&nbsp;Acrobat (ej att förväxlas med Adobe&nbsp;Acrobat&nbsp;Reader) eller någon tredjepartsprogramvara som kan editera PDF-filer.

Nyligen ställdes jag inför att "stämpla" PDF-dokument och märkte att den version av
Adobe&nbsp;Acrobat jag hade installerad inte ville starta i Windows&nbsp;7 och provade därför
en gratisprogramvara för att redigera filerna. Programmet, [PDFill](https://www.pdfill.com),
fungerade utan problem; men det var väldigt omständigt och tidsödande att lägga till flera
"stämplar" i ett dokument, jag hade dessutom ett flertal dokument att hantera.
<br>Av den anledningen undersökte jag om jag inte kunde automatisera processen med hjälp av
exempelvis ett pythonscript.

Det visade sig att det finns ett flertal moduler till Python för att hantera PDF-filer. Se
[här](https://pypi.python.org/pypi?%3Aaction=search&term=PDF&submit=search) för en lista över
PDF-moduler i PyPI, Pythons pakethanterare.
<br>Jag valde att använda mig av [PyPDF2](https://pythonhosted.org/PyPDF2/) och
[ReportLab](http://www.reportlab.com/), PyPDF2 för själva PDF-hanteringen, att öppna, läsa
och skapa filer; och ReportLab för att, med precision, kunna skapa en mallfil att konkatenera
med ursprungsfilen för att skapa ett godkänt dokument. Därefter var det en smal sak att få till
ett script som automatiserade hela processen och som dessutom kan detektera vilken typ av
dokument det rör sig om, om det är stående liggande format, A3 eller A4, m.m.

Vill man lära sig [Python](https://www.python.org) finns det bra länkar till dokumentation
på <https://www.python.org> och om man vill lära sig det specifikt för att automatisera sitt
arbete kan jag rekommendera "[Automate The Boring Stuff With Python](https://automatetheboringstuff.com/)" som dels finns att köpa som
en bok, men som även finns att läsa gratis och i sin helhet på <https://automatetheboringstuff.com/>