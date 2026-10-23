# Personnes traitées pour hypertension : profil, recours aux soins et coûts

Atelier du module d'économie de la santé, Master en Sciences Biomédicales, Université de Genève.

| Version | Ouvrir |
|---|---|
| Python | [![Ouvrir dans Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/daderidd/heco-tp-hypertension/blob/main/tp_hypertension.ipynb) |
| R | [![Ouvrir dans Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/daderidd/heco-tp-hypertension/blob/main/tp_hypertension_R.ipynb) |

Les deux versions contiennent les mêmes analyses et donnent les mêmes résultats. Choisir celle du langage que le groupe connaît le mieux.

## Démarrage

1. Cliquer sur le bouton **Ouvrir dans Colab** de la version choisie. Un navigateur et un compte Google suffisent, sur Windows comme sur macOS, sans rien installer.
2. Dans Colab : **Fichier → Enregistrer une copie dans Drive**. Le groupe travaille sur sa propre copie.
3. **Exécution → Tout exécuter** pour vérifier que les données se chargent. Dans la version R, la première cellule installe au besoin les paquets manquants, ce qui peut prendre un moment la première fois.

Les données sont lues directement depuis ce dépôt : aucun fichier à télécharger.

## En cas de problème

- **Colab s'est déconnecté** après une longue inactivité : relancer **Exécution → Tout exécuter**.
- **« Tout exécuter » s'arrête sur un exercice** : la cellule est incomplète. La compléter, ou la recommenter.
- **Le raccourci Ctrl + / (Cmd + / sur Mac) ne marche pas**, par exemple avec certains claviers suisses : effacer à la main le `# ` au début de chaque ligne.
- **Les données ne se chargent pas** (réseau) : créer un dossier `donnees` dans Colab (panneau Fichiers, à gauche) et y déposer les fichiers CSV de ce dépôt. Le notebook les lit en priorité.

## Contenu

| Fichier | Contenu |
|---|---|
| `tp_hypertension.ipynb` | Notebook de l'atelier, version Python |
| `tp_hypertension_R.ipynb` | Notebook de l'atelier, version R |
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
