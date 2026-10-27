# 🚀 Cyber Runner 3D (Show HN Edition)

> **Un jeu d'arcade 3D néon/synthwave réactif en 9:16, 100 % autonome, zéro dépendance complexe, conçu pour le web moderne.**

---

## 📌 Présentation du Projet

**Cyber Runner 3D** est un mini-jeu d'action-arcade vertical conçu pour tourner de façon ultra-fluide sur tous les appareils (smartphones, tablettes, PC). 

Le joueur contrôle un vaisseau spatial dans un couloir virtuel, esquive des obstacles lumineux générés de façon procédurale, et tente de battre son meilleur score dans une ambiance synthwave rétro-futuriste.

Ce projet a été développé dans l'esprit de l'open-source minimaliste : **un seul fichier HTML self-contained** réunissant les graphismes 3D, le moteur physique, la génération sonore et la sécurité.

---

## 🌟 Fonctionnalités Clés

- **Format Universel 9:16 Adaptatif** :
  - Sur mobile : expérience plein écran native.
  - Sur ordinateur : écran de jeu vertical style borne d'arcade avec conteneur néon et effet scanline/CRT.
- **Moteur Graphique 3D Fluidifié (Three.js)** :
  - Animation verrouillée à 60 FPS avec calcul basé sur la variation de temps réelle (*delta-time*).
  - Grille au sol bleu cyan fixe et illuminée (aucun clignotement ou passage au noir).
  - Éclairage dynamique sur la carrosserie du vaisseau avec lissage *Lerp* pour des déplacements d'une grande fluidité.
- **Synthesizer Audio embarqué (Web Audio API)** :
  - Aucun fichier `.mp3` ou `.wav` externe à charger.
  - Sons de réacteur, de collecte et d'explosion synthétisés dynamiquement en pure JS.
- **Interface Utilisateur 100 % en Français** :
  - HUD complet avec score en temps réel, record enregistré localement et instructions claires.
  - Modal dédié exposant les règles et la licence pour les développeurs.
- **Contrôles Multi-Plateformes** :
  - PC : Clavier (Flèches `←` / `→` ou touches `Q` / `D`).
  - Mobile / Tactile : Glissement (*Swipe*) ou boutons tactiles dédiés.

---

## 🛡️ Mesures de Sécurité & Anti-Triche Intégrées

Le code inclut plusieurs couches de protection pour garantir un environnement stable et équitable :

1. **Vérification d'intégrité du High Score (HMAC Checksum)** :
   - Le score sauvegardé dans le `localStorage` est signé avec une empreinte numérique. Toute tentative d'édition manuelle depuis la console réinitialise automatiquement le score falsifié.
2. **Politique de Sécurité du Contenu (Content Security Policy - CSP)** :
   - En-tête métadonnée bloquant l'exécution d'iframes malveillantes ou l'injection de scripts tiers.
3. **Assainissement des Données (Anti-XSS)** :
   - Traitement systématique des chaînes affichées via une fonction de *sanitisation* (`sanitizeHTML`).
4. **Protections des Constantes (Immutabilité)** :
   - L'objet `CONFIG` régissant la vitesse et les règles physiques est gelé via `Object.freeze()` pour parer la manipulation de variables à la volée.
5. **Limitation de Fréquence des Entrées (Rate Limiter)** :
   - Protection contre le bombardement de commandes par scripts d'automatisation ou bots.

---

## 🤝 Appel à la Communauté Hacker News (Fork & Version 2.0)

Ce projet est conçu comme un **socle de départ communautaire**. Il est volontairement épuré et lisible afin d'inciter la communauté à s'en emparer.

### Idées d'améliorations pour la v2.0 :
- 🎨 **Skins & Visuals** : Ajout de shaders personnalisés, de bonus d'invincibilité ou de multiplicateurs de score.
- 🎵 **Système Musique** : Intégration d'un synthétiseur Chiptune/Web Audio plus élaboré.
- 🌐 **Leaderboard Global** : Remplacement du `localStorage` par une base de données distante sécurisée (Firebase / Supabase).
- 🎮 **Physique & Gameplay** : Ajout de nouvelles formes d'obstacles, de tirs ou de phases de boss.

---

## 📜 Licence & Droits d'Auteur

Ce projet est distribué sous la licence **MIT Modifiée avec Clause d'Attribution Obligatoire**.

```text
================================================================================
MENTIONS D'AUTEUR & LICENCE
================================================================================

Copyright (c) 2026 Martin Nolane. Tous droits réservés.

L'autorisation est accordée, gracieusement, à toute personne obtenant une copie
de ce logiciel et des fichiers de documentation associés, de traiter le Software
sans restriction, y compris sans limitation les droits d'utiliser, de copier,
de modifier, de fusionner, de publier, de distribuer, de sous-licencier et/ou
de vendre des copies du Software, sous réserve des conditions suivantes :

1. CLAUSE D'ATTRIBUTION OBLIGATOIRE :
   Toute version ultérieure, modification, dérivation, amélioration ou "fork" 
   de ce projet (incluant les versions 2.0 et suivantes) doit OBLIGATOIREMENT 
   mentionner de manière claire et visible la paternité du créateur original :
   "Créateur original : Martin Nolane".

2. La notice de copyright ci-dessus et la présente notice d'autorisation doivent 
   être incluses dans toutes les copies ou parties substantielles du Software.

LE LOGICIEL EST FOURNI "EN L'ÉTAT", SANS GARANTIE D'AUCUNE SORTE, EXPRESSE OU
IMPLICITE, Y COMPRIS MAIS SANS S'Y LIMITER LES GARANTIES DE QUALITÉ MARCHANDE,
D'ADÉQUATION À UN USAGE PARTICULIER ET DE NON-CONTREFAÇON.
================================================================================
