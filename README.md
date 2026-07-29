# Edge Quantum 65 — Site

Site vitrine du projet **Edge Quantum 65** : laboratoire R&D en
intelligence artificielle embarquée, souveraine et air-gappée.

**→ [https://edgequantum65.github.io/edge-quantum-65-site/](https://edgequantum65.github.io/edge-quantum-65-site/)**

---

## Sujet

Edge Quantum 65 conçoit des systèmes d'IA qui s'installent **dans la
machine**, pas dans le cloud. Pas de connexion réseau, pas de mise à
jour distante, pas de dépendance à un service tiers. Une intelligence
qui vous appartient physiquement.

Le terrain d'exploration actuel du laboratoire couvre :

- **Moteurs physiques** (asynchrones, brushless, pas-à-pas)
- **Batteries** (LiFePO4, Li-ion, plomb) et leur signature de décharge
- **Actionneurs** (ventilateurs, pompes, compresseurs, convoyeurs)
- **Capteurs** (vibration MPU-6050, température DS18B20, courant ACS712)

## Socle technique

| Brique | Rôle |
|---|---|
| [NNUE](https://github.com/edgequantum65/chess-engine) | Réseau de neurones spécialisé, mise à jour incrémentale des features |
| Rust (no_std) | Sécurité mémoire compile-time, pas de runtime, cible Cortex-M et Xtensa |
| STM32 / ESP32 | Microcontrôleurs souverains (STMicroelectronics Crolles, FR) |
| Boucle Champion/Challenger | Auto-optimisation locale sans label pré-établi |
| Fonction de coût L | L = α·Énergie − β·Rendement + γ·Pénalité, gravée en flash |

## Approche algorithmique

Le système n'utilise pas d'IA générative. Il n'a pas besoin de dataset
pré-étiqueté. La machine apprend en observant sa propre signature
physique, guidée par une fonction de coût L non modifiable après
compilation.

Voir le pseudocode sur le site : [Boucle CvC](https://edgequantum65.github.io/edge-quantum-65-site/#philosophie).

## Banc de test : DSGM Chess

Le moteur d'échecs n'est pas le produit, c'est le **laboratoire
d'entraînement du NNUE**. Toute brique validée aux échecs (HalfKP,
SCReLU, quantification int16, mise à jour incrémentale) est ensuite
transposée sur les machines physiques.

Statut actuel (juillet 2026) :
- Moteur UCI en C et en Rust
- NNUE HalfKP 40960→256→32→1
- Table de transposition 1M entrées
- Killer moves, history heuristic, MVV-LVA, quiescence search
- Ouverture Polyglot 1.7M positions
- 9/9 tests unitaires passent sur le port Rust

## Sécurité & souveraineté

Cinq couches de protection indépendantes (détaillées sur le site) :

1. **Potting physique** (résine époxy MG Chemicals 832B)
2. **Tamper detection** (switch mécanique + mesh PCB)
3. **Secure Boot + Flash Encryption** (AES-256, RDP niveau 2)
4. **Signature par Device ID** (chaque firmware lié à l'UID de la puce)
5. **Pas de code source livré** (uniquement binaires chiffrés et signés)

## Ressources

| Repo | Contenu |
|---|---|
| [edge-quantum-65-site](https://github.com/edgequantum65/edge-quantum-65-site) | Ce site (HTML/CSS pur) |
| [chess-engine](https://github.com/edgequantum65/chess-engine) | Moteur UCI Rust + C avec NNUE |
| [nnue-embedded](https://github.com/edgequantum65/nnue-embedded) | Crate `no_std` : forward pass NNUE seul |
| [champion-vs-challenger](https://github.com/edgequantum65/champion-vs-challenger) | Boucle CvC, mode chess et mode embedded |
| [boitier-3d](https://github.com/edgequantum65/boitier-3d) | Source OpenSCAD du boîtier 80×50×30mm |

Aucun de ces dépôts ne contient d'éléments critiques (poids finaux,
clés de signature, secrets industriels).

## Localisation

Lannemezan, Hautes-Pyrénées, Occitanie (FR).
Création de SASU en cours.

## Contact

David Serreau — [edgequantum65@gmail.com](mailto:edgequantum65@gmail.com)

---

*Edge Quantum 65 — 2026*
