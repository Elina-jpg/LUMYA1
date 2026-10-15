# Atelier LUMYA · mode d'emploi

Ce dossier `atelier` est **pour toi uniquement**. Il contient tous les textes et les codes en clair : ne le pousse jamais sur GitHub.

## Ce qu'il y a dans le dossier LUMYA

| Dossier / fichier | Rôle | Sur GitHub ? |
|---|---|---|
| `site/index.html` | Le site, avec les trois zones protégées chiffrées | **Oui** |
| `site/README.md` | Mention « site fictif » pour qui tombe sur le dépôt | **Oui** |
| `atelier/source.html` | La même page en clair : c'est elle que tu modifies | Non |
| `atelier/chiffrer.html` | L'outil qui transforme `source.html` en `index.html` chiffré | Non |
| `atelier/LISEZ-MOI.md` | Ce fichier | Non |

## Mettre le site en ligne

1. Crée un dépôt public avec un nom neutre (par exemple `lumya`), car le pseudo et le nom du dépôt apparaissent dans l'adresse.
2. Mets **le contenu** du dossier `site` à la racine du dépôt : `index.html` et `README.md`.
3. Sur GitHub, va dans **Settings → Pages**. Sous « Build and deployment », choisis **Deploy from a branch**, la branche **main** et le dossier **/ (root)**, puis enregistre.
4. Au bout d'une ou deux minutes, le site répond à `https://ton-pseudo.github.io/lumya/`. C'est cette adresse, sans nom de fichier, qu'il faut mettre dans le QR code.
5. Teste les trois codes sur ton iPhone en scannant le QR code avant la soirée.

**Si tu avais déjà poussé l'ancienne version** (`LUMYA – Cercle d'Éveil.html`) : la supprimer du dépôt ne suffit pas, car elle reste lisible dans l'historique Git. Le plus simple est de supprimer ce dépôt et d'en créer un neuf avec seulement le contenu de `site`.

## Les codes actuels

| Zone | Code | Remarque |
|---|---|---|
| 1 · Espace membres | `4817` | |
| 2 · Archives supprimées | `bleu` | Indice affiché : la couleur préférée de Raphaël |
| 3 · Messagerie de Shérazade | `cercle2018` | « cercle » + année de fondation (2026 − 8 ans) |

Les majuscules et les espaces au début ou à la fin ne comptent pas (`Bleu` ou ` 4817 ` passent). En revanche, `cercle 2018` avec un espace au milieu est refusé, comme le précise le mémo du jeu.

## Modifier un texte, un mail ou un code

On ne modifie **jamais** `index.html` directement, puisque son contenu est chiffré.

1. Ouvre `atelier/source.html` dans un éditeur de texte et fais tes changements.
   - Les contenus protégés sont dans les blocs `<template data-zone="…" data-code="…">` en bas du fichier. Le code de chaque zone est dans `data-code`.
   - Garde la première ligne de chaque bloc exactement sous cette forme : `<template data-zone="2" data-code="bleu">`.
   - Un mail correspond à un `<article>`. `data-dossier` vaut 0 pour la boîte de réception, 1 pour les brouillons, 2 pour les envoyés et 3 pour la corbeille. Ajoute `data-nonlu` pour qu'il apparaisse comme non lu.
   - Ne supprime pas le repère `<!--ZONES-->` ni les repères `<!--ATELIER-->` / `<!--/ATELIER-->`. Tout ce qui se trouve entre ces deux derniers est retiré de la version publiée.
2. Ouvre `source.html` dans ton navigateur pour vérifier le rendu. Les codes y fonctionnent comme en ligne, et un bandeau rappelle que c'est la version atelier.
3. Ouvre `atelier/chiffrer.html` (avec Chrome ou Firefox), dépose `source.html`, clique sur **Générer index.html** puis télécharge le fichier.
4. Remplace `site/index.html` par le fichier téléchargé, puis pousse-le sur GitHub.

L'outil redéchiffre chaque zone pour vérifier le résultat. Il te prévient aussi si un code apparaît en clair ailleurs dans la page publique, ce qui pourrait constituer un indice involontaire.

## Bon à savoir

- **La page retient les codes déjà saisis** tant que l'onglet reste ouvert. Si Safari recharge la page quand le téléphone se met en veille, les joueurs retrouvent l'espace membres, l'onglet en cours et les zones déjà ouvertes. Un nouvel onglet, ou un nouveau scan du QR code, repart verrouillé.
- **Ce que protège le chiffrement** : ni le code source de la page ni le dépôt GitHub ne contiennent les textes secrets ou les codes. Un joueur qui affiche le source ne voit que des blocs illisibles. Seule limite théorique : un code de 4 chiffres pourrait être retrouvé par quelqu'un qui écrirait un programme pour tester les 10 000 combinaisons. Pour une soirée, c'est sans risque, mais un code plus long réglerait la question.
- **Test sur l'ordinateur** : `index.html` s'ouvre aussi depuis le disque avec Chrome ou Firefox. Si les codes ne passent pas dans un autre navigateur, teste directement la version en ligne.
- Les polices viennent de Google Fonts. Sans connexion, le site s'affiche avec une police de remplacement.

## Corrections apportées par rapport à la version d'origine

- Fichier renommé en `index.html` pour GitHub Pages, ce qui donne une adresse courte et un QR code plus simple.
- Les trois zones protégées sont chiffrées (AES-256, clé dérivée du code). Les codes ne figurent plus dans la page.
- Ajout d'une balise `noindex` pour que le site ne soit pas référencé par Google, et d'un `README.md` « site fictif » dans le dépôt.
- La classe `t` servait à la fois aux titres et aux onglets, ce qui faisait clignoter les titres de l'accueil. Les onglets utilisent désormais la classe `pane`.
- Sur iPhone, ouvrir un mail fait défiler la page jusqu'au message, et un bouton « ← Messages » ramène à la liste.
- Dans les champs de code, la majuscule automatique et la correction orthographique sont désactivées.
- L'avatar du brouillon au journaliste affiche bien un « R » majuscule.
