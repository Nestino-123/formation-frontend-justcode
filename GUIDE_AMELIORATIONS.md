# Guide d'amélioration du portfolio — explications pour débutant

Ce guide explique les changements apportés à ton projet initial et les exercices à réaliser pour les comprendre. **Le code du site est en allemand**, comme ton portfolio original et ton CV ; les explications sont en français.

## 1. Garder le projet existant

Nous conservons `index.html`, `menu.html`, `contact.html`, `style.css` et les trois images. Le PDF `programme.pdf` est déplacé dans `document/` pour respecter la consigne `nom_Projet/document/programme.pdf`. Le dossier `.git` n'est pas dans l'archive pour éviter de copier un historique Git ou des paramètres locaux.

**Exercice :** dans VS Code, repère ces fichiers dans l'Explorer et ouvre les trois pages dans le navigateur.

## 2. Déclarer la bonne langue

Avant : `<html lang="en">` alors que le contenu est surtout en allemand.

Après : `<html lang="de">`.

`lang` aide les lecteurs d'écran, les navigateurs et les moteurs de recherche à interpréter la langue. `<meta charset="UTF-8">` assure l'affichage de `ä`, `ö`, `ü`, `ß`, etc. `<meta name="viewport">` prépare l'affichage mobile.

**Exercice :** cherche `lang="de"` dans les trois pages.

## 3. Utiliser une structure HTML sémantique

`<header>` = en-tête et navigation ; `<nav>` = menu ; `<main>` = contenu principal ; `<section>` = groupe thématique ; `<article>` = contenu indépendant ; `<footer>` = pied de page.

Chaque page possède un seul `<h1>` principal. Les grandes sections ont des `<h2>`, et leurs cartes des `<h3>`. Cette hiérarchie aide à lire, maintenir et rendre accessible le site.

**Exercice :** dans `index.html`, trouve les sections `ueber-mich`, `faehigkeiten`, `projekte`, `erfahrung` et `ausbildung`.

## 4. Corriger les liens de navigation

Avant, les liens `#ueber-mich` et similaires pointaient vers des identifiants qui n'existaient pas. Dans `index.html`, on trouve désormais :

```html
<section id="ueber-mich">...</section>
```

et dans la navigation :

```html
<a href="#ueber-mich">Über mich</a>
```

Depuis une autre page, il faut inclure le fichier :

```html
<a href="index.html#ueber-mich">Über mich</a>
```

**Exercice :** clique sur « Über mich » depuis `index.html`, puis depuis `contact.html`. Les deux liens doivent atteindre la même section.

## 5. Créer le Hero (jours 1–2 du programme HTML)

Le Hero est la première zone visible de la page d'accueil. Il contient le nom, la présentation, l'objectif, la photo et deux liens d'action.

Le texte utilise `<h1>`, `<p>` et `<a>`. La photo est insérée avec `<img src="img/mein_portofolio_bild.jpg" alt="...">` : `src` indique le chemin du fichier, `alt` décrit l'image si elle n'est pas visible ou pour un lecteur d'écran.

**Exercice :** modifie une phrase de présentation et recharge le navigateur.

## 6. Structurer les compétences (jour 3)

Les compétences sont regroupées en trois catégories : web, programmation/backend, données/compétences transversales. Chaque catégorie utilise une liste `<ul>` et des éléments `<li>`.

La présence d'une technologie dans la liste ne signifie pas que tu es expert. Vérifie toi-même ton niveau et actualise le texte à mesure que tu progresses.

**Exercice :** ajoute un outil que tu as réellement utilisé dans la liste appropriée.

## 7. Présenter les projets (jours 3 et 10)

Les trois noms de ton fichier original sont conservés : Sushi Go, Smart Mensa et Tic-Tac-Toe (orthographe normalisée). Chaque projet utilise un `<article>`.

Nous n'avons pas inventé les langages, fonctionnalités, images ou liens GitHub de ces projets. Des indications « documentation en préparation » sont présentes.

Pour compléter une carte, renseigne : objectif, ton rôle, fonctionnalités, technologies, difficultés, capture d'écran, lien GitHub réel. Le programme demande au moins trois projets en HTML V1 et recommande quatre projets visibles pour la version finale.

**Exercice :** commence par décrire Smart Mensa avec tes propres mots en 3 phrases.

## 8. Ajouter expériences et formation

Ces sections rendent ton portfolio cohérent avec ton CV : City Hacker School, travail sur les données, tutorat IA, stage Weptech et études d'informatique. Vérifie dates et descriptions avant de publier.

Nous avons retiré l'adresse de rue privée, le numéro de téléphone personnel et la carte pointant vers cette adresse : ils ne sont pas nécessaires pour un portfolio public.

## 9. Améliorer la page menu.html

Auparavant, `menu.html` montrait surtout une image. Maintenant, elle sert de sommaire : six cartes de navigation et quatre étapes de formation (HTML, CSS, JavaScript, React).

Les cartes sont des liens `<a>` ; la liste des étapes utilise `<ol>` pour conserver un ordre logique.

**Exercice :** depuis `menu.html`, clique sur « Projekte » et vérifie que tu arrives sur la section correspondante.

## 10. Améliorer le formulaire de contact (jours 8–9)

Chaque champ a un `<label for="identifiant">` associé à un `<input id="identifiant">`. `required` impose la saisie, `type="email"` vérifie une forme d'adresse e-mail, et `minlength="10"` demande au moins dix caractères dans le message.

```html
<label for="email">E-Mail</label>
<input id="email" type="email" name="E-Mail" required>
```

**Limite importante :** `action="mailto:..."` dépend du logiciel de messagerie de l'utilisateur. Ce n'est pas un service d'envoi de messages automatique. Le bouton a donc été nommé « E-Mail-Programm öffnen ». Une vraie transmission sera étudiée plus tard avec JavaScript et/ou un service dédié.

**Exercice :** clique sur « E-Mail-Programm öffnen » avec un champ obligatoire vide. Le navigateur doit demander de le remplir.

## 11. Apprendre le CSS progressivement (semaines 1–3)

Dans `style.css`, les sections commentées montrent :

- **Sélecteurs** : `.hero` cible une classe, `h1` cible une balise.
- **Couleurs et variables** : `--navy` est définie dans `:root` ; `var(--navy)` la réutilise.
- **Box Model** : `padding` est l'espace intérieur, `margin` l'espace extérieur, `border` la bordure.
- **Flexbox** : `display: flex` aligne les liens de navigation, boutons et étiquettes.
- **CSS Grid** : `display: grid` organise les cartes et le Hero en colonnes.
- **Responsive** : `@media (max-width: 720px)` réorganise la page pour un téléphone.
- **Pseudo-classes** : `:hover` réagit au survol et `:focus-visible` aide la navigation au clavier.
- **Transitions** : une légère animation au survol des boutons, désactivée si l'utilisateur préfère moins d'animations.

**Exercices :**

1. Dans `:root`, change `--accent: #1fbfa5` et observe les boutons.
2. Change `gap: 20px` dans `.projects-grid` et observe l'espacement.
3. Réduis la largeur de la fenêtre : les trois cartes passent à deux puis une colonne.
4. Utilise `Tab` pour naviguer au clavier et observer les contours de focus.

## 12. Vérifier le résultat et pousser sur GitHub

Dans VS Code, ouvre le dossier du repository cloné, pas un dossier imbriqué supplémentaire. Ouvre `index.html` dans ton navigateur et teste :

1. Les trois pages.
2. Les liens vers les sections.
3. Les trois images.
4. Le PDF `document/programme.pdf`.
5. Les champs obligatoires du formulaire.
6. L'affichage sur un écran étroit.

Puis dans le terminal du repository :

```bash
git status
git add .
git commit -m "Amelioration du portfolio HTML et CSS"
git push
```

## 13. Ce qu'on fera dans les prochaines étapes du programme

**JavaScript (5 semaines)** : variables, conditions, boucles, fonctions, chronomètre, application API, Todo List.

**JavaScript navigateur (Portfolio V3)** : menu mobile, mode sombre, validation plus avancée, filtres de projets, `localStorage`, éventuellement API GitHub.

**React (Portfolio V4)** : composants `Navbar`, `Hero`, `About`, `Skills`, `Projects`, `Contact`, `Footer` ; props, `useState`, hooks, Router, chargement et erreurs.

**Finalisation** : compléter quatre projets documentés, tester l'accessibilité, publier le site et présenter le résultat.

**Ne saute pas directement à React** : le but de la formation est de comprendre les fondations HTML/CSS/JavaScript avant de transformer le site en application.
