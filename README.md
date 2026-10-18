# Interconnexion et Routage de Bout en Bout sous GNS3

Ce projet valide la configuration complète d'une topologie réseau sous GNS3 interconnectant un routeur Client, FAI1 (AS 100) et FAI2 (AS 200).

## 🌐 Topologie Réseau
- **CR (Client)** : Route par défaut vers FAI1 (`10.10.10.2`), LAN `192.168.1.0/24`.
- **FAI1 (AS 100)** : Liaison Série vers CR (`10.10.10.0/24`), interconnexion BGP avec FAI2 (`172.16.1.0/24`).
- **FAI2 (AS 200)** : Réseau `192.168.200.0/24`, route retour vers le client.

## 🛠️ Commandes de Vérification
- Validation des interfaces : `show ip interface brief`
- Table de routage : `show ip route`
- État de la session BGP : `show ip bgp summary`
- Validation de connectivité : `ping 192.168.200.1 source 192.168.1.1` (100% de réussite)
- Traçage de route : `traceroute 192.168.200.1 source 192.168.1.1`
