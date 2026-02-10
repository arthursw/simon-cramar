# Guide de Création et d'Édition de Contenu

Guide complet pour créer et gérer le contenu de votre site web Hugo.

---

## Table des Matières

1. [Configurer Votre Éditeur](#configurer-votre-éditeur)
2. [Comprendre la Structure du Contenu](#comprendre-la-structure-du-contenu)
3. [Écrire en Markdown](#écrire-en-markdown)
4. [Ajouter des Images](#ajouter-des-images)
5. [Ajouter des Vidéos](#ajouter-des-vidéos)
6. [Créer de Nouvelles Pages](#créer-de-nouvelles-pages)
7. [Gérer les Menus](#gérer-les-menus)
8. [Publier Vos Modifications](#publier-vos-modifications)
9. [Référence Rapide](#référence-rapide)

---

## Configurer Votre Éditeur

### 1. Ouvrir Votre Projet

1. **Lancez VSCodium**
2. **Ouvrez le dossier de votre site** : Fichier > Ouvrir le dossier
3. Naviguez vers le répertoire de votre site Hugo et cliquez sur "Ouvrir"

### 2. Démarrer le Serveur de Prévisualisation en Direct

1. **Ouvrez un nouveau terminal** : menu Terminal > Nouveau Terminal
2. **Exécutez le serveur Hugo** :
   ```bash
   hugo serve
   ```
3. Vous verrez une sortie comme :
   ```
   Web Server is available at http://localhost:1313/
   ```
4. **Ouvrez cette URL** dans votre navigateur web

### 3. Organiser Votre Espace de Travail

- Gardez **VSCodium** d'un côté de votre écran
- Gardez votre **navigateur** de l'autre côté
- Les modifications que vous apportez apparaîtront automatiquement dans le navigateur !

:::tip
Appuyez sur `Cmd+S` (Mac) ou `Ctrl+S` (Windows/Linux) pour enregistrer les fichiers. Le navigateur se rafraîchira automatiquement.
:::

---

## Comprendre la Structure du Contenu

### Qu'est-ce que le Contenu Hugo ?

Tout le contenu de votre site web se trouve dans le dossier `content/`. Chaque page est un **fichier Markdown** (`.md`) composé de deux parties principales :

```markdown
---
title: Titre de la Page
description: Description de la page
---

# Le contenu commence ici

Votre texte, images et mise en forme vont sous le frontmatter.
```

### Anatomie d'un Fichier de Contenu

#### 1. **Frontmatter** (Métadonnées)

La section entre les marques `---` en haut du fichier. Cela indique à Hugo des informations sur votre page.

**Exemple basique :**
```yaml
---
title: À Propos
description: En savoir plus sur mon travail
---
```

**Exemple avancé de ce site** (`content/a-propos.md`) :
```yaml
---
title: À propos
description: À propos de Simon Cramar
layout: prose
menus:
  main:
    name: À propos
    weight: 4
---
```

**Champs frontmatter courants :**
- `title` : Titre de la page (requis)
- `description` : Brève description pour le référencement
- `date` : Date de publication (format AAAA-MM-JJ)
- `layout` : Modèle de mise en page à utiliser
- `menus` : Configuration du menu (voir [Gérer les Menus](#gérer-les-menus))
- `weight` : Ordre dans les listes (les nombres plus petits apparaissent en premier)

#### 2. **Contenu** (Corps de Votre Page)

Tout ce qui se trouve sous le deuxième `---` est le contenu de votre page, écrit en **Markdown**.

**Exemple de ce site** (`content/a-propos.md`) :
```markdown
---
title: À propos
description: À propos de Simon Cramar
layout: prose
---

# Simon Cramar

**"Chasseur d'images, capturant l'espace-temps..."**

A 10 ans, j'ai reçu le plus grand cadeau qu'il soit : mon premier appareil photo !

Il m'a appris à découvrir le monde. Il m'a ouvert les yeux, jusqu'à voler dans les cieux!
```

---

## Écrire en Markdown

Markdown est un langage de formatage simple. Vous écrivez du texte brut avec des caractères spéciaux pour ajouter du style.

### En-têtes

Utilisez les symboles `#` pour les en-têtes. Plus de `#` = en-tête plus petit.

```markdown
# Titre Principal (H1)
## Titre de Section (H2)
### Sous-section (H3)
#### Petit En-tête (H4)
```

**S'affiche comme :**

# Titre Principal (H1)
## Titre de Section (H2)
### Sous-section (H3)
#### Petit En-tête (H4)

---

### Formatage du Texte

```markdown
**Texte en gras** ou __texte en gras__
*Texte en italique* ou _texte en italique_
***Gras et italique ensemble***
~~Texte barré~~
```

**S'affiche comme :**

**Texte en gras**
*Texte en italique*
***Gras et italique ensemble***
~~Texte barré~~

**Exemple de ce site** (`content/materiel.md`) :
```markdown
**Bien que "l'outil ne fasse pas l'image"...**
```

---

### Listes

#### Points de Liste (Listes Non Ordonnées)

```markdown
- Premier élément
- Deuxième élément
- Troisième élément
  - Élément imbriqué
  - Autre élément imbriqué
    - Imbrication encore plus profonde
- Retour au niveau principal
```

**S'affiche comme :**

- Premier élément
- Deuxième élément
- Troisième élément
  - Élément imbriqué
  - Autre élément imbriqué
    - Imbrication encore plus profonde
- Retour au niveau principal

#### Listes Numérotées (Listes Ordonnées)

```markdown
1. Première étape
2. Deuxième étape
3. Troisième étape
   1. Sous-étape A
   2. Sous-étape B
4. Quatrième étape
```

**S'affiche comme :**

1. Première étape
2. Deuxième étape
3. Troisième étape
   1. Sous-étape A
   2. Sous-étape B
4. Quatrième étape

**Exemple de ce site** (`content/materiel.md`) :
```markdown
## Optiques

- **Panasonic 12-35mm f/2.8**
- **Panasonic 35-100mm f/2.8**
- **Panasonic 7-14mm f/4**
```

---

### Liens

```markdown
[Texte du lien](https://exemple.com)
[Lien avec titre](https://exemple.com "Texte au survol")
```

**Liens internes** (vers d'autres pages de votre site) :
```markdown
[Page À propos](/about/)
[Contact](/contact/)
```

---

### Citations

```markdown
> Ceci est une citation.
> Elle peut s'étendre sur plusieurs lignes.
>
> Et sur plusieurs paragraphes.
```

**S'affiche comme :**

> Ceci est une citation.
> Elle peut s'étendre sur plusieurs lignes.
>
> Et sur plusieurs paragraphes.

---

### Code

#### Code en Ligne

Utilisez des apostrophes inversées pour le code en ligne :
```markdown
Utilisez la commande `hugo serve` pour démarrer le serveur.
```

**S'affiche comme :**

Utilisez la commande `hugo serve` pour démarrer le serveur.

#### Blocs de Code

Utilisez trois apostrophes inversées avec un langage optionnel :

````markdown
```python
def bonjour_monde():
    print("Bonjour, Monde !")
```
````

**S'affiche comme :**

```python
def bonjour_monde():
    print("Bonjour, Monde !")
```

---

### Lignes Horizontales

```markdown
---
```

**S'affiche comme :**

---

### Tableaux

```markdown
| En-tête 1 | En-tête 2 | En-tête 3 |
|-----------|-----------|-----------|
| Cellule 1 | Cellule 2 | Cellule 3 |
| Cellule 4 | Cellule 5 | Cellule 6 |
```

**S'affiche comme :**

| En-tête 1 | En-tête 2 | En-tête 3 |
|-----------|-----------|-----------|
| Cellule 1 | Cellule 2 | Cellule 3 |
| Cellule 4 | Cellule 5 | Cellule 6 |

**En savoir plus :** [Aide-mémoire Markdown Complet](https://www.markdownguide.org/cheat-sheet/)

---

## Ajouter des Images

Il existe **deux méthodes** pour ajouter des images à votre site Hugo.

### Méthode 1 : Images dans le Dossier `static/images/`

**Idéal pour :** Images partagées utilisées sur plusieurs pages, ressources à l'échelle du site.

#### Étape 1 : Ajouter Vos Fichiers Image

**Option A : Utiliser VSCodium**
1. Dans VSCodium, faites un clic droit sur le dossier `static/images/`
2. Sélectionnez **"Nouveau dossier"** pour créer une catégorie (ex : `portfolio`, `blog`, `produits`)
3. Faites un clic droit sur le nouveau dossier
4. Sélectionnez **"Afficher dans le Finder"** (Mac) ou **"Afficher dans l'explorateur de fichiers"** (Windows)
5. Copiez vos fichiers d'images dans ce dossier

**Option B : Utiliser GitHub (pour les sites existants)**
1. Allez sur votre dépôt sur GitHub.com
2. Naviguez vers `static/images/`
3. Cliquez sur **"Ajouter un fichier"** → **"Télécharger des fichiers"**
4. Glissez-déposez vos images
5. Validez les modifications

#### Étape 2 : Référencer les Images dans Votre Contenu

Utilisez cette syntaxe :
```markdown
![Texte alternatif descriptif](/images/nom-dossier/nom-image.jpg)
```

**Notes importantes :**
- Le chemin commence par `/images/` (le dossier static est omis)
- Fournissez toujours un texte alternatif pour l'accessibilité
- Formats supportés : `.jpg`, `.png`, `.gif`, `.svg`, `.webp`

#### Exemple Réel de ce Site

**Structure des fichiers :**
```
static/
  images/
    materiel/
      camera-1.jpg
      camera-2.jpg
```

**Dans `content/materiel.md` :**
```markdown
# Matériel

**Bien que "l'outil ne fasse pas l'image"...**

Voici le matériel que j'utilise sur mes projets.

![Équipement photo et vidéo](/images/materiel/camera-1.jpg)

## Caméras

### Panasonic GH5
- **Résolution capteur :** 20,3 Mpx
- **Vidéo :** Ultra HD 4K en 60ips

![Supports et accessoires](/images/materiel/camera-2.jpg)

## Supports

### Trépied Benro S6
Trépied en carbone avec tête vidéo fluide.
```

---

### Méthode 2 : Page Bundle avec Ressources

**Idéal pour :** Images spécifiques à une page qui appartiennent à une seule page (comme des couvertures d'articles, des galeries).

#### Étape 1 : Convertir Votre Page en Bundle

Au lieu d'un seul fichier comme `ma-page.md`, créez :
```
content/
  ma-page/
    index.md          ← Contenu de votre page
    cover.jpg         ← Images dans le même dossier
    photo1.jpg
    photo2.jpg
```

#### Étape 2 : Déclarer les Ressources dans le Frontmatter

```markdown
---
title: Ma Page
description: Une page avec des images groupées
resources:
  - src: cover.jpg
    params:
      cover: true
  - src: photo1.jpg
    title: Première Photo
  - src: photo2.jpg
    title: Deuxième Photo
---

Contenu de la page ici...
```

#### Étape 3 : Référencer les Images

Puisque les images sont dans le même dossier, vous pouvez les référencer directement :
```markdown
![Description](photo1.jpg)
```

Ou utiliser le chemin de la ressource :
```markdown
![Description](./photo1.jpg)
```

#### Exemple Réel de ce Site

**Structure des fichiers :**
```
content/
  videos/
    clip/
      index.md
      cover.jpg       ← Image de couverture pour cette catégorie
```

**Dans `content/videos/clip/index.md` :**
```markdown
---
title: CLIP
date: 2024-01-03
description: Clips musicaux
sort_by: Date
sort_order: desc
resources:
  - src: cover.jpg
    params:
      cover: true
videos:
  - url: https://www.youtube.com/watch?v=kau_K_asQKQ
    title: Jusqu'à (CLIP à Louvain-la-Neuve)
    date: 2017-01-01
---

Clips musicaux mêlant créativité visuelle et ambiance musicale.
```

Le `cover.jpg` est utilisé par le thème comme image mise en avant pour cette catégorie vidéo.

---

### Bonnes Pratiques pour les Images

#### Optimisation
- **Compressez les images** avant de les télécharger (utilisez des outils comme [TinyPNG](https://tinypng.com/))
- **Utilisez des tailles appropriées** : Ne téléchargez pas d'images de 4000px si elles s'affichent à 800px
- **Choisissez le bon format** :
  - `.jpg` pour les photos
  - `.png` pour les graphiques avec transparence
  - `.webp` pour les navigateurs modernes (taille de fichier plus petite)

#### Conventions de Nommage
- Utilisez des lettres minuscules
- Utilisez des traits d'union au lieu d'espaces : `mon-image.jpg` et non `Mon Image.jpg`
- Soyez descriptif : `produit-camera-face.jpg` et non `img001.jpg`

#### Texte Alternatif
Fournissez toujours un texte alternatif significatif :
```markdown
✓ Bon :  ![Caméra Panasonic GH5 sur trépied](/images/camera.jpg)
✗ Mauvais : ![camera](/images/camera.jpg)
✗ Mauvais : ![](/images/camera.jpg)
```

---

## Ajouter des Vidéos

### Intégration YouTube

La façon la plus courante d'ajouter des vidéos est via l'intégration YouTube dans votre frontmatter.

#### Méthode : Liste de Vidéos dans le Frontmatter

**Exemple réel de ce site** (`content/videos/clip/index.md`) :

```markdown
---
title: CLIP
date: 2024-01-03
description: Clips musicaux
videos:
  - url: https://www.youtube.com/watch?v=kau_K_asQKQ
    title: Jusqu'à (CLIP à Louvain-la-Neuve)
    date: 2017-01-01
  - url: https://www.youtube.com/watch?v=buOTKcu__lY
    title: Edel Sheep - Flesh to Dust
    date: 2016-01-01
---

Clips musicaux mêlant créativité visuelle et ambiance musicale.
```

Cela crée une page avec des lecteurs YouTube intégrés pour chaque vidéo.

#### Comment Obtenir les URL YouTube

1. Allez sur la vidéo sur YouTube
2. Cliquez sur le bouton **Partager**
3. Copiez l'URL (ex : `https://www.youtube.com/watch?v=kau_K_asQKQ`)
4. Ajoutez-la à votre frontmatter

#### Gestion des Vidéos Spécifique au Thème

:::warning
La syntaxe d'intégration vidéo dépend de votre thème Hugo. Consultez la documentation de votre thème pour :
- Les shortcodes pour intégrer des vidéos
- Les champs frontmatter personnalisés
- Les mises en page de galerie vidéo
:::

### Vidéo HTML5 (Auto-hébergée)

Si vous hébergez vous-même des fichiers vidéo :

1. **Ajoutez la vidéo dans `static/videos/`** :
   ```
   static/
     videos/
       ma-video.mp4
   ```

2. **Intégrez dans le markdown** (si votre thème supporte le HTML) :
   ```html
   <video controls>
     <source src="/videos/ma-video.mp4" type="video/mp4">
     Votre navigateur ne supporte pas la lecture vidéo.
   </video>
   ```

:::note
Les vidéos auto-hébergées augmentent le temps de chargement de la page et l'utilisation de la bande passante. L'hébergement sur YouTube/Vimeo est généralement meilleur pour les performances.
:::

---

## Créer de Nouvelles Pages

### Page Simple

1. **Dans VSCodium**, faites un clic droit sur le dossier `content/`
2. Sélectionnez **"Nouveau fichier"**
3. Nommez-le `ma-nouvelle-page.md`
4. Ajoutez le frontmatter et le contenu :

```markdown
---
title: "Ma Nouvelle Page"
description: "Une brève description pour le référencement"
---

# Bienvenue sur Ma Page

Ceci est le contenu de ma nouvelle page.

## Section 1

Du texte ici...

## Section 2

Plus de contenu...
```

5. **Enregistrez** (Cmd+S / Ctrl+S)
6. **Vérifiez votre navigateur** - la page devrait apparaître à `http://localhost:1313/ma-nouvelle-page/`

---

### Page avec Images (Bundle)

1. **Créez un dossier** dans `content/` : clic droit → "Nouveau dossier" → nommez-le `ma-galerie`
2. **Créez `index.md`** à l'intérieur de `ma-galerie/`
3. **Copiez les fichiers d'images** dans le dossier `ma-galerie/`
4. **Ajoutez le contenu** :

```markdown
---
title: "Ma Galerie Photo"
description: "Une collection de mes meilleures photos"
---

# Ma Galerie Photo

Découvrez ces photos incroyables !

![Première photo](photo1.jpg)
![Deuxième photo](photo2.jpg)
![Troisième photo](photo3.jpg)
```

5. **Enregistrez** et vérifiez le navigateur : `http://localhost:1313/ma-galerie/`

---

### Exemple Réel : Créer une Page "Services"

Créons une page de services complète inspirée de la structure de ce site :

**Fichier :** `content/services.md`

```markdown
---
title: Services
description: Services professionnels de photographie et vidéographie
layout: prose
menus:
  main:
    name: Services
    weight: 3
---

# Mes Services

**"Capturer vos moments, raconter votre histoire."**

## Photographie

### Photographie de Portrait
Portraits professionnels pour :
- **Photos de profil** - Image de marque professionnelle et personnelle
- **Portraits de famille** - Capturer les souvenirs de famille
- **Événements** - Mariages, célébrations, événements d'entreprise

![Exemples de photographie de portrait](/images/services/portraits.jpg)

### Photographie Commerciale
- Photographie de produits
- Immobilier
- Événements d'entreprise
- Alimentation et boissons

## Production Vidéo

### Clips Musicaux
Direction créative et production pour :
- Artistes indépendants
- Groupes
- Artistes solo

### Vidéos d'Entreprise
- Vidéos promotionnelles
- Présentations d'entreprise
- Matériel de formation
- Couverture d'événements

![Configuration de production vidéo](/images/services/video-setup.jpg)

## Photographie et Vidéo Aériennes

Pilote de drone certifié offrant :
- Prises de vue aériennes immobilières
- Couverture d'événements vue du ciel
- Photographie de paysages
- Documentation de l'avancement des constructions

## Équipement

J'utilise du matériel de qualité professionnelle incluant :
- **Caméras :** Panasonic GH5, GH3
- **Objectifs :** 12-35mm f/2.8, 35-100mm f/2.8, 7-14mm f/4
- **Drones :** DJI Mavic Pro
- **Stabilisation :** Stabilisateur Zhiyun Crane

## Contact

Intéressé pour travailler ensemble ? [Contactez-moi !](/contact/)
```

Cette page inclut :
- ✓ Contenu structuré avec des en-têtes
- ✓ Texte en gras pour l'emphase
- ✓ Listes à puces
- ✓ Images
- ✓ Liens internes
- ✓ Intégration au menu

---

## Gérer les Menus

### Ajouter une Page au Menu Principal

Ajoutez ceci au frontmatter de votre page :

```markdown
---
title: Ma Page
menus:
  main:
    name: Ma Page
    weight: 10
---
```

**Champs :**
- `main` : L'identifiant du menu (généralement "main" pour le menu d'en-tête)
- `name` : Texte affiché dans le menu
- `weight` : Ordre (les nombres plus petits apparaissent en premier)

**Exemple de poids de menu :**
```
Accueil   - weight: 1
À propos  - weight: 2
Services  - weight: 3
Portfolio - weight: 4
Contact   - weight: 5
```

### Exemple Réel de ce Site

**Dans `content/a-propos.md` :**
```markdown
---
title: À propos
description: À propos de Simon Cramar
layout: prose
menus:
  main:
    name: À propos
    weight: 4
---
```

Cela ajoute "À propos" au menu principal comme 4ème élément.

### Plusieurs Menus

Si votre thème supporte les menus de pied de page ou d'autres emplacements :

```markdown
---
title: Politique de Confidentialité
menus:
  main:
    name: Confidentialité
    weight: 10
  footer:
    name: Politique de Confidentialité
    weight: 2
---
```

---

## Publier Vos Modifications

Une fois que vous êtes satisfait de vos modifications, poussez-les vers GitHub pour que Cloudflare puisse reconstruire votre site.

### Étape 1 : Examiner les Modifications

1. **Cliquez sur l'icône Contrôle de source** dans la barre latérale gauche de VSCodium (3ème icône, ressemble à une branche)
2. Vous verrez tous les fichiers modifiés listés
3. Cliquez sur les fichiers pour voir ce qui a changé (vert = ajouté, rouge = supprimé)

### Étape 2 : Préparer les Modifications

- Tous les fichiers modifiés devraient être automatiquement préparés
- Sinon, cliquez sur l'icône **+** à côté de chaque fichier

### Étape 3 : Valider (Commit)

1. **Écrivez un message de commit** dans la zone de texte en haut
   - Soyez descriptif : "Ajout de la page services et mise à jour de la section à propos"
   - Pas : "mises à jour" ou "modifications"
2. **Cliquez sur le bouton ✓ Valider**

### Étape 4 : Pousser vers GitHub

1. **Cliquez sur le bouton "Synchroniser les modifications"** ou **"Push"**
2. Si demandé, authentifiez-vous avec GitHub
3. Attendez que le push se termine

### Étape 5 : Attendre le Déploiement

1. Cloudflare détecte automatiquement les modifications
2. Construit votre site (généralement 1-2 minutes)
3. Déploie vers votre URL en direct
4. Vérifiez votre site en ligne : `votre-nom-de-site.pages.dev`

:::tip
Vous pouvez surveiller la progression de la construction :
1. Allez sur [dash.cloudflare.com](https://dash.cloudflare.com)
2. Cliquez sur votre projet Pages
3. Cliquez sur "Voir la construction" pour voir les journaux en temps réel
:::

---

## Référence Rapide

### Syntaxe Markdown

| Élément | Syntaxe |
|---------|---------|
| Gras | `**texte**` ou `__texte__` |
| Italique | `*texte*` ou `_texte_` |
| Gras + Italique | `***texte***` |
| En-tête 1 | `# Texte` |
| En-tête 2 | `## Texte` |
| En-tête 3 | `### Texte` |
| Liste à puces | `- élément` |
| Liste numérotée | `1. élément` |
| Lien | `[texte](url)` |
| Image | `![alt](/chemin/vers/image.jpg)` |
| Citation | `> texte` |
| Code en ligne | `` `code` `` |
| Bloc de code | ` ```langage` <br> `code` <br> ` ``` ` |
| Ligne horizontale | `---` |

### Tâches Courantes

| Tâche | Comment Faire |
|-------|---------------|
| Créer une nouvelle page | Clic droit sur `content/` → Nouveau fichier → `nom-page.md` |
| Ajouter au menu | Ajouter une section `menus:` dans le frontmatter |
| Ajouter une image (static) | Mettre dans `static/images/`, référencer comme `![alt](/images/fichier.jpg)` |
| Ajouter une image (bundle) | Mettre dans le même dossier que `index.md`, référencer comme `![alt](fichier.jpg)` |
| Prévisualiser le site | Exécuter `hugo serve` dans le terminal |
| Arrêter la prévisualisation | Appuyer sur `Ctrl+C` dans le terminal |
| Publier les modifications | Contrôle de source → Valider → Push |

### Chemins de Fichiers

| Type | Exemple |
|------|---------|
| Image static | `/images/dossier/image.jpg` |
| Image bundle | `image.jpg` ou `./image.jpg` |
| Lien interne | `/about/` ou `/blog/mon-article/` |
| Lien externe | `https://exemple.com` |

### Champs Frontmatter

| Champ | Objectif | Exemple |
|-------|----------|---------|
| `title` | Titre de la page | `title: À Propos` |
| `description` | Description SEO | `description: En savoir plus sur mon travail` |
| `date` | Date de publication | `date: 2024-01-15` |
| `layout` | Modèle à utiliser | `layout: prose` |
| `menus` | Placement dans le menu | Voir [Gérer les Menus](#gérer-les-menus) |
| `weight` | Ordre de tri | `weight: 5` |
| `resources` | Ressources du page bundle | Voir [Méthode 2](#méthode-2-page-bundle-avec-ressources) |

---

## Dépannage

### Problèmes de Serveur de Prévisualisation

**Problème :** Commande `hugo serve` introuvable
**Solution :** Assurez-vous que Hugo est installé. Exécutez la commande d'installation du guide de démarrage rapide.

**Problème :** Port déjà utilisé
**Solution :** Exécutez `hugo serve -p 1314` pour utiliser un port différent.

**Problème :** Les modifications n'apparaissent pas
**Solution :** Rafraîchissement forcé du navigateur (Cmd+Shift+R sur Mac, Ctrl+Shift+R sur Windows)

### Problèmes d'Images

**Problème :** L'image ne s'affiche pas
**Solution :**
- Vérifiez le chemin du fichier (sensible à la casse !)
- Vérifiez que l'image est dans le bon dossier
- Vérifiez que l'extension correspond au type de fichier réel
- Assurez-vous que le chemin commence par `/images/` pour les images static

**Problème :** Image trop grande/lente à charger
**Solution :** Compressez l'image avant de la télécharger en utilisant [TinyPNG](https://tinypng.com/)

### Problèmes de Publication

**Problème :** Le push a échoué
**Solution :**
- Tirez d'abord les dernières modifications : `git pull`
- Vérifiez l'authentification GitHub
- Vérifiez la connexion réseau

**Problème :** Le site ne se met pas à jour après le push
**Solution :**
- Attendez 2-3 minutes pour la construction Cloudflare
- Vérifiez le tableau de bord Cloudflare Pages pour les erreurs de construction
- Videz le cache du navigateur

---

## Ressources

- [Guide Markdown](https://www.markdownguide.org/) - Référence Markdown complète
- [Documentation Hugo](https://gohugo.io/documentation/) - Documentation officielle Hugo
- [Docs Cloudflare Pages](https://developers.cloudflare.com/pages/) - Aide au déploiement
- [TinyPNG](https://tinypng.com/) - Outil de compression d'images
- [Unsplash](https://unsplash.com/) - Photos gratuites

---

**Bonne création de contenu ! 🎉**
