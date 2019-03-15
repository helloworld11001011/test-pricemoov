# Pricemoov - Test Data Engineer - 2019

## Description

Ce dataset comporte des données de ventes (transaction) pour chaque date et chaque produit:

```
 transaction_id | date | product_id | value
 9 | 2017-01-01 | 111 | 12
 ---
 se lit : le 2017-01-01 il y a eu 12 ventes pour le produit 111
 au cours de la transaction 9.

 ```


 Chaque produit appartient à une sous-famille qui elle-même appartient à une famille.
 Pour déterminer la sous-famille il suffit de conserver les 2 premiers chiffres du code produit
 et pour déterminer la famille, il suffit de conserver son premier chiffre.
 Ainsi le produit 111 appartient à la sous-famille 11 qui appartient à la famille 1.

 On peut donc représenter l'ensemble des produits sous forme d'arbre :
 ```
                  1
      –––––––––––––––––––––––
      |                     |
      11                    12
 –––––––––––––         –––––––––––
 |      |    |        |           |
 111    113   112     121         122
 ```




 1. Construire une table regroupant le nombre de vente **par jour** à tous les niveaux d'aggregations (produit, famille, sous famille) (toute transaction confondue).

 2. Construire une table synthésisant les ventes **par semaine** à tous les niveaux d'aggregations et (toute transaction confondue).

 3. Ajouter des colonnes permettant de savoir si les ventes pour la semaine en cours sont à la hausse ou à la baisse (up, down), de combien en écart relatif (-1%, +2%)
  - par rapport à la semaine précédente
  - par rapport à la même semaine de l'année précédente

**NB**:
Le code devra respecter les normes PEP8 (https://www.python.org/dev/peps/pep-0008/) être commité et pushé sur un répo git.
