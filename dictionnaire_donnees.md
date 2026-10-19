# Dictionnaire des données

Extraction fictive des décomptes d'un assureur-maladie pour l'assurance obligatoire des
soins (LAMal), année de prestation 2024, population adulte (19 ans et plus).
**Toutes les données sont synthétiques** : aucune ligne ne correspond à une personne réelle.

Les fichiers sont liés par la variable `id_assure`.

## assures.csv (une ligne par personne assurée)

| Variable | Description |
|---|---|
| id_assure | Identifiant pseudonymisé |
| annee_naissance | Année de naissance |
| sexe | F / M |
| canton | Canton de domicile |
| franchise_chf | Franchise annuelle choisie (CHF) |
| modele_assurance | standard, medecin_de_famille, hmo, telmed |
| subside | 1 si la personne bénéficie d'une réduction individuelle de primes |
| debut_couverture / fin_couverture | Période d'assurance auprès de l'assureur durant l'année |
| motif_fin_couverture | Vide si assuré·e toute l'année ; sinon deces ou changement_assureur_ou_depart |

## prestations.csv (une ligne par position de décompte, hors médicaments)

| Variable | Description |
|---|---|
| id_ligne | Identifiant de la ligne de décompte |
| id_assure | Identifiant de la personne |
| date_prestation | Date de la prestation (date d'entrée pour un séjour hospitalier) |
| date_decompte | Date de traitement par l'assureur |
| type_prestation | medecin_generaliste, medecin_specialiste, laboratoire, ambulatoire_hospitalier, physiotherapie, soins_domicile, stationnaire |
| specialite | Spécialité du médecin (consultations de spécialistes uniquement) |
| nb_jours_hospitalisation | Durée du séjour (stationnaire uniquement) |
| cout_chf | Montant décompté à la charge de l'assurance obligatoire. Pour le stationnaire : part de l'assureur uniquement |
| participation_chf | Part payée par l'assuré·e (franchise, quote-part, contribution hospitalière) |

## medicaments.csv (une ligne par délivrance en pharmacie)

| Variable | Description |
|---|---|
| id_ligne | Identifiant de la ligne de décompte |
| id_assure | Identifiant de la personne |
| date_delivrance | Date de délivrance |
| code_atc | Code ATC du produit (classification anatomique, thérapeutique et chimique de l'OMS) |
| nb_emballages | Nombre d'emballages délivrés |
| taille_emballage | Nombre d'unités par emballage |
| cout_chf | Montant décompté (CHF) |
| participation_chf | Part payée par l'assuré·e |

## referentiel_atc.csv

Table de correspondance entre `code_atc`, substance(s), groupe anatomique (niveau 1) et
libellé du groupe ATC de niveau 4 (renseigné pour les groupes cardiovasculaires et métaboliques).

## Rappels

- Les montants sont ceux **décomptés par l'assureur** ; ce ne sont pas nécessairement
  tous les soins reçus par les assuré·es.
- Participation LAMal : franchise, puis quote-part de 10% plafonnée à
  700 CHF par an, et contribution de 15 CHF par jour d'hospitalisation.
