---
name: Fork Eat by Foodéfix
author:
    - Maud Gellée
    - Marion Armangaud
    - Carine Talendier
    - Jean Michel Remeur
    - Thomas Lacaze
    - Arsène Lapostolet
...


# Pitch

Système d'information de gestion de stocks de nourriture. 

- Stock de nourriture
- Gestion (création et import) des recettes (nb de personnes, durée)
- Planification des repas (ICAL)
- Génération de listes de courses
- Moteur de recherches de recettes
- Système de recommendation de recettes (possibilité de ML)

Bob veut des crêpes. Il ouvre sa recette de crêpe sur son SI Fork Eat. Le SI lui génère une liste de courses comportant : farine, oeufs, car il possède déjà du lait, et du sucre.

Après avoir suivi la recette sur son application mobile Fork Eat, il valide la finalisation de la recette, ce qui met à jours sont stock de produits.

Idées en vracs : 

- ⚠ Certain produits n'ont pas de dates de péremption
- Balance connectée
- Avoir une précision du suivi de la quantité des ingrédients personnalisable
- Assistant vocaux
- Intégration d'un système de la nutrition
- Sharding : accès aux recettes d'autres instances

# Etude de marché

## Concurrents

- https://github.com/julianpoy/RecipeSage
  - Pas de getsion de stock
  - Pas d'appli mobile
- https://github.com/AmandaBoatswain/McHacks2020
  - Notion de stock uniquement
  - Mauvaise UI/UX
- https://github.com/wiltonribeiro/nutrivali-app
  - Pas de gestion des recettes
- https://github.com/ayns01/Fridge
  - Stock uniquement
- https://github.com/Bernd-L/exDateMan
  - Dates de péremption uniquement
  - Pas d'appli mobile

## Valeur ajoutée

- Un système avec toutes les features intégrées entre elles
- Bonne UI/UX, bonne ergonomie
- App mobile et App Web selon les cas d'utilisation
- Auto-hébergeable, respectueux de la vie privée
- Open source

## Marché

Notre plateforme permet d'optimiser la consommation pour limiter le gachis et les déchets. Il est donc susceptible d'attirer les gens ayant une conviction écologique. Cette tendance est de plus en plus grandissante de nos jours.

Pour donner un ordre idée, 40% des foyer français ont tendance à faire attention au gâchis.

# Stack

- Application Mobile : Flutter
- Front Web : Angular
- Back : .NET
- Prototype UI : Figma
- RDMBS : Postgres (support natif de Full Text Search)

# Répartition 

- A Equipe Back : Marion + Arsène + Maud
- B Equipe Front : Carine + JM (support Marion et Arsène)
- C Equipe ML : Carine + Maud
- D Equipe Mobile : JM
- E Equipe Maquette : Maud + Carine + Thomas
- F Equipe Embarqué : Thomas + JM + (support Marion)
- G Equipe Infra : Thomas

Chef de Projet : Maud

# Livrables

|                                                           | V.0 | V.1 | V.2 | V.3+ |
|-----------------------------------------------------------|-----|-----|-----|------|
|                                                           |     |     |     |      |
| **Infra**                                                 | -   | -   | -   | -    |
| Pipelines CI/CD sur AMD64                                 | G   |     |     |      |
| Pipelines CI/CD sur ARM64                                 |     |     |     | G    |
| Build CI sur ARM64                                        | G   |     |     |      |
| **Backend**                                               | -   | -   | -   | -    |
| Logique inventaire                                        | A   |     |     |      |
| Logique de recettes : insérer                             | A   |     |     |      |
| Logique de recettes : importer                            |     |     | A   |      |
| Moteur de recettes : recherche par ingrédient             | A   |     |     |      |
| Moteur de recettes : full text search                     |     | A   |     |      |
| Moteur de recettes : recommandation naïve                 |     | A   |     |      |
| Gestion des codes barre                                   |     | A   |     |      |
| Alerte péremption                                         |     |     | A   |      |
| Alerte péremption : modulaire                             |     |     |     | A    |
| Moteur de recettes : nutrition et contrainte alimentaires |     |     | A   |      |
| **Machine Learning**                                      |     |     |     |      |
| Moteur de recette : machine learning                      |     |     |     | C    |
| **Application mobile**                                    | -   | -   | -   | -    |
| UI Gestion Stock                                          | D   |     |     |      |
| UI Gestion recette                                        | D   |     |     |      |
| Date de péremption via datepicker                         | D   |     |     |      |
| Date de péremption via vocal                              |     |     |     | D    |
| Scan des produits                                         |     |     | D   |      |
| Alerte péremption                                         |     |     | D   |      |
| Alerte péremption : modulaire                             |     |     |     | D    |
| **Web UI**                                                | -   | -   | -   | -    |
| UI Gestion Stock                                          |     | B   |     |      |
| UI Gestion recette                                        |     | B   |     |      |
| Alerte péremption                                         |     |     | B   |      |
| Alerte péremption : modulaire                             |     |     |     | B    |
| **Embarqué**                                              | -   | -   | -   | -    |
| Scan via caméra                                           |     | F   |     |      |
| Information du scan sur écran                             |     |     | F   |      |
| Pèse aliment                                              |     |     |     | F    |
| Date de péremption via vocal                              |     |     |     | F    |
| Suppression via vocal                                     |     |     |     | F    |



