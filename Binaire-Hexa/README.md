# Système binaire et Héxadécimale

Challenge S04 TSSR @ Wild Code School - rendu le 17 mars

# Contexte

* Que vaut 5𝐵1(ℎ𝑒𝑥𝑎) en base 2 ?

* Que vaut 0xA en décimal ?

* En hexadécimal, quelles sont les valeurs maximales et minimales que l'on peut représenter sur 1 octets ?

* Donner la représentation binaire et hexadécimale de l'adresse IP 192.168.1.80

## Critères d'acceptation

Répondre correctement aux 4 questions sous forme de fichier markdown

* 5 = 0101, B = 1011, 1 = 0001 >> donc 5B1 vaut 0101 1011 0001 en base binaire

* 0xA = 00000000000000A, on ne tient donc pas compte des 0 et A = 10 en décimale

* un octet correspond à 8 bits, donc les valeurs maximales seront 00000000 et 11111111  
00000000 = 0 en héxa  
11111111 doit être découpé en 1111 1111, 1111 = en héxa, donc 11111111 = FF

* 192.168.1.80  
192 = 11000000 en binaire soit 1100 0000 = C0 en héxa  
168 = 10101000 en binaire soit 1010 1000 = A8 en héxa  
1 = 00000001 en binaire soit 0000 0001 = 01 en héxa  
80 = 01010000 en binaire soit 0101 0000 = 50 en héxa  
On aura donc en binaire 11000000.10101000.00000001.01010000, et C0.A8.01.50 en héxa