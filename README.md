# 🖧 NetPractice 

NetPractice est un projet visant à apprendre les bases du réseau et de l'adressage IP.\
Il permet d'acquérir une compréhension approfondie des concepts liés aux adresses IP, aux sous-réseaux, aux masques, au routage et aux protocoles de communication.

---
## 📖 Definitions

### 🔹 **Adresse IP (Internet Protocol)**
Une adresse IP est un identifiant unique attribué à chaque appareil connecté à un réseau informatique. Elle permet aux machines de s’identifier et de communiquer entre elles sur Internet ou un réseau local.  
**Format IPv4 :** 4 nombres séparés par des points (ex. `192.168.1.1`), chacun représentant 8 bits, soit un total de **32 bits**.

### 🔹 **Masque de sous-réseau**
Un masque de sous-réseau est un ensemble de bits qui détermine la partie **réseau** et la partie **hôte** d’une adresse IP. Il est souvent noté sous forme décimale pointée (ex. `255.255.255.0`) ou en notation CIDR (`/24` indique que les 24 premiers bits sont réservés à l’identification du réseau).  
**Exemple :**  
- `192.168.1.10 / 255.255.255.0` → La partie réseau est `192.168.1.x`, la partie hôte est `x`.

### 🔹 **Routage**
Le routage est le processus de transmission de données d’un réseau à un autre via des équipements appelés **routeurs**. Il utilise des **tables de routage** pour déterminer le chemin optimal qu’un paquet de données doit emprunter.

### 🔹 **Switch (Commutateur)**
Un switch est un équipement réseau qui connecte plusieurs appareils au sein d’un **réseau local (LAN)**. Contrairement à un routeur, il fonctionne uniquement au niveau **du réseau interne** et ne gère pas l’interconnexion entre différents réseaux.

### 🔹 **Protocole TCP/IP**
Le **TCP/IP** est l’ensemble des règles qui régissent la transmission des données sur Internet. Il se compose de plusieurs couches :
- **TCP (Transmission Control Protocol)** : Assure la transmission fiable des paquets de données en garantissant leur ordre et leur intégrité.
- **IP (Internet Protocol)** : Assure l’adressage et le routage des paquets à travers les réseaux.

### 🔹 **Notation CIDR (Classless Inter-Domain Routing)**
La notation **CIDR** est une méthode permettant de représenter efficacement une plage d’adresses IP et son masque de sous-réseau. Elle simplifie l’écriture et optimise l'utilisation des adresses.  
**Exemple :**  
- `192.168.1.0/24` signifie que les **24 premiers bits** définissent le réseau et que les **8 bits restants** sont dédiés aux hôtes.

## 📌 1. Unicité de l’adresse IP

Lorsqu’une communication réseau est établie, trois éléments sont essentiels :
1. **Le nom de la machine distante** 🖥️ : Qui est l’hôte distant ?
2. **L’adresse IP** 🌍 : Où se trouve cet hôte ?
3. **Le chemin d’accès** : Comment y parvenir ?

Les machines communiquent uniquement en **binaire**. Une adresse IP (version 4 - IPv4) est standardisée sur **32 bits**, ce qui permet de structurer l'adressage réseau.

###  Deux informations clés contenues dans une adresse IPv4 :
- **L’adresse réseau**
- **L’adresse de l’hôte**

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

### **TCP (Transmission Control Protocol)**
- **Protocole de communication fiable** assurant la transmission des données 📦.
- Avant d’envoyer des données, il établit une **connexion (handshake)**.
- **Garantit l’ordre des paquets** et retransmet ceux qui sont perdus.
- **Gère la congestion** pour éviter d’encombrer le réseau.

### **Routage des paquets**
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
Niveau 6 - Configuration de base du routage
</details>
<summary>Niveau 6</summary>
![6](https://github.com/user-attachments/assets/f47a471c-11d5-4f64-8051-66de9d4ddd96)
Adresse IP et Masque de sous-réseau : Chaque appareil possède une adresse IP unique attribuée à son interface.
Passerelle par défaut : Un hôte doit avoir une passerelle configurée pour acheminer le trafic en dehors de son réseau local.
Routage statique : L'ajout manuel d'une route permettant la communication entre différents sous-réseaux.
Dans ce niveau, il faut configurer les routes sur les hôtes et les routeurs afin d'assurer la communication entre webserv.non-real.com et Somewhere on the Net.
</details>
level : 6

---

