
# The Grand Archive

Lecteur de musique open source à interface cristalline.

[![Licence: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Version](https://img.shields.io/badge/version-3.0.0-brightgreen)]()
[![Status](https://img.shields.io/badge/status-développement-yellow)]()

---

## À propos

The Grand Archive est un lecteur de musique développé dans des conditions atypiques : entièrement conçu sur iPhone XR via l'application Koder, avec le code généré par des IA (Gemini et DeepSeek). L'auteur ne possède pas de compétences en programmation et a agi en tant que "donneur d'ordre" et directeur artistique.

Le projet est désormais open source dans l'objectif d'être repris, amélioré et finalisé par la communauté.

---

## État du projet

### Fonctionnalités existantes (partiellement opérationnelles)

- **Interface** : 3 blocs de glace transparents, ghost UI, responsive
- **Thèmes** : 7 thèmes dont "Spectrum" (couleurs dynamiques)
- **Diaporama** : 10 catégories d'images d'ambiance + import utilisateur
- **Radio** : streaming (FIP, Nova, RFI, France 24, BBC)
- **APIs** : iTunes, Last.fm (intégrées mais instables)
- **Cache** : IndexedDB avec localforage
- **PWA** : Service worker, manifest, fonctionnement hors-ligne partiel
- **Mode immersion** : structure de base, import vidéo

### Problèmes identifiés

- **Son des boutons** : incohérent, non fonctionnel sur certains éléments
- **APIs externes** : appels instables, timeouts fréquents
- **Contrôles player** : certains boutons sans effet
- **Navigation** : ouverture de panneaux parfois défaillante
- **Dossier "bonhomme-neige"** : images non chargées
- **Thème Spectrum** : incohérences de couleurs sur certains composants
- **Mode immersion** : paroles non synchronisées, vidéos sans lecture rythmée
- **Performances** : ralentissements sur mobile ancien

---

## Objectifs techniques

### Phase 1 - Stabilisation
- [ ] Correction de tous les sons d'interface
- [ ] Stabilisation des appels API (iTunes, Last.fm, Genius)
- [ ] Rétablissement de tous les contrôles player
- [ ] Harmonisation des thèmes (notamment Spectrum)
- [ ] Correction du dossier "bonhomme-neige"

### Phase 2 - Lecteur audio professionnel
- [ ] Implémentation d'un moteur audio robuste (Howler.js avancé ou Web Audio API)
- [ ] Support des formats courants (MP3, FLAC, ALAC, AAC)
- [ ] Accès au système de fichiers pour importation musique
- [ ] Lecture complète des métadonnées (ID3, Vorbis comments)
- [ ] Gestion des playlists (création, édition, sauvegarde)
- [ ] Bibliothèque musicale avec tri, recherche, filtres
- [ ] Mode karaoké avec paroles synchronisées
- [ ] Visualiseur audio temps réel

### Phase 3 - Mode immersion avancé
- [ ] Synchronisation paroles/musique au niveau temporel
- [ ] Vidéos d'ambiance synchronisées
- [ ] Transitions fluides entre morceaux

### Phase 4 - Applications natives
- [ ] Version desktop (Electron/Tauri)
- [ ] Version iOS native (Swift)
- [ ] Version Android native (Kotlin)
- [ ] Conservation du design original sur toutes les plateformes

---

## Architecture

```

The Grand Archive/
├── index.html                 # Structure principale
├── main.js                    # Orchestrateur
├── style.css                  # Design system
├── sw.js                      # Service Worker
├── backgrounds/.              # Images d'ambiance
└── modules/                   # Modules sandboxés
├── about-handler.js
├── background-manager.js
├── content-loader.js
├── gallery-engine.js
├── immersion-engine.js
├── itunes-api.js
├── lastfm-api.js
├── local-library.js
├── lyrics-sync.js
├── metadata-bot.js
├── navigation.js
├── offline-manager.js
├── panel-buttons.js
├── player-controls.js
├── player-interface.js
├── radio-stream.js
├── sound-system.js
└── ui-core.js

```

L'architecture est basée sur des modules indépendants communiquant uniquement par événements (sandbox). Aucune dépendance directe entre modules.

---

## Technologies

- **Frontend** : HTML5, CSS3 (variables CSS), JavaScript pur
- **Stockage** : IndexedDB (via localforage)
- **APIs** : iTunes, Last.fm, Genius, Radio France
- **Animations** : CSS transitions, GSAP
- **PWA** : Service Worker, manifest.json

---

## Installation

```bash
git clone https://github.com/davidb/the-grand-archive.git
cd the-grand-archive
# Ouvrir index.html dans un navigateur
```

Ou utiliser la version PWA hébergée (si disponible).

---

Contribution

Les contributions sont les bienvenues, particulièrement sur les axes identifiés dans la roadmap.

Processus

1. Forker le projet
2. Créer une branche (git checkout -b feature/ma-feature)
3. Commiter les changements (git commit -m 'Ajout feature')
4. Pousser (git push origin feature/ma-feature)
5. Ouvrir une Pull Request

Règles

· Documenter les changements
· Tester sur différents navigateurs si possible
· Conserver l'architecture modulaire et le système d'événements

---

Licence

GNU General Public License v3.0

Ce projet est libre. Toute modification ou distribution doit conserver la même licence et partager les sources.

---

Contact

· GitHub : davidb
· Issues : github.com/davidb/the-grand-archive/issues

---

Remerciements

· Gemini et DeepSeek pour la génération du code
· Koder pour l'application ayant permis le développement sur mobile
· La communauté open source pour son futur travail

---

Développé sur iPhone XR, 2026
