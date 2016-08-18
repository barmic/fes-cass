# Cassandra

FES sur Cassandra

## Une base de données NoSQL orienté large raw

- NoSQL ?
 - Les limites de SQL (montée en charge lié aux grosses garanties offertes)
 - La nomenclature NoSQL (document, clef-valeur, graphe, colonne, autres)
- Cassandra → orienté longue ligne
 - un modèle paire à paire pour des données structurées ou semi-structurées
 - avantage : montée en charge linéaire, gestion du multi-dc, résistance aux pannes
 - inconvénient : difficulté de modélisation, requêtage un peu trop simple
- Quand s'en servir ? (parler de l'experience Tagsys ?)
 - énorme volume de données, multi-dc, résistance aux pannes
 - quand on monte de grosses architectures type Big Data (comme l'architecture lambda)
 - quand le modèle de données conincide bien
 - pas quand on est dans un mode « je requête n'importe quoi, n'importe comment » (ou alors pas tout seul)
 - pas quand on veut être léger (Cassandra consomme 4 Gio minimum)

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
dedans et faire des requètes simples (en utilisant [zeppelin](https://zeppelin.apache.org/)).

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
- TTL (→ parler des tombstone et des SSTables : notamment les cas au limites si on crèe trop de tombstones et que du coup cassandra refuse de repondre …)
- JSON

## Retour d'experience

Présenter l'experience Tagsys (OS, materiel, noœud unique, passage à du
relationnel, maintient du modèle de données).
// _Monitoring en utilisant https://jolokia.org/_
Présentation de quelques futures fonctionnalitées cool comme l'ajout de Lucene :)
