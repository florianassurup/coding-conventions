# Guide de Naming CSS : Respect des Bonnes Pratiques et du Clean Code

Ce guide a pour objectif de garantir une écriture cohérente, lisible et maintenable des styles CSS dans vos projets, tout en respectant les standards de l'industrie.

---

## 1. **Conventions de formatage**

### 1.1 Utiliser des minuscules uniquement
- Tous les noms de classes et d’ID doivent être en minuscules pour éviter les erreurs liées à la sensibilité à la casse (*case-sensitive*).
- Cette convention est essentielle pour maintenir une cohérence et éviter des conflits dans les environnements sensibles à la casse, comme Linux.

```html
<!-- Correct : -->
<div class="menu-item"></div>

<!-- Incorrect : -->
<div class="MenuItem"></div>
```

### 1.2 Utiliser le tiret (`-`) comme séparateur
- Préférez le tiret pour séparer les mots dans les noms de classes afin d’améliorer la lisibilité et de respecter les conventions telles que BEM.

```html
<!-- Correct : -->
<div class="card-header"></div>

<!-- Incorrect : -->
<div class="card_header"></div>
```

---

## 2. **Conventions pour les classes**

### 2.1 Utiliser une structure hiérarchique
- Adoptez la méthodologie **BEM (Block, Element, Modifier)** pour structurer les noms de classe :
  - **Block** : Représente un composant indépendant.
  - **Element** : Représente une partie du composant.
  - **Modifier** : Représente une variation ou un état du composant.

```html
<!-- Exemple avec BEM : -->
<div class="button button--primary">
  <span class="button-icon"></span>
  <span class="button-text">Submit</span>
</div>
```

### 2.2 Éviter les noms génériques
- Les noms doivent refléter clairement leur fonction.

```html
<!-- Correct : -->
<div class="navbar"></div>

<!-- Incorrect : -->
<div class="header"></div>
```

> **Conseil** : Dans les projets complexes, préférez des noms comme `site-header` pour plus de précision.

---

## 3. **Conventions pour les ID**

### 3.1 Réserver les ID pour des cas spécifiques
- Les ID doivent être utilisés uniquement pour des éléments uniques.
- Privilégiez les classes pour le stylage afin d’éviter les problèmes liés à leur haute spécificité en CSS.

```html
<!-- Correct : -->
<div id="main-header"></div>

<!-- Incorrect : -->
<div id="button"></div>
```

### 3.2 Respecter les conventions de nommage
- Les noms d’ID doivent suivre les mêmes conventions que les classes (minuscules avec tirets).

---

## 4. **Gestion des états et des variations**

### 4.1 Utiliser des classes pour les états
- Représentez les états avec des classes, par exemple `is-active` ou `has-error`, au lieu d’utiliser des ID ou de coder directement dans le DOM.

```html
<!-- Correct : -->
<div class="menu-item is-active"></div>

<!-- Incorrect : -->
<div id="active-menu-item"></div>
```

### 4.2 Préfixer les classes d’état
- Utilisez des préfixes comme `is-` et `has-` pour signaler un état ou une condition.

```html
<!-- Correct : -->
<div class="button is-disabled"></div>
<div class="form has-error"></div>

<!-- Incorrect : -->
<div class="button disabled"></div>
<div class="form error"></div>
```

---

## 5. **Noms fonctionnels et descriptifs**

### 5.1 Nommer en fonction de la finalité
- Les noms doivent décrire le rôle fonctionnel de l’élément, pas seulement son apparence.

```html
<!-- Correct : -->
<div class="alert alert--error"></div>

<!-- Incorrect : -->
<div class="red-box"></div>
```

---

## 6. **Organisation et modularité**

### 6.1 Groupement logique
- Organisez vos styles en blocs logiques : composants, layouts, et utilitaires.

Exemple :
  - **Composants** : `.button`, `.card`, `.navbar`.
  - **Layouts** : `.container`, `.grid`, `.row`.
  - **Utilitaires** : `.text-center`, `.m-4`, `.p-2`.

### 6.2 Utilisation des fichiers modulaires CSS ou SCSS
- Divisez vos styles en modules logiques.

```scss
// Exemple de fichier SCSS modulaire
// styles.scss
@import 'components/button';
@import 'components/navbar';
@import 'layouts/grid';
```

### 6.3 Adopter des classes utilitaires et des variables CSS
- Utilisez des classes utilitaires pour des styles récurrents (ex. Tailwind CSS).
- Adoptez les variables CSS pour améliorer la modularité et la réutilisation.

```css
:root {
  --primary-color: #007bff;
  --secondary-color: #6c757d;
}

.button {
  background-color: var(--primary-color);
}
```

---

## 7. **Validation et nettoyage**

### 7.1 Supprimer les classes inutilisées
- Identifiez et supprimez les classes inutiles pour alléger le projet.
- Utilisez des outils comme **PurgeCSS** ou **UnCSS** pour automatiser cette tâche.

### 7.2 Valider avec des outils
- Employez des outils comme [Stylelint](https://stylelint.io/) pour vérifier vos feuilles de style.

---

## 8. **Annexe : Checklist des bonnes pratiques**

- Les noms de classes et d’ID sont en minuscules avec des tirets comme séparateurs.
- Respect de la structure BEM pour les composants.
- Utilisation des préfixes `is-` et `has-` pour les états.
- Noms fonctionnels et descriptifs, jamais basés sur l’apparence.
- Organisation modulaire des styles.
- Validation et nettoyage réguliers.

En suivant ces règles, vos styles CSS seront plus lisibles, maintenables et conformes aux standards de l'industrie. Ces bonnes pratiques favoriseront une collaboration efficace et réduiront la dette technique.
