# Personnes traitées pour hypertension : profil, recours aux soins et coûts

Atelier du module d'économie de la santé, Master en Sciences Biomédicales, Université de Genève.

[![Ouvrir dans Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/daderidd/heco-tp-hypertension/blob/main/tp_hypertension.ipynb)

## Démarrage

1. Cliquer sur le bouton **Ouvrir dans Colab** ci-dessus (un compte Google suffit, aucune installation).
2. Dans Colab : **Fichier → Enregistrer une copie dans Drive**. Le groupe travaille sur sa propre copie.
3. **Exécution → Tout exécuter** pour vérifier que les données se chargent.

Les données sont lues directement depuis ce dépôt : aucun fichier à télécharger.

## Contenu

| Fichier | Contenu |
|---|---|
| `tp_hypertension.ipynb` | Notebook de l'atelier |
| `dictionnaire_donnees.md` | Description des fichiers et des variables |
| `donnees/assures.csv` | Une ligne par personne assurée |
| `donnees/prestations.csv` | Décomptes hors médicaments |
| `donnees/medicaments.csv` | Médicaments remis ou administrés en ambulatoire (code ATC, prestataire) |
| `donnees/referentiel_atc.csv` | Correspondance code ATC / substance / groupe |
| `donnees/referentiel_prestataires.csv` | Catégorie, canton, spécialité et statut juridique des prestataires de soins |

## Avertissement

**Toutes les données sont synthétiques.** Elles imitent la structure des décomptes d'un
assureur-maladie suisse (LAMal, année 2024, adultes) mais ne correspondent à aucune personne
réelle. Les ordres de grandeur sont plausibles sans constituer des statistiques officielles :
ils ne doivent pas être cités comme tels.
