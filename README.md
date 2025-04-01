<<<<<<< HEAD
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

## 📂 Structuur

=======
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
   - Matcht producten met categorieën uit `inflatie_data.csv`
   - Haalt maximaal aanvaardbare inflatie per categorie en land op
   - Vergelijkt met opgegeven inflatie
3. Bij overschrijding:
   - Stuurt JSON naar Zapier webhook
   - Genereert grafiek met verschillen
   - Voegt analyse toe aan e-mail

---

## 📂 Structuur


