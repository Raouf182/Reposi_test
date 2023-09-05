# Le HTML

L'HTML (HyperText Markup Language) est le langage de balisage utilisé pour créer et structurer le contenu d'une page Web. Il s'agit d'une composante fondamentale du World Wide Web, permettant aux créateurs de sites Web de définir la structure et la présentation des informations affichées dans un navigateur. HTML fonctionne en utilisant un système de balises qui décrivent le type de contenu et sa mise en forme.

## Notions clés

1. **Balises et éléments:** en HTML, le contenu est structuré à l'aide de balises. Les balises sont des éléments entourés de chevrons angulaires (< >). Elles sont utilisées pour définir différents types de contenu tels que les titres, les paragraphes, les images, les liens, etc...  

*Exemple d'une balise de titre:*
```html
<h1>Ceci est un titre</h1>
```

2. **Balises ouvrantes et fermantes:** La plupart des balises HTML ont une balise ouvrante et une balise fermante pour délimiter le contenu qu'elles affectent. La balise fermante a un slash ( / ) qui se situe juste avant le nom de la balise.

*Exemple d'une paire de balises:*
```html
<p>Ceci est un paragraphe</p>
```

3. **Nesting (Hiérarchie)** : Vous pouvez imbriquer des balises les unes dans les autres pour créer une structure hiérarchique.  
Les balises internes sont contenues à l'intérieur des balises externes.

*Exemple d'imbrication de balises:*
```html
<ul>
    <li>Objet1</li>
    <li>Objet2</li>
    <li>Objet3</li>
</ul>
```

4. **Attributs:** Les balises peuvent avoir des attributs qui fournissent des informations supplémentaires sur l'élément. Les attributs sont toujours spécifiés à l'intérieur de la balise ouvrante.

*Exemple d'attribut:*
```html
<a href="www.monsite.fr">nom_du_site_affiché_sur_la_page</a>
```

5. **Structure de base:** Une page HTML de base commence généralement par une déclaration de type de document (`<!DOCTYPE>`) suivi d'une balise `<html>` qui contient des balises `head` et `body`.

*Exemple de structure de base:*
```html
<!DOCTYPE html>
    <html>
        <head>
            <title>Titre de la page affiché dans l'onglet du navigateur</title>
        </head>

        <body>
            <h1>Titre de la page</h1>
            <p>Contenu de la page</p>
        </body>
    </html>
```

L'HTML fournit la structure fondamentale d'une page web, mais pour définir le style et le comportement, il est souvent utilisé en combinaison avec des langages tels que le **CSS** (Cascading Style Sheet) pour la mise en page et **Javascript** pour l'interaction dynamique avec les utilisateurs.

## Les balises de base

```html
<p>Ceci est un paragraphe</p> 

<h1>Titre de niveau 1</h1>

<br /> : Elle permet de revenir à la ligne (par exemple au sein d'un paragraphe)
<hr /> : Elle permet de créer un séparateur horizontal.

<b>Met le texte en gras</b>  
<i>Met le texte en italique</i> 
<u>Souligne le texte</u> 
**On évitera d'utiliser ces 3 balises, on préfèrera appliquer le style en CSS**

<strong>Met l'emphase sur uen partie du texte (le navigateur l'appliquera en gras)</strong>
<em>Met l'emphase sur une partie du texte (le navigateur l'appliquera en italique)</em>

<a href="www.monsite.fr">Créer un lien hypertexte</a>

<ul>
    <li>Ceci est une liste non organisée</li>
</ul>

<ol>
    <li>Ceci est une liste organisée</li>
</ol>

```

## Les tableaux

Pour construire un tableau, il me faut avant tout une balise `<table></table>`. A l'intérieur de cette balise, je spécifie le nombre de lignes que comporte mon tableau à l'aide de `<tr></tr>`

```html
<table>
    <tr></tr>
    <tr></tr>
    <tr></tr>
</table>
```

A l'interieur de ces lignes, je peux placer des headers avec `<th></th>` ou des donnée simples avec `<td></td>`

```html
<table>
    
    <tr>
        <th>header1</th>
        <th>header2</th>
    </tr>
    <tr>
        <td>data1</td>
        <td>data2</td>
    </tr>
    <tr>
        <td>data3</td>
        <td>data4</td>
    </tr>
</table>
```

Pour le référencement et pour un code plus solide et lisible, je précise grâce aux balises `<thead></thead>`,`<tbody></tbody>` et `<tfoot></tfoot>`, l'organisation de mon tableau.

```html
<table>
    <thead>
        <tr>
            <th>header1</th>
            <th>header2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>data1</td>
            <td>data2</td>
        </tr>
        <tr>
            <td>data3</td>
            <td>data4</td>
        </tr>
    </tbody>
</table>
```
On peut rajouter un titre à son tableau grâce à la balise `<caption></caption>`   
Au niveau des attributs, on peut rajouter des attributs de style à notre tableau, mais on évitera de le faire, on privilégiera le CSS :   
`border ="nombre` : La taille en pixels des bordures  
`width="nombre"` : La longueur en pixels de notre tableau  
`height="nombre` : La hauteur en pixels de notre tableau  
`align="left", "right" ou "center"` : L'alignement vertical des données  

Si on veut que l'une de nos données prenne plus d'une ligne ou colonne, on lui appliquera l'attribut `rowspan="nombre"` ou `colspan="nombre"`.

## Les ancres avec la balise \<a>

Notre balise `<a>` permet aussi de faire des références à notre page elle-même, grâce à un système d'**ancrage**. Il suffit de marquer l'une de nos balises d'un identifiant et de rappeler cet identifiant dans notre lien href précédé d'un dièse (#)

```html
<p id="mon-ancre"></p>
<a href="#mon-ancre"></a>
```


## Les boutons `<button>`

Pour naviguer sur un site internet ou en informatique en général, on utilise des boutons. Pour créer un bouton en HTML, j'utiliserai une balise `<button>nom_du_bouton</button>`.

Il est cependant intéressant de spécifier le type de bouton, grâce à l'attribut type:  
```html
- <button type="submit">: Il s'agit d'un bouton classique. C'est le choix par défaut si le type n'est pas spécifié.
- <button type="submit"> : Utile uniquement au sein d'un formulaire, il envoie le formulaire.
- <button type="reset"> : Utile également au sein d'un formulaire, il réinitialise les champs de ce formulaire.
```
Si on veut désactiver un bouton, on lui met l'attribut `disabled` : `<button disabled>`

## Les images `<img>`

C'est une balise auto-fermante.  
Pour afficher une image, je dois indiquer à ma balise sa **source** via l'attribut `src`. Elle peut provenir du web ou êtrr en local dans mon ordinateur.  
Attention, si l'image est stockée dans votre ordinateur, le fichier devra être fourni durant l'hébergement de votre site si vous souhaitez que tout le monde puisse les consulter. On préfèrera indiquer le chemin des images sous forme de **chemin relatif**.

On peut redimensioner nos images grâce aux **attributs** `width` et `height` auxquels je donnerai une valeur en pixels.  

Enfin, très important pour l'accessibilité, j'essaye, dès que j'ai une balise image de lui mettre un **attribut** `alt` (pour alternatif). C'est un texte qui va s'afficher si l'image n'arrive pas elle-même à s'afficher. Ce texte alternatif est également utile pour certaines formes de handicap.  

Au sein de notre répertoire de projet, on préfèrera stocker nos images dans un dossier qui leur est dédié. On nommera généralement ce répertoire "img".  

## Les formulaires `<form>`

Pour ouvrir et fermer un formulaire, on applique les balises `<form></form>`. Cette balise contiendra beaucoup d'attributs importants pour notre JavaScript. Mais nous allons d'abord voir le placement des inputs en HTML :  

### Les inputs

En HTML, les éléments `<input>` sont utilisés pour collecter des données entrées par les utilisateurs. Il existe plusieurs types d'input couramment utilisés pour différents tupes de données et d'interactions.  
Si je veux rendre l'un de mes inputs **obligatoire**, j'utilise l'attribut `required`.
Voici les plus courants :

1. **Texte (`text`)** : Ce type d'`input` permet aux utilisateurs de saisir du texte libre, comme des noms, des adresses, des commentaires, etc ...

```html
<input type="text" placeholder="Votre nom" name="nom">
```

2. **Mot de passe (`password`)** : Utilisé pour collecter des mots de passe, ce type masque les caractères saisis.

```html
<input type="password" placeholder="Mot de passe" name="password">
```

3. **Cases à cocher (`checkbox`)** : Les cases à cocher permettent aux utilisateurs de sélectionner plusieurs options parmi un groupe d'éléments. C'est l'attribut `name` qui permet de rattacher les éléments entre eux.


```html
<input type="checkbox" name="interets" value="football"> Football
<input type="checkbox" name="interets" value="tennis"> Tennis
```

4. **Boutons radio (`radio`)** : Les boutons radios permettent aux utilisateurs de ne sélectionner qu'une seule option parmi un groupe d'éléments. C'est l'attribut `name` qui permet de rattacher les éléments entre eux.

```html
<input type="radio" name="interets" value="football"> Football
<input type="radio" name="interets" value="tennis"> Tennis
```

5. **E-mail (`email`)** : Il est utilisé pour collecter des adresses e-mail, il vérifie également la validité de la syntase de l'adresse saisie.

```html
<input type="email" placeholder="Votre adresse e-mail" name="email">
```

6. **Dates (`date`)** : Utilisé pour collecter des dates, il affiche un sélecteur de date.

```html
<input type="date" name="date">
```

7. **Numérique (`number`)** : Ce type d'input permet aux utilisateurs de saisir des valeurs numériques.

```html
<input type="number" name="nombre">
```

8. **URL (`url`)** : Utilisé pour collecter des URL (adresses de sites web), il vérifie également la validité de l'URL saisie.

```html
<input type="url" placeholder="Votre lien" name="url">
```

9. **Téléphone (`tel`)** : Utilisé pour collecter des numéros de téléphone.

```html
<input type="tel" placeholder="Votre numéro de téléphone" name="téléphone">
```

10. **Fichier (`file`)** : Les éléments de type `file` permettent aux utilisateurs de selectionner et de télécharger des fichiers à partir de leur ordinateur.

```html
<input type="file" name="fichier_utilisateur">
```

11. **Bouton (`button`)** : Cet élément crée un bouton personnalisable qui peut être utilisé pour déclencher des actions JavaScript ou des soumissions de formulaire. Il peut également vous permettre de reset le formulaire. 

```html
<input type="button" value="Cliquez moi" name="bouton">
<input type ="submit"> <!-- Envoyer un formulaire -->
<input type ="reset"> <!-- Reset un formulaire -->
```

### La liste de sélection `select`

Pour afficher une liste déroulante en HTML, j'utiliserai la balise `select`. Je délimiterai chacune des options de mon sélecteur à l'aide de la balise `option`.

```html
<select name="pays">
    <option value="france">France</option>
    <option value="espagne">Espagne</option>
    <option value ="allemagne">Allemagne</option>
</select>
```

### La boite de texte `textarea`

Un élément `textarea` est utilisé pour créer une zone de texte multilignes.

```html
<textarea name="description" rows="10" cols="30"></textarea>
```

## La sémantique en HTML
### Les balises spécifiques

`<header></header>` : Utilisé pour représenter l'en-tête d'une section ou d'une page web. Il peut contenir des éléments tels que le logo, le titre de la page, la navigation principale...

`<nav></nav>` : Utilisé pour représenter la section de navigation principale d'une page web. Il contient généralement des liens vers d'autres parties du site.

`<main></main>` : Utilisé pour représenter le contenu principal d'une page web. Il devrait contenir le contenu central et unique de la page.

`<section></section>` : Utilisé pour diviser le contenu en sections thématiques. 

`<article></article>` : Utilisé pour représenter un contenu autonome et indépendant comme un article de blog ou une publication.

`<aside></aside>` : Utilisé pour représenter du contenu connexe ou supplémentaire qui est généralement mis en évidence à côté du contenu principal, comme des informations complémentaires, des publicités, etc...

`<footer></footer>` : Utilisé pour représenter le pied de page d'une section ou d'une page web. Il peut contenir des informations de contact, des liens de navigation supplémentaire, etc...

`<figure></figure>` : Utilisé pour encapsuler un contenu multimédia comme une image, une vidéo ou une illustration, avec une légende associée (mais facultative), le `<figcaption></figcaption>`.

### Les balises génériques

`<div></div>` : Elle est principalement utilisée pour regrouper des éléments en bloc et créer une structure de page, elle ne nécessite pas d'un contexte spécifique.

`<span></span>` : Elle n'est pas une balise en bloc mais une balise en ligne. Elle sert à appliquer des styles ou des modifications à une portion de texte à l'intérieur d'un élément plus large.
