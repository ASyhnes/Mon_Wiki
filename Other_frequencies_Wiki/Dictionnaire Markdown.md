
---

id: test-markdown  

title: Markdown pour Docusaurus  

sidebar_position: 98

---

  

# Markdown pour Docusaurus

  

Ce fichier markdown démontre la plupart des fonctionnalités prises en charge par **Docusaurus**.

  

## Formatage de base

  

Vous pouvez rendre le texte **gras**, *italique* ou ~~barré~~.

  

### Titres

  

# Titre H1  

## Titre H2  

### Titre H3  

#### Titre H4  

##### Titre H5  

###### Titre H6  

  

### Règle horizontale

  

---  

___  

  

## Listes

  

### Liste non ordonnée

  

- Élément 1  

  - Sous-élément 1  

  - Sous-élément 2  

- Élément 2  

- Élément 3  

  

### Liste ordonnée

  

1. Premier élément  

2. Deuxième élément  

   1. Sous-élément 1  

   2. Sous-élément 2  

3. Troisième élément  

  

### Liste de tâches

  

- [x] Tâche 1  

- [X] Tâche 2  

- [ ] Tâche 3  

  

## Liens

  

[Lien vers perdu.com](https://perdu.com)

  

## Images

  

![Image](https://picsum.photos/100/100)

  

## Citations

  

> Ceci est une citation.  

>  

> Une autre ligne dans la citation.

  

## Code en ligne

  

Voici un `code en ligne`.

  

## Blocs de code

  

```js

// Bloc de code JavaScript

function helloWorld() {

  console.log('Hello, world!');

}

```

  

```python

# Bloc de code Python

def greet():

    print("Hello, world!")

```

  

### Bloc de code avec mise en évidence de la syntaxe

  

```js title="hello.js"

// Ceci est un fichier JavaScript

console.log("Bonjour depuis hello.js");

```

  

## Tableaux

  

| Syntaxe    | Description |

| ---------- | ----------- |

| En-tête    | Titre       |

| Paragraphe | Texte       |

  

| Aligné à gauche | Centré    | Aligné à droite |

| :-------------- | :-------: | --------------: |

| Gauche          | Centre    | Droite          |

  

## Images avec légendes

  

![Belle Montagne](https://picsum.photos/600/400)  

*Ceci est une belle montagne.*

  

## Admonitions (Alertes)

  

:::note  

Ceci est une **note**.  

:::

  

:::tip  

Ceci est un **conseil**.  

:::

  

:::danger  

Ceci est une alerte de **danger**.  

:::

  

:::info  

Ceci est une alerte **d'information**.  

:::

  

## Composants MDX personnalisés

  

Vous pouvez créer des composants React personnalisés dans les fichiers markdown en utilisant MDX.

  

```mdx

import React from 'react';

  

export const CustomButton = () => (

  <button style={{ padding: '10px', backgroundColor: 'blue', color: 'white' }}>

    Bouton personnalisé

  </button>

);

  

<CustomButton />

```

  

## Diagrammes Mermaid

  

```mermaid

graph TD;

    A-->B;

    A-->C;

    B-->D;

    C-->D;

```

  

## Émojis

  

Vous pouvez utiliser des émojis dans le markdown : 🎉 👍 💯

  

## Conclusion

  

Ce fichier de test couvre la plupart des fonctionnalités markdown et MDX que vous pouvez utiliser dans **Docusaurus**.