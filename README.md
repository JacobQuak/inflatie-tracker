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

Deze sectie beschrijft hoe je de Inflatie Tracker GPT kunt nabouwen en welke onderdelen je nodig hebt.

---

## 📦 Benodigdheden

- ✅ Custom GPT via ChatGPT/Gizmo (OpenAI)
- ✅ Zapier Webhook URL voor meldingen
- ✅ Referentie-CSV met inflatiecijfers (bijv. *CPI; bijdragen aan de jaarmutatie*)
- ✅ PDF-documenten van leveranciers met inflatie-informatie
- 🟡 (Optioneel) Hosting van visuals of integratie met e-mailsysteem

---

## 🧠 GPT Configuratie in OpenAI

- **Naam**: Inflatie Tracker (of een andere naam naar keuze)
- **Beschrijving**: Verwerkt volledige datasets en analyseert productinflatie.
- **Gedragscontext (Contextveld)**: Plak hier de volledige instructies zoals gedefinieerd in `instructions.md`

---

## 📑 Referentiebestand (CSV)

- Bestandsnaam: `CPI; bijdragen aan de jaarmutatie (%-punt).csv`
- Locatie: Toevoegen als knowledge bestand in je GPT (of in de repo onder `/dataset`)
- **Vereiste kolommen**:
  - `productcategorie`
  - `land`
  - `inflatie januari 2025`
- 🔒 Enkel dit bestand mag als bron gebruikt worden voor inflatiepercentages

---

## 📨 Zapier Webhook Instellen

1. Maak een nieuwe Zap aan in Zapier
2. Kies trigger: **Catch Hook**
3. Gebruik de webhook URL die de trigger voor je gecreëerd heeft. Voeg deze url ook toe aan de handeling waarvan het schema in 'webhook_openapi.json' staat
4. Bouw de zap na zoals in 'Inflatie tracker | Zapier.png'
   

