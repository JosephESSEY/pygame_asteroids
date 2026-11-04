# 🚀 Asteroids (Pygame)

Une réimplémentation en Python du célèbre jeu d'arcade rétro **Asteroids**, développée avec [Pygame](https://www.pygame.org/) et gérée via le gestionnaire de paquets [uv](https://docs.astral.sh/uv/).

---

## 🎮 Fonctionnalités

- **Contrôles du vaisseau** :
  - Rotation fluide à gauche et à droite.
  - Déplacement avant et arrière dans la direction orientée.
- **Système de tir (Blaster)** :
  - Projectiles tirés dans la direction du vaisseau avec cadence limitée (cooldown de 0.3s).
- **Génération & Division des astéroïdes** :
  - Génération continue d'astéroïdes de différentes tailles sur les bords de l'écran via un gestionnaire dédié (`AsteroidField`).
  - Découpage réaliste : les grands astéroïdes se divisent en deux astéroïdes moyens, qui se divisent à leur tour en deux petits astéroïdes avec une vitesse accrue et des trajectoires déviées.
- **Détection des collisions** :
  - Collisions circulaires optimisées entre vaisseaux, astéroïdes et tirs.
  - Fin de partie instantanée (*Game Over*) si le vaisseau heurte un astéroïde.
- **Architecture Orientée Objet** :
  - Classe de base `CircleShape` héritant des `Sprite` de Pygame.
  - Gestion automatique du cycle de vie des objets via des groupes Pygame (`updatable`, `drawable`, `asteroids`, `shots`).

---

## 🕹️ Commandes de jeu

| Touche | Action |
| :--- | :--- |
| **`W`** | Avancer |
| **`S`** | Reculer |
| **`A`** | Tourner à gauche (sens anti-horaire) |
| **`D`** | Tourner à droite (sens horaire) |
| **`Espace`** | Tirer |

---

## ⚙️ Prérequis & Installation

### Prérequis
- [Python 3.13+](https://www.python.org/)
- [uv](https://docs.astral.sh/uv/) (recommandé pour une installation rapide des dépendances)

### Installation
Clonez le dépôt et installez les dépendances :

```bash
git clone https://github.com/JosephESSEY/pygame_asteroids.git
cd pygame_asteroids
uv sync
```

---

## 🚀 Lancer le jeu

Pour démarrer la partie :

```bash
uv run main.py
```

*(Ou avec un environnement virtuel Python classique : `python main.py`)*

---

## 📂 Structure du projet

```
asteroids/
├── constants.py      # Constantes de jeu (dimensions d'écran, vitesses, rayons)
├── circleshape.py    # Classe de base pour tous les sprites circulaires
├── player.py         # Classe du vaisseau du joueur (rendu triangulaire, contrôles, tir)
├── asteroid.py       # Classe des astéroïdes (mouvement, division)
├── asteroidfield.py  # Système de réapparition/génération des astéroïdes
├── shot.py           # Classe des projectiles
├── logger.py         # Enregistreur d'état et d'événements de jeu
├── main.py           # Boucle de jeu principale
├── pyproject.toml    # Dépendances et configuration du projet
└── README.md
```
