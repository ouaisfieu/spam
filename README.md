# mySPOT

**Strategic Planning & Organization Tool**

Application web single-file pour la gestion d'univers complexes et la planification stratégique de plaidoyer.

---

## 🎯 À quoi ça sert ?

mySPOT est un outil d'intelligence tout-en-un qui permet de :

- **Cartographier des univers** — Personnages, organisations, lieux, événements, objets
- **Visualiser les connexions** — Graphe interactif avec simulation physique
- **Planifier des campagnes de plaidoyer** — 15 outils stratégiques intégrés
- **Analyser des réseaux d'influence** — Fiches de ciblage, cartographie des alliés/adversaires

### Cas d'usage

| Domaine | Utilisation |
|---------|-------------|
| 🎬 Fiction | Worldbuilding, bible de série, univers de jeu |
| 🏛️ Plaidoyer | Campagnes d'influence, lobbying, mobilisation |
| 🔍 Investigation | Cartographie de réseaux, analyse de parties prenantes |
| 📚 Recherche | Organisation de sources, mind mapping relationnel |
| 🎮 JDR | Gestion de campagne, PNJ, factions |

---

## 🚀 Démarrage rapide

1. **Ouvrir** `myspot.html` dans un navigateur moderne
2. **Créer** une première entité avec le bouton `＋ Nouvelle entité`
3. **Importer** des données existantes via l'onglet Import (drag & drop)

> 💾 Les données sont automatiquement sauvegardées dans IndexedDB (persistance locale)

---

## 📱 Interface

### Navigation principale

| Onglet | Fonction |
|--------|----------|
| 👥 Entités | Liste, filtres, détails, relations, notes |
| 🕸️ Graphe | Visualisation interactive du réseau |
| 📅 Timeline | Chronologie des événements datés |
| 🎯 Plaidoyer | 15 outils de planification stratégique |
| 📥 Import | Import JSON, CSV, XLSX, TXT |
| 🔧 Outils | Export, chiffrement, statistiques |

### Raccourcis clavier

| Raccourci | Action |
|-----------|--------|
| `Ctrl/Cmd + K` | Recherche globale |
| `Ctrl/Cmd + N` | Nouvelle entité |
| `Escape` | Fermer les modales |

---

## 📊 Types d'entités

| Type | Icône | Usage |
|------|-------|-------|
| person | 👤 | Individus, personnages |
| org | 🏢 | Organisations, entreprises, factions |
| place | 📍 | Lieux, territoires |
| event | 📅 | Événements, batailles, réunions |
| object | 🔮 | Objets, artefacts, documents importants |
| document | 📄 | Sources, références, preuves |

### Rôles (Plaidoyer)

| Rôle | Signification |
|------|---------------|
| ✅ ally | Allié, soutien actif |
| ❌ adversary | Adversaire, opposition |
| 🎯 target | Cible à convaincre |
| ❓ undecided | Position incertaine |

---

## 🕸️ Graphe interactif

### Contrôles

| Action | Résultat |
|--------|----------|
| **Clic + glisser sur nœud** | Déplacer le nœud |
| **Clic + glisser sur fond** | Pan (déplacer la vue) |
| **Molette** | Zoom in/out |
| **Double-clic sur nœud** | Ouvrir l'entité |
| **Survol** | Afficher tooltip |

### Boutons

- `⟳ Reset` — Réinitialiser zoom et position
- `＋ Zoom` / `－ Dézoom` — Ajuster le zoom
- `⚡ Physique` — Activer/désactiver la simulation
- `📷 Export PNG` — Télécharger l'image

### Légende visuelle

- **Couleur du nœud** = Type d'entité
- **Cercle externe** = Rôle (allié vert, adversaire rouge, etc.)
- **Lignes** = Relations entre entités

---

## 🎯 Module Plaidoyer

### 📐 Cadrage

| Outil | Description |
|-------|-------------|
| 🧭 Théorie du Changement | Vision, valeurs, hypothèses, missions |
| 📊 SWOT | Forces, faiblesses, opportunités, menaces |
| 🌍 PESTEL | Analyse macro (politique, économique, social, tech, environnement, légal) |

### 🔍 Analyse

| Outil | Description |
|-------|-------------|
| 🌳 Arbre à Problèmes | Causes → Problème central → Conséquences |
| ❓ 5 Pourquoi | Remonter à la cause racine |
| 🎯 Objectifs SMART | Générateur d'objectifs Spécifiques, Mesurables, Atteignables, Réalistes, Temporels |

### ⚔️ Stratégie

| Outil | Description |
|-------|-------------|
| ♟️ Choix de Stratégies | 12 stratégies types (recherche, mobilisation, juridique, médias...) |
| 👥 Fiches de Ciblage | Profils détaillés : intérêt, influence, position, accès, arguments |

### 📢 Communication

| Outil | Description |
|-------|-------------|
| 💬 Messages clés | Structure : Accroche → Problème → Importance → Cible → Action |

### 📈 Suivi

| Outil | Description |
|-------|-------------|
| 📉 Marqueurs de Progrès | Matrice Expect/Like/Love par acteur |
| ✅ Suivi des Actions | Liste d'actions avec statut (planifié/en cours/terminé) |

---

## 📥 Import de données

### Formats supportés

| Format | Structure attendue |
|--------|-------------------|
| **JSON** | `{ entities: [], relations: [], notes: [], plaidoyer: {} }` |
| **CSV/XLSX** | Colonnes : id, name, type, alias, desc, date, role, tags |
| **TXT** | Liste de noms (1 par ligne), créés comme `person` |

### Import JSON (structure complète)

```json
{
  "entities": [
    {
      "id": "unique_id",
      "name": "Nom",
      "type": "person|org|place|event|object|document",
      "alias": "Autres noms",
      "desc": "Description",
      "date": "Date ou période",
      "role": "ally|adversary|target|undecided",
      "tags": ["tag1", "tag2"]
    }
  ],
  "relations": [
    {
      "id": "rel_id",
      "from": "entity_id_source",
      "to": "entity_id_target",
      "type": "type de relation"
    }
  ],
  "notes": [
    {
      "id": "note_id",
      "entityId": "entity_id",
      "content": "Contenu de la note",
      "source": "Source optionnelle"
    }
  ]
}
```

---

## 📤 Export

| Format | Contenu |
|--------|---------|
| **JSON** | Données complètes (réimportables) |
| **CSV** | Tableau des entités |
| **Markdown** | Documentation lisible |
| **HTML Univers** | Site web navigable autonome |
| **PNG Graphe** | Image du graphe |
| **Markdown Plaidoyer** | Plan de plaidoyer complet |

---

## 🔐 Sécurité

### Chiffrement AES-256-GCM

L'onglet Outils inclut un module de chiffrement :
1. Coller le texte à chiffrer
2. Entrer une clé secrète
3. Cliquer sur 🔒 Chiffrer ou 🔓 Déchiffrer

> ⚠️ La clé n'est jamais stockée. Si vous la perdez, les données sont irrécupérables.

### Stockage local

- Données stockées en **IndexedDB** (navigateur)
- Aucune donnée envoyée sur internet
- Exporter régulièrement en JSON pour backup

---

## 🛠️ Technique

| Caractéristique | Détail |
|----------------|--------|
| **Type** | Single-file HTML (autonome) |
| **Taille** | ~120 KB |
| **Dépendances** | SheetJS (XLSX), Google Fonts |
| **Stockage** | IndexedDB |
| **Compatibilité** | Chrome, Firefox, Safari, Edge (modernes) |

### Stack

- HTML5 / CSS3 (variables CSS, Grid, Flexbox)
- JavaScript vanilla (ES6+)
- Canvas 2D pour le graphe
- Web Crypto API pour le chiffrement

---

## 📋 Changelog

### v1.0.0
- Interface complète 6 onglets
- Gestion entités/relations/notes
- Graphe interactif avec physique
- Timeline chronologique
- 15 outils de plaidoyer
- Import multi-format
- Export JSON/CSV/MD/HTML
- Chiffrement AES intégré
- Persistance IndexedDB

---

## 📄 Licence

Usage libre. Créé avec Claude (Anthropic).

---

## 💡 Tips

1. **Commencez petit** — Quelques entités clés, puis enrichissez progressivement
2. **Utilisez les tags** — Ils permettent de filtrer et retrouver rapidement
3. **Datez vos événements** — La timeline devient un outil puissant
4. **Exportez régulièrement** — JSON = backup complet réimportable
5. **Double-cliquez sur le graphe** — Navigation rapide vers les entités
