# 📊 Power BI -- Analyse des Ventes, Produits et Boutiques

## 👩‍💻 Projet réalisé par

**Ghizlane Lamzouri**\
Bac+5 -- Ingénierie Informatique\
Spécialité : Intelligence Artificielle & Data Analytics

------------------------------------------------------------------------

## 📁 Description du Projet

Ce projet Power BI a pour objectif de fournir une analyse complète et
interactive des ventes, des produits et des boutiques d'une entreprise
fictive.\
Il s'appuie sur un modèle de données en étoile, des mesures DAX et
plusieurs pages de visualisation permettant d'explorer les KPI
commerciaux.

------------------------------------------------------------------------

## 📂 Contenu du Repository

    📦 PowerBI-Sales-Analysis
    │
    ├── ProjetPowerBi.pbix          # Fichier Power BI complet
    ├── README.md                   # Documentation GitHub
    ├── Rapport_Projet_PowerBI.pdf  # Rapport PDF (optionnel)
    └── images/                     # Captures d’écran du dashboard

------------------------------------------------------------------------

## 🗂️ Modèle de Données (Star Schema)

### Table de faits

-   Sales

### Tables de dimensions

-   Produits\
-   Sous Catégories Produits\
-   Categories Produits\
-   Boutiques\
-   Geographie\
-   DateTable
-  sales
-  DateTable

------------------------------------------------------------------------

## 🧮 Principales Mesures DAX

``` dax
NB produits = COUNT(Produits[IdProduit])

PaysSelected = SELECTEDVALUE(Geographie[Pays], "Pays")

Nombre Boutique = COUNT(Boutiques[IdBoutique])

CA = SUM(Sales[Montant vente après remise])

CA N-1 =
CALCULATE([CA], SAMEPERIODLASTYEAR(DateTable[Date]))

Ecart vente = DIVIDE([CA] - [CA N-1], [CA N-1])

Nb ventes = COUNT(Sales[IdVente])

Remise =
IF(Sales[Montant vente] < 2000, 0,
    IF(Sales[Montant vente] <= 5000, 0.05, 0.1))

Montant vente après remise =
Sales[Montant vente] * (1 - Sales[Remise])

Montant vente =
(Sales[Quantité de vente] - Sales[Quantité de retour]) *
RELATED(Produits[Prix unitaire])
```

------------------------------------------------------------------------

## 📊 Pages du Dashboard

### 🔹 Page 1 : Boutiques

-   Répartition géographique\
-   Types de boutique\
-   Statut On/Off\
-   Carte interactive\
-   Ventes par boutique

### 🔹 Page 2 : Produits

-   Nombre total de produits\
-   Produits par catégorie & sous-catégorie\
-   Sankey\
-   Ventes vs retours\
-   Tableau détaillé

### 🔹 Page 3 : Ventes

-   CA total\
-   CA N-1\
-   Écart %\
-   Analyse temporelle\
-   CA par catégorie, marque, classe

------------------------------------------------------------------------

## 📘 Documentation intégrée

Une page dédiée dans Power BI contient :\
- Description du dataset\
- Dictionnaire des mesures DAX\
- Objectifs du dashboard\
- Schéma du modèle de données

------------------------------------------------------------------------

## 🏁 Conclusion

Ce projet démontre la maîtrise de :\
✔ Préparation & modélisation des données\
✔ Création de mesures DAX avancées\
✔ Conception d'un dashboard professionnel\
✔ Documentation claire et complète

------------------------------------------------------------------------

## 📬 Contact

**Ghizlane Lamzouri**\
Data Analyst & IA Engineer
