# Découpage de réseaux IP

Challenge S04 TSSR @ Wild Code School - rendu le 17 mars 2024

## Contexte

Une société fictive a 4 pôles informatiques. Le réseau est en 172.16.1.0/24.
Découper ce réseau de 2 manières, symétrique et asymétrique, pour que chaque pôle ci-dessous puissent avoir assez d'adresse pour chaque équipement.

Le Pôle informatique (6 bureaux, environ 50 équipements au total)
Le Pôle développement (6 bureaux, environ 12 équipements au total)
Le Pôle Administratif (4 bureaux, environ 20 équipements au total)
Le Pôle Technicien (4 bureaux, environ 15 équipements au total)

### Découpage symétrique

Nous allons par conséquent découper notre réseau en 4 sous-réseaux de taille identique, chacun devant avoir au moins 50 équipements adressables, pour palier à la demande du Pôle informatique qui comprend 50 équipements au total

En regadant la table de puissance de 2, et en cherchant un nombre supérieur à 50, dans notre cas c'est _2_ puissance _6_ qui fait un total de _64_ adresses

Ansi, le nombre d'adresses disponibles par sous-réseaux sera de 64-2 (une pour le réseau, une pour la diffusion), soit 62

Le calcul du CIDR se fera 32-6 (nombre de la puissance utilisé) soit 26

Ce qui nous donneras sous forme de tableau

|Service|Adresse réseau| Adresse de broacast| Adresse de début de plage|Adresse de fin de plage|
|:-:|:-:|:-:|:-:|:-:|
|Pôle Informatique|172.16.1.0/26|172.16.1.63|172.16.1.1|172.16.1.62|
|Pôle Développement|172.16.1.64/26|172.16.1.127|172.16.1.65|172.16.1.126|
|Pôle Administratif|172.16.1.128/26|172.16.1.191|172.16.1.129|172.16.1.190|
|Pôle Technicien|172.16.1.192/26|172.16.1.255|172.16.1.193|172.16.1.254|

### Découpage asymétrique

Il faut maintenant découper le réseaux pour que chaque sous-réseaux est juste ce dont il a besoin

Donc par rapport à la liste des équipements

* Pôle Informatique (50 équipements) soit  2puissance6 -2 = 64-2 = 62
* Pôle Développement (12 équipements) soit 2puissance4 -2 = 16-2 = 14
* Pôle Administratif (20 équipements) soit 2puissance5 -2 = 32-2 =30
* Pôle Technicien (15 équipements) soit 2puissance5 -2 = 32-2 = 30

Ce qui nous donne convertit en tableau

|Service|Adresse réseau| Adresse de broacast| Adresse de début de plage|Adresse de fin de plage|
|:-:|:-:|:-:|:-:|:-:|
|Pôle Informatique|172.16.1.0/26|172.16.1.63|172.16.1.1|172.16.1.62|
|Pôle Développement|172.16.1.64/28|172.16.1.79|172.16.1.65|172.16.1.78|
|Pôle Administratif|172.16.1.80/27|172.16.1.111|172.16.1.81|172.16.1.110|
|Pôle Technicien|172.16.1.112/27|172.16.1.143|172.16.1.113|172.16.1.142|