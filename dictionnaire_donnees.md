# Dictionnaire des données

Extraction fictive des décomptes d'un assureur-maladie pour l'assurance obligatoire des
soins (LAMal), année de prestation 2024, population adulte (19 ans et plus).
**Toutes les données sont synthétiques** : aucune ligne ne correspond à une personne réelle.

Les fichiers sont liés par `id_assure` (personnes) et `id_prestataire` (prestataires de soins).

## assures.csv (une ligne par personne assurée)

| Variable | Description |
|---|---|
| id_assure | Identifiant pseudonymisé |
| annee_naissance | Année de naissance |
| sexe | F / M |
| canton | Canton de domicile |
| franchise_chf | Franchise annuelle choisie (CHF) |
| modele_assurance | standard, medecin_de_famille, hmo, telmed |
| couverture_accident | 1 si l'assurance-maladie couvre aussi les accidents (personnes sans assurance-accidents de l'employeur, LAA) |
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
| cause | maladie, accident ou maternite |
| type_prestation | medecin_generaliste, medecin_specialiste, laboratoire, ambulatoire_hospitalier, physiotherapie, soins_domicile, sage_femme, stationnaire |
| specialite | Spécialité du médecin (consultations de spécialistes uniquement) |
| id_prestataire | Identifiant pseudonymisé du prestataire qui facture |
| categorie_prestataire | Catégorie du prestataire qui facture (une analyse de laboratoire peut être facturée par un cabinet médical) |
| nb_jours_hospitalisation | Durée du séjour (stationnaire uniquement) |
| cout_chf | Montant décompté à la charge de l'assurance obligatoire. Pour le stationnaire : part de l'assureur uniquement |
| participation_chf | Part payée par l'assuré·e (franchise, quote-part, contribution hospitalière) |

## medicaments.csv (une ligne par médicament remis ou administré en ambulatoire)

Le fichier ne contient qu'une **sélection d'environ 85 substances** (traitements cardiovasculaires et
métaboliques, autres traitements chroniques fréquents, épisodes aigus courants, principaux traitements
de spécialité). Il ne représente pas l'ensemble des médicaments remboursés : la part des médicaments
dans les coûts totaux y est donc plus faible que dans la statistique officielle (environ 20 %).

| Variable | Description |
|---|---|
| id_ligne | Identifiant de la ligne de décompte |
| id_assure | Identifiant de la personne |
| date_delivrance | Date de délivrance ou d'administration |
| code_atc | Code ATC du produit (classification anatomique, thérapeutique et chimique de l'OMS) |
| id_prestataire | Pharmacie, hôpital ou cabinet qui facture le médicament |
| nb_emballages | Nombre d'emballages délivrés |
| taille_emballage | Nombre d'unités par emballage |
| cout_chf | Montant décompté (CHF) |
| participation_chf | Part payée par l'assuré·e |

## referentiel_atc.csv

Table de correspondance entre `code_atc`, substance(s), groupe anatomique (niveau 1) et
libellé du groupe ATC de niveau 4.

## referentiel_prestataires.csv

Catégorie, canton, spécialité (médecins spécialistes) et statut juridique (hôpitaux : public ou privé)
de chaque prestataire présent dans les décomptes.

## Rappels

- Les montants sont ceux **décomptés par l'assureur** ; ce ne sont pas nécessairement
  tous les soins reçus par les assuré·es.
- Participation LAMal : franchise, puis quote-part de 10% plafonnée à
  700 CHF par an, et contribution de 15 CHF par jour d'hospitalisation.
  Les prestations de maternité, et toutes les prestations dès la 13e semaine de grossesse et
  jusqu'à 8 semaines après l'accouchement, sont exonérées de participation.
- Les accidents ne figurent que pour les personnes dont la LAMal couvre le risque accident.
