# Cassandra

FES sur Cassandra

// _Je suis peut etre medisant mais pas sur que tout le monde voit ce qu'est une base NoSQL_

## Points clefs

- montée en charge linéaire
- continuous availability
- multi data-center native
- operation simple (facilité de déploiement par exemple)
- Big Data (Spark en particulier)
- // _Pro et cons par rapport au autres solutions NoSQL_

## Architecture

Expliquer que c'est un fonctionnement P2P entre les nœuds cassandra comment
fonctionne :

- Distribution/partitionnement des données
- Nœuds virtuels pour gérer la monté et la descente de charge
- Réplication des données
- Nœud coordinateur // _Ou le Quorum => et du coup le split brain, ca peut servir ^^'_ 
- Niveau de consistence

## Data modeling

- Keyspace/table
- Queries
- User Defined Type/Function/Aggregate
- Data compaction
- Partition Key, Clustering Columns
- Collections

Avoir un exercice (présentation d'un contexte et de quelques requêtes que l'on
veut pouvoir exécuter) pour créer son premier keyspace/table, insérer des données
dedans et faire des requètes simples. // _En python bien sur :p_

## Multi-DC

Quelques explications sur la configuration multi-DC.
Notament pour la stratégie de réplication.
Peut être expliquer succintement la réparation des données.

Exercice/démonstration : on fait tomber des instances cassandra et on voit quels
niveau de consistence continu de fonctionner.

## Data modeling 2

Nouvel exercice où l'on reprend la base précédente, mais on ajoute de nouvelles
requètes pour montrer l'intérêt des vues materialisées.

- Materialized view
- LightWeight Transaction
- Batch
- TTL (→ parler des tombstone et des SSTables) // _Notamment les cas au limites si on crèe trop de tombstones et que du coup cassandra refuse de repondre ..._
- JSON

## Retour d'experience

Présenter l'experience Tagsys (OS, materiel, noœud unique, passage à du
relationnel, maintient du modèle de données).
// _Monitoring en utilisant https://jolokia.org/_
// _Présentation de quelques futures fonctionnalitées cool comme l'ajout de Lucene :)_
