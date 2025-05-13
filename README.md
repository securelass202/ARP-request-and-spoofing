# 🔎 ARP Request & ARP Spoofing

## 📘 Qu’est-ce que l’ARP ?

**ARP (Address Resolution Protocol)** est un protocole du réseau local qui permet à un ordinateur de trouver **l'adresse MAC** correspondant à une **adresse IP** sur le même réseau.

> 🧠 Exemple : "Je connais l'adresse IP 192.168.1.10, mais je veux savoir à quelle carte réseau (adresse MAC) elle appartient."

---

## 📨 ARP Request – Fonctionnement normal

### 📦 Définition

Une **ARP Request** est une requête envoyée par un appareil pour **demander l’adresse MAC** correspondant à une **adresse IP spécifique**.

### 🔁 Processus

1. Un PC veut parler à une IP locale (ex. 192.168.1.5).
2. Il ne connaît pas son adresse MAC.
3. Il envoie un message en broadcast :
   > "Qui a l’IP 192.168.1.5 ? Donne-moi ton adresse MAC."
4. Le propriétaire de cette IP répond avec un **ARP Reply** contenant sa MAC.

### 🧠 Analogie

C’est comme si tu étais dans une salle remplie de gens, et tu cries :
> "Qui s’appelle Sophie ? J’ai un message pour toi !"

Et Sophie répond :
> "C’est moi ! Je suis à la chaise 5 (adresse MAC)."

---

## ⚠️ ARP Spoofing – Une attaque dangereuse

### 📦 Définition

L’**ARP Spoofing (ou ARP Poisoning)** est une attaque où un pirate envoie de **fausses réponses ARP** sur le réseau pour **se faire passer pour un autre appareil**, souvent la **passerelle (gateway)**.

> L’objectif : **intercepter, modifier ou bloquer** le trafic réseau. C’est une attaque **de type Man-in-the-Middle (MITM)**.

### 🎯 Exemple d’attaque

1. Alice veut parler à sa passerelle (192.168.1.1).
2. Le pirate (Mallory) envoie un faux ARP Reply à Alice :
   > "192.168.1.1, c’est moi (adresse MAC de Mallory)."
3. Alice envoie ses données au pirate, croyant qu’il s’agit du routeur.
4. Mallory intercepte ou modifie le trafic.

### 🧠 Analogie

Imagine que tu cries dans une salle :
> "Qui est le facteur du bâtiment ?"

Et un inconnu répond :
> "C’est moi ! Donne-moi ton courrier."

Tu lui donnes tout ton courrier… sauf que ce n’est pas le vrai facteur. Il lit ou modifie tes lettres avant de les rediriger.

---

## 🔐 Comment se protéger ?

- ✅ Utiliser des outils de détection d’ARP spoofing (ex. `arpwatch`, `XArp`)
- 🔒 Mettre en place des **tables ARP statiques** pour les adresses critiques
- 🧱 Utiliser des **switchs managés** avec protection ARP/DHCP (Dynamic ARP Inspection)
- 🔐 Utiliser le chiffrement (HTTPS, VPN) pour rendre les données inutilisables même interceptées

---

## 🧠 À retenir

| Terme         | Rôle                                                      |
|---------------|-----------------------------------------------------------|
| ARP Request   | Demande d'adresse MAC pour une IP donnée                  |
| ARP Spoofing  | Attaque qui envoie de fausses réponses pour tromper le réseau |
| Risque        | Interception, manipulation ou redirection de trafic réseau |
| Défense       | Surveillance, tables ARP statiques, chiffrement, outils de détection |

---


![Image](https://github.com/user-attachments/assets/ed899047-8ee8-4f73-bfa2-fbc9e8b587c1)
