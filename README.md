# 📊 Inflatie-analyse GPT voor Inkopers

Deze GPT helpt inkopers automatisch de inflatie van producten van leveranciers te analyseren, op basis van PDF's én een referentie-inflatie-dataset. Bij afwijkingen worden leveranciers automatisch aangeschreven via een Zapier-integratie.

---

## 🧠 Functionaliteiten

- 🔍 Analyseert leveranciers-PDF’s op inflatie per product
- 📎 Koppelt producten aan officiële productcategorieën (op basis van CSV)
- 🌍 Gebruikt land-specifieke inflatiegegevens (uit CSV)
- ⚖️ Vergelijkt opgegeven inflatie met maximaal aanvaardbare inflatie
- ⚠️ Stuurt melding via Zapier bij overschrijdingen
- 📊 Genereert visuele vergelijking (met grafiek)
- 📧 Stuurt automatisch e-mails naar leveranciers via webhook

---

## 🛠️ Werkwijze

1. Leverancier stuurt PDF met inflatie-informatie
2. GPT:
   - Leest PDF automatisch uit
   - Matcht producten met categorieën uit `CPI; bijdragen aan de jaarmutatie (%-punt).csv`
   - Haalt maximaal aanvaardbare inflatie per categorie en land op
   - Vergelijkt met opgegeven inflatie
3. Bij overschrijding:
   - Stuurt JSON naar Zapier webhook
   - Genereert grafiek met verschillen
   - Voegt analyse toe aan e-mail

---

## 📁 Structuur 
Deze sectie beschrijft hoe je de Inflatie Tracker Simplified GPT kunt nabouwen en welke onderdelen je nodig hebt.

-- 

##📦 Benodigdheden
 - Custom GPT via ChatGPT/Gizmo (OpenAI)
 - Zapier Webhook URL voor meldingen
 - Referentie-CSV met inflatiecijfers (bijv. CPI; bijdragen aan de jaarmutatie)
 - PDF-documenten van leveranciers met inflatie-informatie
 - (optioneel) Hosting van visuals of integratie met e-mailsysteem

--

##🧠 GPT Configuratie in OpenAI
 - Naam: Inflatie Tracker (of een andere naam naar keuze)
 - Beschrijving: Verwerkt volledige datasets en analyseert productinflatie.
 - Gedragscontext (Contextveld): Plak hier de instructions zoal in 'instructions.md' 

##📑 Referentiebestand (CSV)
 - Bestand met als naam bijv. CPI; bijdragen aan de jaarmutatie (%-punt).csv

 - Opslaan als knowledge bestand in de GPT
Kolommen moeten bevatten: productcategorie, land, en inflatie januari 2025
Enkel dit bestand mag als bron voor inflatiepercentages worden gebruikt

##📨 Zapier Webhook Instellen
Maak een Zap aan in Zapier
Gebruik de Catch Hook trigger
Webhook URL voeg je toe in de GPT-context of als plugin-koppeling
https://hooks.zapier.com/hooks/catch/22296654/2c5wukr/
Payload bevat:
Naam leverancier
E-mail
Lijst met producten waarbij inflatie te hoog is
Opgegeven inflatie & maximaal aanvaardbaar inflatiepercentage
📄 Leveranciersdata (PDF)
Bevat: productnamen, opgegeven inflatiepercentages, leverancier info
Wordt geüpload door gebruiker in GPT interface
GPT leest deze automatisch uit en vergelijkt met de CSV
📊 Grafiek Output
Wanneer één of meerdere producten over de limiet gaan:

GPT genereert automatisch een grafiek
Titel: "Inflatievergelijking per product – [Naam leverancier]"
Groepering per product
Twee staven per product: Leverancier vs. Maximaal aanvaardbaar
Emoji’s en labels bij sterke overschrijding
Laat me weten of je dit als markdown wil ontvangen of dat ik het direct in je README.md bestand mag formatteren.
