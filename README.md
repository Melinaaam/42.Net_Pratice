# 🖧 NetPractice 

NetPractice est un projet pédagogique de l'école 42 visant à apprendre les bases du réseau et de l'adressage IP. Il permet d'acquérir une compréhension approfondie des concepts liés aux adresses IP, aux sous-réseaux, aux masques, au routage et aux protocoles de communication.

---

## 📌 1. Unicité de l’adresse IP

Lorsqu’une communication réseau est établie, trois éléments sont essentiels :
1. **Le nom de la machine distante** 🖥️ : Qui est l’hôte distant ?
2. **L’adresse IP** 🌍 : Où se trouve cet hôte ?
3. **Le chemin d’accès** 🚀 : Comment y parvenir ?

Les machines communiquent uniquement en **binaire**. Une adresse IP (version 4 - IPv4) est standardisée sur **32 bits**, ce qui permet de structurer l'adressage réseau.

### 🏷️ Deux informations clés contenues dans une adresse IPv4 :
- **L’adresse réseau** 🏠
- **L’adresse de l’hôte** 👤

Ces deux éléments forment ensemble une **adresse unique** sur un réseau.

---

## 📌 2. Délivrance des adresses IPv4

### 🔐 **Adresses privées**
- Tout administrateur réseau peut attribuer librement des adresses **privées**, tant qu’elles restent **hors-ligne**.
- Définies par la RFC **1918**.

### 🌍 **Adresses publiques**
- Délivrées par des **organismes mondiaux** assurant leur unicité.
- Fournies généralement par les **FAI** (Fournisseurs d’Accès Internet).

### 📊 **Classification des adresses IP**
| Classe | Réseau | Hôtes |
|--------|--------|------|
| **A**  | 1 octet | 3 octets |
| **B**  | 2 octets | 2 octets |
| **C**  | 3 octets | 1 octet |

---

## 📌 3. Routeurs et commutateurs

### 🔄 **Routeur**
- Permet de **connecter plusieurs réseaux** entre eux.
- Possède autant d’interfaces réseau que de connexions.
- Veille à ce que les adresses d’un réseau ne passent pas vers un autre réseau.

### 🔗 **Switch (commutateur)**
- Relie les machines d’un réseau local 🏠 (LAN).
- Fonctionne avec des **ports RJ45** pour connecter les équipements.
- Un réseau local peut accéder à Internet via un **routeur**.

---

## 📌 4. Adresses particulières

| Type d’adresse | Description |
|---------------|-------------|
| **Loopback** | `127.0.0.1` - Adresse permettant à un PC de communiquer avec lui-même |
| **Adresse non spécifiée** | `0.0.0.0` - Désigne toutes les interfaces |
| **Adresses privées** | `192.168.X.Y` ou `10.X.X.X` pour les réseaux internes |
| **APIPA** | `169.254.X.X` - Assignation automatique lorsqu’aucun serveur DHCP n’est trouvé |
| **Broadcast** | `255.255.255.255` - Message envoyé à tous les appareils d’un réseau |

---

## 📌 5. Masques de sous-réseau

Un **masque de sous-réseau** permet de séparer :
- 🏠 **La partie réseau**
- 👤 **La partie hôte**

### 📝 **Exemple :**
- **IP** : `192.168.1.10`
- **Masque** : `255.255.255.0`
- **En binaire** : `192.168.1.10 -> 11000000.10101000.00000001.00001010 255.255.255.0 -> 11111111.11111111.11111111.00000000`

- Partie **réseau** : `192.168.1.0`
- Partie **hôte** : `.10`

📌 **Notation CIDR** :
- `192.168.1.0/24` signifie que **les 24 premiers bits** définissent le réseau.
- `2^(32-24) = 256` adresses possibles.

---

## 📌 6. Le protocole TCP/IP

### 🌍 **TCP (Transmission Control Protocol)**
- **Protocole de communication fiable** assurant la transmission des données 📦.
- Avant d’envoyer des données, il établit une **connexion (handshake)**.
- **Garantit l’ordre des paquets** et retransmet ceux qui sont perdus.
- **Gère la congestion** pour éviter d’encombrer le réseau.

### 🚀 **Routage des paquets**
- Les paquets IP transitent à travers différents réseaux pour atteindre leur destination.
- Utilisation des **tables de routage** pour définir le chemin optimal.

---

## 📌 7. Opération AND et Masque réseau

L’opération **AND** est utilisée pour déterminer l’adresse réseau d’une machine.

### 📝 **Exemple :**
| Bit 1 | Bit 2 | Résultat |
|------|------|------|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

Avec :
- **Adresse IP** : `192.168.1.10`
- **Masque réseau** : `255.255.255.0`

La conversion en binaire et l’opération AND permettent de déterminer **l’adresse réseau** `192.168.1.0`.

---

## 📌 8. Exercices NetPractice

Le projet NetPractice propose **10 niveaux** progressifs permettant de tester ses connaissances en adressage réseau.

📸 **Ajoutez ici des images des 10 niveaux du projet.**

---

## 🎯 **Objectifs pédagogiques**
- Comprendre et manipuler l’adressage **IPv4**.
- Apprendre à utiliser les **masques de sous-réseau**.
- Connaître la différence entre **adresses privées et publiques**.
- Comprendre les **routeurs et commutateurs**.
- Appliquer des notions comme **le routage, la transmission TCP/IP et la segmentation des réseaux**.

---

## 📌 **Conclusion**
NetPractice est un projet essentiel pour toute personne souhaitant **maîtriser les bases des réseaux**. En réalisant les exercices et en expérimentant avec les sous-réseaux, on acquiert une compréhension approfondie de la structure et de la gestion des réseaux informatiques. 🚀

---

📌 **Références :**
- [RFC 1918 - Adresses privées](https://datatracker.ietf.org/doc/html/rfc1918)
- [IPv4 et sous-réseaux](https://fr.wikipedia.org/wiki/IPv4)
- [TCP/IP et routage](https://fr.wikipedia.org/wiki/TCP/IP)

# 42.Net_Pratice
