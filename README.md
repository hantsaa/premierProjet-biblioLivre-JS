# 🏛 Projet JavaScript HAI305I – Bibliothèque interactive

## 📌 Présentation
**Cours :** HAI305I – 2025-2026  
**Professeur :** Pierre Pompidor  
**Coefficient :** 15%  
**Type :** Projet obligatoire en binôme  
**Thème :** Les joueurs doivent ranger des livres qui arrivent progressivement (ex: sur un tapis roulant) sur des étagères. Chaque fois que le dernier livre posé et ses voisins créent un classement, des points sont attribués.

---

## 🎯 Objectifs pédagogiques
- Manipulation du DOM et interface interactive
- Gestion des événements en temps réel (connexion, messagerie)
- Organisation du code et architecture client-serveur
- Gestion du jeu au tour par tour pour plusieurs joueurs

---

## ⚙️ Fonctionnalités principales
- Connexion / déconnexion des joueurs
- Messagerie temps réel
- Jeu multijoueur (au moins 2 joueurs) sur ordinateurs différents
- Gestion du tour par tour
- Placement de livres et attribution des points
- Suivi des scores et fin de partie

---

## 🧩 Répartition des rôles et tâches

### 👨‍💻 Binôme A – Back-End / Logique de jeu
**Objectif :** Gérer la partie côté serveur, tours, communication et scores

**Tâches :**
- [ ] Initialiser le serveur Node.js et charger `livres.json`
- [ ] Gérer les connexions / déconnexions des joueurs
- [ ] Maintenir la liste des joueurs (pseudo, score, tour)
- [ ] Gérer le tour par tour et notifier le joueur actif
- [ ] Envoyer un livre à placer au joueur actif
- [ ] Vérifier les classements et calculer les points
- [ ] Envoyer les mises à jour de scores à tous les joueurs
- [ ] Gérer les événements réseau : chat, livre posé, tour, fin de partie
- [ ] Déterminer la fin de partie et envoyer le classement final

---

### 👨‍🎨 Binôme B – Front-End / Interface / Expérience utilisateur
**Objectif :** Créer une interface claire et interactive pour le joueur

**Tâches :**
- [ ] Créer la page HTML avec :
  - Zone tapis roulant
  - Zone étagères
  - Zone chat / messages
  - Tableau des scores
- [ ] Styliser l’interface (CSS)
- [ ] Afficher le livre à placer
- [ ] Permettre au joueur de déposer le livre (drag & drop ou clic)
- [ ] Indiquer le tour courant (à toi de jouer / attendre)
- [ ] Afficher la liste des messages et envoyer de nouveaux messages
- [ ] Mettre à jour les scores en temps réel
- [ ] Ajouter animations ou retours visuels (bonus expérience utilisateur)

---

## 🔄 Flux de communication serveur-client (simplifié)
| Événement       | Émetteur | Description |
|-----------------|----------|-------------|
| `playerJoined`  | client → serveur | Un joueur se connecte |
| `playerList`    | serveur → clients | Liste des joueurs connectés |
| `nextBook`      | serveur → joueur actif | Livre à placer |
| `bookPlaced`    | joueur actif → serveur | Livre posé sur étagère |
| `scoreUpdate`   | serveur → tous | Mise à jour des scores |
| `chatMessage`   | tous | Messages du chat |
| `turnChange`    | serveur → tous | Joueur courant |
| `gameOver`      | serveur → tous | Fin de partie et classement |

---

## 🪜 Plan de progression conseillé
| Étape | Objectif | Responsable |
|-------|----------|------------|
| 1     | Serveur minimal + connexion Socket.io | A |
| 2     | Interface HTML/CSS basique + connexion serveur | B |
| 3     | Gestion liste des joueurs | A & B |
| 4     | Messagerie temps réel | A & B |
| 5     | Tour par tour | A |
| 6     | Interface tapis + étagères + pose de livres | B |
| 7     | Calcul points et scores | A |
| 8     | Synchronisation graphique + scores | B |
| 9     | Tests multi-PC | A & B |
| 10    | Finitions visuelles et stabilité | B |

---

## 📌 Notes supplémentaires
- Respecter le **format JSON fourni pour les livres**
- Toutes les actions critiques passent par le **serveur** pour éviter les incohérences
- Ajouter un **feedback visuel** pour chaque action (pose, points, tour)
- Tester régulièrement entre deux machines pour vérifier le multijoueur
