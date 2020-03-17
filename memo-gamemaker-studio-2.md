# Mémo GameMaker Studio 2

*par flashjaysan*

## Introduction

*GameMaker Studio 2* est un moteur de jeux vidéos multi-plateformes. Principalement destiné à la création de jeux vidéos 2D, il embarque une multitude d'outils pour faciliter le développement. Il propose de scripter les comportements des éléments de jeu avec deux approches différentes.

- La première approche appelée *Drag and drop* (*DND*) vous permet de manipuler et d'organiser visuellement des briques d'actions. Elle est destinée aux débutants.
- La seconde approche utilise un langage de programmation appelé *GameMaker Language* (*GML*) spécifique à *GameMaker Studio 2*. Cette approche est la plus utilisée car elle permet un contrôle plus précis des choses.

## Système de coordonnées et angles

L'axe vertical (Y) augmente vers le bas. L'origine d'une Room se trouve dans son coin supérieur gauche. Un angle de 0 degrés pointe vers la droite. Les angles augmentent dans le sens anti-horaire (inverse des aiguilles d'une montre).

## Créer un nouveau projet

- Sur l'écran de démarrage, cliquez sur le bouton *New*. Si cet écran n'est pas visible, vous pouvez également utiliser le menu `File -> New Project` ou les touches `CTRL+N`.

- Vous devez ensuite choisir entre *GML* et *DND* en cliquant sur les boutons correspondants. Si vous n'êtes pas totalement débutant, utilisez *GML*.

- Enfin, sélectionnez un emplacement sur votre ordinateur et donnez un nom à votre projet.

**Remarque :** Les actions *DND* sont converties automatiquement en *GML* lorsque vous exportez votre jeu. Vous pouvez à tout moment demander à voir la conversion en *GML* sans convertir définitivement le script *DND* en faisant un clic droit sur le script *DND* et en choisissant l'option `Live Preview`. Vous pouvez également demander la conversion (définitive) d'un script *DND* en faisant un clic droit sur l'évènement et en choisissant l'option `Convert to GML`.

## Régler le nombre d'images par seconde

Dans la section `Main Options -> General`, paramétrez la fréquence de rafraichissement de l'écran (`60` par défaut) à la ligne `Game frames per second`.

**Conseil :** Créez un script `MACROS` et saisissez la ligne `#macro FRAME_RATE 60`. Cela définit une constante `FRAME_RATE` dont la valeur est `60` utilisable partout dans votre projet.

## Concepts de GameMaker Studio 2

Dans *GameMaker Studio 2*, un jeu est essentiellement composé de ressources *Rooms* (des écrans ou niveaux du jeu) qui comportent des ressources *Objects*.

**Remarque :** *GameMaker Studio 2* fournit à tout nouveau projet une *room* vide appelée `room0`. Testez le jeu vide en cliquant sur le bouton`Run`ou sur le menu `Build -> Run` ou en appuyant sur la touche `F5`.

-  Les ressources *Objects* interagissent entre elles par le biais de scripts *GML* (ou d'actions *DND* mais cela revient au même) attachés à des évènements. Pour afficher quelque chose à l'écran, un *object* a besoin d'une ressource *sprite* associée.
- Les ressources *Sprites* correspondent aux éléments graphiques du jeu. Un *sprite* peut être une simple image fixe ou une série d'images animées.

- Les ressources *Sounds* correspondent aux éléments audio du jeu. Un *sound* peut être un son ou une musique.

## Créer des ressources

Dans le panneau `Resources`, faites un clic droit sur un dossier correspondant à un type de ressource et choisissez l'option `Create X` (où `X` correspond au type de ressource à créer).

Donnez à la nouvelle ressource un nom unique (de préférence avec un préfixe indiquant le type de ressource car *GameMaker Studio 2* ne fait pas la distinction entre les différentes ressources).

**Remarque :** Vous pouvez renommer une ressource par la suite en faisant un clic droit dessus et en sélectionnant l'option `Rename` ou en appuyant sur la touche `F2`.

## Définir la résolution du jeu

*Par défaut, GameMaker Studio 2* définit la résolution générale du jeu en se basant sur la taille de la première *room* existante dans le dossier `Rooms` du panneau `Resources`.

- Dans le dossier `Rooms` du panneau `Ressources`, double cliquez sur `room0` (la Room créée par défaut) ou la première *room* de la liste pour l'ouvrir dans l'éditeur.

- Dans la section `Properties` du panneau `Room Editor`, sous-section `Room Settings`, définissez les dimensions de la *room* grâce aux champs `Width` (largeur) et `Height` (hauteur).

**Attention !** Si vous avez activé les *viewports* (en cochant la case `Enable Viewports` dans la sous-section `Viewport and Cameras`) et que des viewports ont la case `Visible` de cochée, la résolution du jeu sera celle du *viewport* visible. La résolution du jeu peut donc être différente de la taille de la *room* (par exemple avec une *room* très grande où la caméra n'affiche qu'une partie de la *room*).

- Définissez la résolution de ces *viewports* grâce aux champs `Width` (largeur) et `Height` (hauteur) de la sous-section `Camera Properties` de chaque *viewport* visible pour définir la résolution.

Vous pouvez également définir une résolution d'affichage du jeu différente de celle du *viewport* (par exemple si votre jeu en pixel art a une résolution très faible et que vous souhaitez afficher le jeu avec une résolution supérieure).

-  Utilisez les champs `Width` (largeur) et `Height` (hauteur) de la sous-section `Viewport Properties` de chaque *viewport* visible.

## Configuration générale

Pour ouvrir le menu de configuration du projet, cliquez sur le bouton `Game Options` ou, dans le panneau `Resources`, dans le dossier `Options`, double cliquez sur `Main`.

## Sprites

Bien que vous puissiez utilisez les fonctions de dessin fournies par *GameMaker Studio 2* pour afficher des formes géométriques à l'écran, vous aurez généralement besoin d'importer ou de créer des images pour afficher des choses à l'écran.

*GameMaker Studio 2* vous permet d'importer des images facilement et de les modifier directement depuis l'éditeur intégré.

### Créer un *sprite* vide

Faites un clic droit sur le dossier `Sprites` du panneau `Resources` et choisissez l'option `Create Sprite` ou les touches `ALT+S`.

Pour créer des *sprites* à partir de fichiers images, faites simplement cliquer les fichiers sur le dossier `Sprites` du panneau `Resources`.

### Importer une image dans un *sprite*

Cliquez sur le bouton `Import` du *sprite* pour sélectionner un fichier image.

### Créer un *sprite* à partir d'un fichier image

Une animation au format `.gif` est automatiquement importée sous la forme d'une suite d'images composant l'animation.

Un fichier image au format `.png` finissant par `_stripXX` est automatiquement importé sous la forme d'une suite de `XX` images en découpant le fichier image original horizontalement. Les sous-images du fichier image doivent être disposées à la suite sur une seule ligne.

Positionnez leur centre. Définissez leur rectangle de collision.

## Rooms

### Définir la couleur de fond

Dans la section `Layers` du panneau `Room Editor`, définissez la couleur de fond du calque `Background`.

## Objects

Dans le panneau `Resources`, faites un clic droit sur le dossier `Objects` puis sélectionnez `Create Object` ou les touches `ALT+O` pour créez un *object*.

### Attribuez un *sprite* à l'*object* créé.

Pour attribuer des comportements associés aux évènements `Create` et `Step`.

### Position d'une instance

Les propriété `x` et `y` définissent la position de l'instance.

### Editer les propriétés d'un *object*

Dans le panneau `ressources`, double cliquez sur l'*object* à éditer.

## Editer les propriétés d'une instance

Dans le panneau `Instances properties` ou dans la vue éditeur, double cliquez sur l'instance.

## Tester si une instance entre en collision avec une instance d'un Object

Utilisez la fonction `place_meeting` qui prend la position à tester et le nom de l'*Object*.

## Retourner ou redimensionner un Sprite

Les propriétés `image_xscale` et `image_yscale` définissent le taux d'agrandissement du *Sprite*. Utilisez une valeur négative pour retourner le *Sprite* autour de son origine.

## GML

### Commentaires

```js
// Commentaire de fin de ligne
/// Commentaire de documentation
/*
Commentaire
multi-lignes
*/
```

### Types de base et conversion

*GameMaker Studio 2* utilise trois types de base. Les booléens, les nombres (entiers ou à virgule) et les chaînes de caractères.

Un booléen peut valoir `false` ou `true`.  Ces valeurs sont équivalentes aux valeurs entières `0` et `1`.

*GameMaker Studio 2*  ne fait pas de distinction entre les nombres entiers et les nombres à virgules.

```js
var dix = 10;
var demi = 0.5;
var dix_et_demi = dix + demi;
```

Les littéraux chaînes sont écrits entre guillemets doubles.

```js
var bonjour = "bonjour";
```

Vous pouvez concaténer plusieurs chaînes avec l'opérateur ``.

```js
var bonjour = "bonjour";
var nom = "Steve";
var message = bonjour + ", " + nom + ".";
```

Vous pouvez convertir un nombre en chaîne grâce à la fonction `string`.

```js
var nombre = 10.5;
var chaine = string(nombre);
```

Vous pouvez convertir une chaîne en nombre grâce à la fonction `real`.

```js
var texte = "10";
var dix = real(texte);
```

### Afficher un message

La fonction `show_message` prend une chaîne de caractères en paramètre et l'affiche dans une boîte de dialogue lorsque l'évènement associé se déclenche.

### Saisie de l'utilisateur

La fonction `get_string` affiche une boîte de dialogue proposant à l'utilisateur de saisir une chaîne de caractères que vous pouvez ensuite utiliser dans votre jeu.

- Le premier paramètre est une chaîne correspondant au titre de la boîte de dialogue.
- Le second paramètre correspond à la chaîne de caractères utilisée par défaut et affichée dans le champ de saisie.

```js
var nom = get_string("Saisissez votre nom :", "Steve");
```

La fonction `get_integer` affiche une boîte de dialogue proposant à l'utilisateur de saisir un nombre entier que vous pouvez ensuite utiliser dans votre jeu.

- Le premier paramètre est une chaîne correspondant au titre de la boîte de dialogue.
- Le second paramètre correspond à un nombre utilisé par défaut et affiché dans le champ de saisie.

```js
var age = get_string("Saisissez votre age :", 18);
```

**Remarque :** L'utilisateur peut également saisir un nombre à virgule.

### Variables

#### Variables prédéfinies

*GameMaker Studio 2* définit automatiquement certaines variables. Chaque *room*, chaque instance d'*object* et de nombreuses autres choses possèdent des variables prédéfinies. Elles s'affichent en vert dans l'éditeur de *GameMaker Studio 2*.

**Attention !** Soyez attentif à la couleur des variables. Par exemple, la variable `speed` d'un *object* est une variable prédéfinie dans *GameMaker Studio 2*.  Si vous donnez à cette variable une valeur différente de `0`, chaque instance de cet *object* se déplacera automatiquement dans la direction définie par la variable `direction` (par défaut `0`, soit vers la droite).

```js
x += 1;
y += 1;
```

#### Variables d'instance

Une *variable d'instance* est une variable associée à une *instance* d'un *object*. Elle peut être accédée ou être modifiée depuis n'importe quelle évènement de l'instance. Elle s'affiche en violet dans l'éditeur de *GameMaker Studio 2*. Pour éviter les erreurs, on la définit et on l'initialise généralement dans l'évènement `Create` d'un *object*.

- Créez une variable d'instance dans l'évènement `Create` en lui affectant une valeur. Vous pouvez ensuite y accéder ou la modifier depuis n'importe quel autre évènement de l'instance. 

```js
depart_x = 10;
arrivee_x = 20;
```

#### Variables locales

Une variable locale est une variable utilisable uniquement dans un seul script. A la fin de l'exécution du script, la variable est détruite. Elle s'affiche en jaune dans l'éditeur de *GameMaker Studio 2*.

- Créez une variable locale en la faisant précéder du mot clé `var`.

```js
var longueur = arrivee_x - depart_x;
```

#### Variables globales

Une variable globale est une variable accessible depuis l'ensemble des scripts du jeu. Elle s'affiche en rose dans l'éditeur de *GameMaker Studio 2*.

- Créez une variable globale en ajoutant une sous variable à la variable prédéfinie `global`.

```js
global.meilleur_score = 100;
```

### Macros

La directive `#macro` vous permet de définir une constante symbolique associée à une valeur. Cette constante peut alors être utilisée à la place de la valeur.

```js
#macro FRAME_RATE 60
```

**Conseil :** Créez un script appelé `MACROS` et définissez vos constantes symboliques dans ce script. En faisant ainsi, toutes les constantes seront accessibles dans tous vos scripts.

### Tableaux

Utilisez un indice entre des crochets pour accéder aux éléments d'un tableau. Le premier élément est à l'indice `0`.

```js
tableau[0] = valeur;
```

Utilisez une liste d'indices séparés par une virgule pour manipuler un tableau à plusieurs dimensions.

```js
tableau_deux_dimensions[0, 0] = valeur;
```

### Énumérations

Les énumérations sont globales. Utilisez le mot clé `enum` suivi du nom de l'énumération et listez vos constantes séparées par une virgule dans des accolades.

```js
enum nom_enum {
    CONSTANTE_1,
    CONSTANTE_2,
    CONSTANTE_3,
    CONSTANTE_4
}
```

Chaque constante est associée à un entier. Par défaut, une constante prend la valeur entière de la constante précédente plus un. Par défaut, la première constante prend la valeur zéro. Vous pouvez affecter une valeur spécifique à une constante.

```js
enum nom_enum {
    CONSTANTE_1, // 0
    CONSTANTE_2, // 1
    CONSTANTE_3 = 10, // 10
    CONSTANTE_4 // 11
}
```

Utilisez une constante en la faisant précéder du nom de l'énumération et d'un point. Comme ce sont des constantes, vous ne pouvez pas modifier leur valeur.

```js
une_variable = nom_enum.CONSTANTE_2;
```

**Remarque :** Comme ces constantes sont des valeurs entières, vous pouvez vous en servir comme des indices de tableaux.

### Opérateurs

- `+` : s'applique sur deux nombres et donne un nombre. Calcule la somme de ses opérandes.
- `-` : s'applique sur deux nombres et donne un nombre. Calcule la différence de ses opérandes.
- `-` : appliqué sur un seul nombre et donne un nombre. Calcule l'opposé de son opérande.
- `*` : s'applique sur deux nombres et donne un nombre. Calcule le produit de ses opérandes.
- `/` : s'applique sur deux nombres et donne un nombre. Calcule la division de ses opérandes.
- `%` : s'applique sur deux nombres et donne un nombre. Calcule le reste de la division de ses opérandes.
- `<` : s'applique sur deux nombres et donne un booléen. Vrai si le premier opérande est inférieur au second opérande.
- `<=` : s'applique sur deux nombres et donne un booléen. Vrai si le premier opérande est inférieur ou égale au second opérande.
- `>` : s'applique sur deux nombres et donne un booléen. Vrai si le premier opérande est supérieur au second opérande.
- `>=` : s'applique sur deux nombres et donne un booléen. Vrai si le premier opérande est supérieur ou égal au second opérande.
- `==` : s'applique sur deux nombres et donne un booléen. Vrai si le premier opérande est égal au second opérande.
- `!=` : s'applique sur deux nombres et donne un booléen. Vrai si le premier opérande est différent du second opérande.
- `!` : donne un booléen correspondant à la négation de son opérande booléen (inverse la valeur de l'opérande).
- `&&` ou `and` : s'applique sur deux booléens et donne un booléen. Vrai si les deux opérandes sont vrais.
- `||` ou `or` : s'applique sur deux booléens et donne un booléen. Vrai si au moins un des deux opérandes est vrai.
- `^^` : s'applique sur deux booléens et donne un booléen. Vrai un seul des deux opérandes est vrai.

### Affectation simple et composée

```js
nom_de_variable = valeur;
nom_de_variable += valeur;
nom_de_variable -= valeur;
nom_de_variable *= valeur;
nom_de_varialbe /= valeur;
nom_de_variable %= valeur;
```

### Incrémentation et décrémentation

```js
nom_de_variable++;
++nom_de_variable;
nom_de_variable--;
--nom_de_variable;
```

### Instruction conditionnelle

```js
if (condition)
    // instruction
```

```js
if (condition)
{
    // instructions
}
```

```js
if (condition)
    // instruction
else
    // instruction
```

```js
if (condition)
{
    // instructions
}
else
{
    // instructions
}
```

```js
switch (valeur)
{
    case CONSTANTE_1:
        // instructions
        break;
    case CONSTANTE_2:
        // instructions
        break;
    ...
    default:
        //instructions
}
```

### Boucles

```js
while (condition)
    // instruction
```

```js
while (condition)
{
    // instructions
}
```

```js
for (var i = 0; i < valeur; i++)
    // instruction
```

```js
for (var i = 0; i < valeur; i++)
{
    // instructions
}
```

```js
repeat (nombre_de_fois)
    // instruction
```

```js
repeat (nombre_de_fois)
{
    // instructions
}
```

```js
do
{
    // instructions
} until (condition);
```

### Scripts et fonctions

Créez un script dans le dossier `Scripts` du panneau `Resources`.

```js
// script some_function
show_message('Hello');
```

Vous pouvez ensuite appeler le script par son nom comme s'il s'agissait d'une fonction depuis n'importe quel autre script.

```js
some_function();
```

Si vous avez besoin de passer des arguments, utilisez le mot clé `argument` suivi d'un nombre correspondant au numéro de l'argument (à partir de zéro).

```js
var some_local_variable = argument0;
```

Vous pouvez également définir un commentaire de documentation pour indiquer un nom plus parlant au paramètre attendu. Il s'affichera dans l'aide de *GameMaker Studio 2*.

```js
///@param name_of_parameter

var name_of_parameter = argument0;
```

## Exemple de code pour retourner un personnage avec les flèches du clavier

```js
var x_input = keyboard_check(vk_right) - keyboard_check(vk_left);
var y_input = keyboard_check(vk_down) - keyboard_check(vk_up);

if x_input == 0 and y_input == 0 {
	image_index = 0;
	image_speed = 0;
} else {
	image_speed = 0.6;
	if x_input != 0 {
		image_xscale = x_input;	
	}
}
```

## Effets de particules

Crée un effet en dessous d'une instance :

```js
effect_create_below(effet, x, y, taille, couleur);
```

Crée un effet au dessus d'une instance:

```js
effect_create_above(effet, x, y, taille, couleur);
```

- Le paramètre `effet` correspond au type d'élement graphique à utiliser en tant que particule. Peut avoir l'une des valeurs suivantes :
  - `ef_cloud`
  - `ef_ellipse`
  - `ef_explosion`
  - `ef_firework`
  - `ef_flare`
  - `ef_rain`
  - `ef_ring`
  - `ef_smoke`
  - `ef_smokeup`
  - `ef_snow`
  - `ef_spark`
  - `ef_star`
- Le paramètre `x` correspond à la position horizontale de l'effet.
- Le paramètre `y` correspond à la position verticale de l'effet.
- Le paramètre `taille` correspond à la taille des particules de l'effet. Valeur numérique comprise entre 0 et 2.
- Le paramètre `couleur` correspond à la couleur de l'effet. Une constante prédéfinie ou un code numérique spécifique à GameMaker. Utilisez le [color picker](https://chrisanselmo.com/tools/#/gm/color-picker) pour trouver la valeur.

Exemple :

```js
// dans un step event

// déclenche un effet d'explosion lorsque la souris est cliquée
if (mouse_check_button_pressed(mb_left)) {
    effect_create_above(ef_ring, mouse_x, mouse_y, 0.5, c_red);
}

// affiche une pluie en continue en haut de l'écran à une position horizontale entre 0 et 600
var totally_random = irandom_range(0, 600);
effect_create_above(ef_rain, totally_random, 0, 0, c_blue);
```

## Trouver la doc des variables prédéfinies

`GML Reference -> Instances -> Instance variables`

## Objects

### Propriétés prédéfinies d'un Object

- `x` : correspond à la position horizontale de l'Object. Lecture et écriture.
- `y` : correspond à la position verticale de l'Object. Lecture et écriture.
- `id` : correspond à l'identifiant unique de l'instance de l'Object. Lecture seule.
- `v_speed` : correspond à la vitesse horizontale de l'Object. Lecture et écriture.
- `h_speed` : correspond à la vitesse verticale de l'Object. Lecture et écriture.
- `speed` : correspond à la vitesse de l'Object sans direction. Lecture et écriture.
- `direction` : correspond à la direction de mouvement de l'Object sous forme d'angle. Lecture et écriture.
- `friction` : correspond à la force de frottement appliquée à de l'Object. Lecture et écriture.
- `gravity` : correspond à la force de gravité appliquée à l'Object. Lecture et écriture.
- `gravity_direction` : correspond à la direction de la gravité appliquée à l'Object. Lecture et écriture.

## Sprites

### Propriétés prédéfines d'un Sprite

- `image_alpha` : correspond à l'opacité du Sprite (entre 0 et 1). Lecture et écriture.
- `image_blend` : correspond à la teinte à appliquer au Sprite sous la forme d'une couleur (par défaut `c_white`). Lecture et écriture.
- `image_index` : correspond à l'indice de l'image à afficher par le Sprite. Lecture et écriture.
- `sprite_index` : correspond à l'index du Sprite définit dans l'arborescence `Resources`. Lecture et écriture.
- `x_scale` : correspond à l'échelle horizontale du Sprite (par défaut 1). Lecture et écriture.
- `y_scale` : correspond à l'échelle verticale du Sprite (par défaut 1). Lecture et écriture.
- `image_speed` : correspond à la vitesse de lecture des images composant le Sprite. Lecture et écriture.
- `image_width` : correspond à la largeur du Sprite. Lecture et écriture.
- `image_height` : correspond à la hauteur du Sprite. Lecture et écriture.
- `image_number` : correspond à ??????????????. Lecture et écriture.
- `sprite_xoffset` : correspond au décalage horizontal de l'origine du Sprite par rapport au bord gauche.
- `sprite_yoffset` : correspond au décalage vertical de l'origine du Sprite par rapport au bord supérieur.
- `bbox_left` : correspond à la position horizontale du côté gauche de la boite de collision du Sprite.
- `bbox_right` : correspond à la position horizontale du côté droit de la boite de collision du Sprite.
- `bbox_top` : correspond à la position verticale du côté supérieur de la boite de collision du Sprite.
- `bbox_bottom` : correspond à la position verticale du côté inférieur de la boite de collision du Sprite.

## Surfaces

- Créez un game object vide et définir les évènements `Create`, `Draw` et `Destroy`.
- Faites glisser le game object dans la Room de votre choix.

Dans l'évènement `Create`, créez la surface :

```js
surface = surface_create(Room_width, Room_height);
```

Dans l'évènement `Destroy`, détruisez la surface :

```js
surface_free(surface);
```

Dans l'évènement `Draw`, affichez la surface :

```js
if (surface_exists(surface))
{
    draw_surface(surface, 0, 0);
}
```

Ensuite, dans l'évènement `Draw` d'un game object, affichez ce que vous voulez :

```js
if (surface_exists(game_object_surface.surface))
{
    // où dessiner
    surface_set_target(game_object_surface.surface);
    //quoi dessiner
    draw_sprite_ext(sprite_index, image_index, x, y, x_scale, y_scale, image_angle, c_white, image_alpha);
    // réinitialiser
    surface_reset_target(game_object_surface.surface);
}
else
{
    // créer une nouvelle surface
    o_surface.surface = surface_create(Room_width, Room_height);
}
```

## Instances d'Objects

### Créer une instance

Pour créer une instance sur un calque spécifique :

```js
var instance_id = instance_create_layer(x, y, "nom_de_calque", game_object);
```
Pour créer une instance sur le calque du game object contenant ce script :

```js
var instance_id = instance_create_layer(x, y, layer, game_object);
```

Pour créer une instance sur un nouveau calque (qui n'est pas accessible) à une profondeur donnée (entre -16000 (devant) et 16000 (derrière)) :

```js
var instance_id = instance_create_depth(x, y, profondeur, game_object);
```

### Détruire une instance

```js
instance_destroy(); // détruit l'instance attachée à ce script
instance_destroy(instance_id); // détruit l'instance instance_id
instance_destroy(game_object); // détruit toutes les instances de game_object existantes dans la Room
```

### Vérifier si une instance existe

```js
if (instance_exists(instance_id))
{
    // instructions
}
```

## Contrôles

### Clavier

#### Constantes du clavier virtuel

- vk_nokey : keycode representing that no key is pressed
- vk_anykey : keycode representing that any key is pressed
- vk_left : keycode for left arrow key
- vk_right : keycode for right arrow key
- vk_up : keycode for up arrow key
- vk_down : keycode for down arrow key
- vk_enter : enter key
- vk_escape : escape key
- vk_space : space key
- vk_shift : either of the shift keys
- vk_control : either of the control keys
- vk_alt : alt key
- vk_backspace : backspace key
- vk_tab : tab key
- vk_home : home key
- vk_end : end key
- vk_delete : delete key
- vk_insert : insert key
- vk_pageup : pageup key
- vk_pagedown : pagedown key
- vk_pause : pause/break key
- vk_printscreen : printscreen/sysrq key
- vk_f1 ... vk_f12 : keycode for the function keys F1 to F12
- vk_numpad0 ... vk_numpad9 : number keys on the numeric keypad
- vk_multiply : multiply key on the numeric keypad
- vk_divide : divide key on the numeric keypad
- vk_add : add key on the numeric keypad
- vk_subtract : subtract key on the numeric keypad
- vk_decimal : decimal dot keys on the numeric keypad

#### Associer une touche à un évènement

La fonction `keyboard_set_map` vous permet d'associer une touche du clavier à une autre. Cela vous permet de combiner plusieurs touches du clavier à un seul évènement et cela vous évite de dupliquer du code. Enfin, cela évite que plusieurs évènements se déclenchent et éxécutent plusieurs fois le même code. Le premier paramètre correspond à une touche réelle du clavier (accessible via la fonction `ord` qui prend en paramètre une chaîne correspondant à une touche). Le dernier paramètre correspond à une constante associée à une touche du clavier virtuel.

```js
keyboard_set_map(ord("W"), vk_up);
```

### Convertir une direction en un nombre

```js
number = round(direction / 90);
```

ou

```js
number = round(direction / 45);
```

### Gamepads

Documentation *GameMaker* sur les gamepads : `Scripting -> GML Reference -> Controls -> Gamepad Input`.

GameMaker ne fournit pas d'évènement dédié aux gamepads. Vous devez donc gérer manuellement les contrôles dans un évènement `Step`.

La fonction `gamepad_is_connected` renvoie un booléen indiquant si un gamepad est connecté au moment de l'appel. Vous devez lui passer en paramètre l'indice (commençant à 0) d'un gamepad. C'est la première fonction à appeler avant de gérer les contrôles d'un gamepad.

```js
if (gamepad_is_connected(indice_de_gamepad))
{
    // instructions
}
```

La fonction `gamepad_axis_value` renvoie la valeur d'un axe de stick d'un gamepad. Le premier paramètre correspond à l'indice du gamepad. Le second paramètre correspond à quatre constantes prédéfinies associées à une direction d'un des deux sticks possibles (`gp_axislh` pour stick gauche direction horizontale, `gp_axislv` pour stick gauche direction verticale, `gp_axisrh` pour stick droit direction horizontale et `gp_axisrv` pour stick droit direction verticale).



```js
if (gamepad_is_connected(indice_de_gamepad))
{
    var leftStickH = gamepad_axis_value(indice_de_gamepad, gp_axislh);
    var leftStickR = gamepad_axis_value(indice_de_gamepad, gp_axislv);
    var rightStickH = gamepad_axis_value(indice_de_gamepad, gp_axisrh);
    var rightStickR = gamepad_axis_value(indice_de_gamepad, gp_axisrv);
}
```

Un stick au repos n'a jamais de valeur horizontale et verticale totalement nulle. Pour éviter de gérer ces valeurs parasites, la fonction `gamepad_set_axis_deadzone` vous permet de paramétrer la zone morte des sticks d'un gamepad. Placez-la dans un évènement `Create` et passez-lui comme argument l'indice du gamepad et une valeur limite comprise en `0` et `1` (`0.2` par exemple). Les valeurs comprises entre `0` et cette limite seront considérées comme nulles.

```js
gamepad_set_axis_deadzone(indice_de_gamepad, valeur);
```

La fonction `gamepad_button_check_pressed` renvoie un booléen indiquant si un bouton est enfoncé lors de l'appel. Elle prend en paramètre l'indice du gamepad et une constante prédéfinie correspondant à un bouton de gamepad :

- `gp_padl` correspond à la direction gauche de la croix directionnelle.
- `gp_padr` correspond à la direction droite de la croix directionnelle.
- `gp_padu` correspond à la direction haute de la croix directionnelle.
- `gp_padd` correspond à la direction basse de la croix directionnelle.
- `gp_axislh` correspond à la direction horizontale du stick gauche.
- `gp_axislv` correspond à la direction verticale du stick gauche.
- `gp_axisrh` correspond à la direction horizontale du stick droit.
- `gp_axisrv` correspond à la direction verticale du stick droit.
- `gp_stickl` correspond au clic du stick gauche.
- `gp_stickr` correspond au clic du stick droit.
- `gp_select` correspond au bouton *Select*.
- `gp_start` correspond au bouton *Start*.
- `gp_face1` correspond au bouton *A* d'une manette Xbox (bas).
- `gp_face2` correspond au bouton *B* d'une manette Xbox (droite).
- `gp_face3` correspond au bouton *X* d'une manette Xbox (gauche).
- `gp_face4` correspond au bouton *Y* d'une manette Xbox (haut).
- `gp_shoulderl` correspond au bouton *LB* d'une manette Xbox (L1).
- `gp_shoulderlb` correspond au bouton *LT* d'une manette Xbox (L2).
- `gp_shoulderr` correspond au bouton *RB* d'une manette Xbox (R1).
- `gp_shoulderrb` correspond au bouton *RT* d'une manette Xbox (R2).

```js
if (gamepad_is_connected(0))
{
    var padLeftPressed = gamepad_button_check_pressed(0, gp_padl);
    var padRightPressed = gamepad_button_check_pressed(0, gp_padr);
    var padUpPressed = gamepad_button_check_pressed(0, gp_padu);
    var padDownPressed = gamepad_button_check_pressed(0, gp_padd);
    var leftStickHorizontalPressed = gamepad_button_check_pressed(0, gp_axislh);
    var leftStickVerticalPressed = gamepad_button_check_pressed(0, gp_axislv);
    var rightStickHorizontalPressed = gamepad_button_check_pressed(0, gp_axisrh);
    var rightStickVerticalPressed = gamepad_button_check_pressed(0, gp_axisrv);
    var leftStickClicked = gamepad_button_check_pressed(0, gp_stickl);
    var rightStickClicked = gamepad_button_check_pressed(0, gp_stickr);
    var selectPressed = gamepad_button_check_pressed(0, gp_select);
    var startPressed = gamepad_button_check_pressed(0, gp_start);
    var buttonAPressed = gamepad_button_check_pressed(0, gp_face1);
    var buttonBPressed = gamepad_button_check_pressed(0, gp_face2);
    var buttonXPressed = gamepad_button_check_pressed(0, gp_face3);
    var buttonYPressed = gamepad_button_check_pressed(0, gp_face4);
    var buttonLbPressed = gamepad_button_check_pressed(0, gp_shoulderl);
    var buttonLtPressed = gamepad_button_check_pressed(0, gp_shoulderlb);
    var buttonRbPressed = gamepad_button_check_pressed(0, gp_shoulderr);
    var buttonRtPressed = gamepad_button_check_pressed(0, gp_shoulderrb);
}
```

Pour combiner la gestion du gamepad avec une gestion du clavier, vous pouvez simuler l'appui d'une touche du clavier avec la fonction `keyboard_key_press`.

```js
if (buttonAPressed)
{
    keyboard_key_press(vk_space);
    keyboard_key_release(vk_space);
}
```

**Attention !** Cette fonction simule l'appui d'une touche de manière permanente. Pensez à appeler aussitôt la fonction `keyboard_key_release` pour simuler le relâchement de la touche.

## Afficher un message dans une boîte de dialogue

La fonction `show_message` affiche une chaîne passée en paramètre dans une boîte de dialogue. Utiliser la fonction `string` pour convertir une valeur en chaîne.

```js
show_message(string(valeur));
```

## Timers

A chaque game object sont associées 12 alarmes qui servent de timer. Vous pouvez accéder à ces alarmes grâce à la variable prédéfinie `alarm` qui est un tableau. Chaque frame, la valeur contenue dans chaque case de ce tableau diminue de `1`. Lorsque la valeur d'une case atteint `0`, l'évènement `alarm[x]` se déclenche et exécute le script que vous avez associé à cet évènement.

Par exemple, vous pouvez définir un timer de `60` frames dans l'évènement `Create` dans la première case du tableau `alarm` associé à un game object.

```js
alarm[0] = 60;
```

Lorsque 60 frames sont passées, l'évènement `alarm[0]` se déclenche. Définissez des instructions à exécuter dans cet évènement. Par exemple, faites apparaître un ennemi.

```js
instance_create_layer(irandom_range(0, Room_width), irandom_range(0, Room_height), "Instances", ennemi);
```

Si vous souhaitez relancer le timer, redéfinissez dans l'évènement `alarm[0]` une nouvelle valeur.

```js
alarm[0] = 120;
```

Si vous souhaitez déclencher l'évènement `alarm[0]` manuellement, donnez-lui la valeur `1` pour que le timer se déclenche à nouveau à la frame suivante.

```js
alarm[0] = 1;
```

### Générer une instance

La fonction `instance_create_layer` vous permet de créer une nouvelle instance d'un game object sur un calque particulier. Elle prend en argument la position x et y, le nom d'un calque de la Room active (sous forme de chaîne) et le nom du game object à instancier.

```js
instance_create_layer(x, y, "nom_de_calque", nom_game_object);
```

**Remarque :** Le calque du game object peut être directement accédé via la variable prédéfinie `layer`.

```js
instance_create_layer(x, y, layer, nom_game_object);
```

### Détruire une instance

La fonction `instance_destroy` vous permet de détruire une instance existante d'un game object. Sans argument, elle détruit l'instance du game object associée à ce script.

```js
instance_destroy(); // détruit l'instance du game object possédant ce script
```

Elle peut également prendre l'id d'une instance particulière à détruire.

```js
instance_destroy(id_instance);
```

Enfin, elle peut également prendre le nom d'un game object. Dans ce cas, toutes les instances de ce game object sont détruites.

```js
instance_destroy(nom_game_object);
```

## Nombres aléatoires

Par défaut, GameMaker génère des nombres aléatoire avec la même graine (*seed*). Cela produit à chaque exécution du jeu la même suite de valeurs. Pour réellement générer des suites de nombres aléatoires, appelez la fonction `randomize` avant d'utiliser les fonctions suivantes.

```js
randomize();
```

La fonction `random` sans argument génère un nombre à virgule compris entre 0 et 1.

```js
random_number = random(); // génère un nombre entre 0 et 1
```

La fonction `random` avec un argument génère un nombre à virgule compris entre 0 et le paramètre.

```js
random_number = random(20); // génère un nombre entre 0 et 20
```

La fonction `irandom` avec un argument entier génère un nombre entier compris entre 0 et le paramètre.

```js
random_number = irandom(20); // génère un nombre entre 0 et 20
```

La fonction `irandom_range` prend deux entiers en arguments et génère un nombre entier compris entre le premier argument et le second.

```js
random_number = irandom_range(10, 20); // génère un nombre entre 10 et 20
```

## Rooms

### Dimensions d'une Room

Les variables prédéfinies `Room_width` et `Room_height` vous permettent de connaître les dimensions de la Room en cours.

```js
random_x = irandom_range(0, Room_width);
random_y = irandom_range(0, Room_height);
```

### Ajouter du code à une Room

Ouvrez la Room à éditer. Dans le panneau `Properties`, cliquez sur le bouton `Creation Code` pour ouvrir le script associé à une Room. Vous pouvez par exemple utilisez la fonction `audio_play_sound`.

### Organisation des Rooms

*GameMaker Studio 2* gère les Rooms en leur associant un indice selon leur organisation dans le panneau `Resources`. Dans ce panneau, vous pouvez déplacer les différentes Rooms par cliquer-glisser. Si vous cliquez-glissez une Room sur une autre, cette dernière s'illumine différemment selon la position du pointeur de la souris.

- Si le pointeur de la souris est sur la partie supérieure de la Room, la Room glissée sera placée au dessus de la Room située sous le pointeur de souris.
- Si le pointeur de la souris est sur la partie inférieure de la Room, la Room glissée sera placée au dessous de la Room située sous le pointeur de souris.
- Si le pointeur de la souris est sur la partie centrale de la Room, la Room glissée deviendra un enfant de la Room située sous le pointeur de souris. Elle héritera de ses propriétés.

- La variable prédéfinie `Room` contient l'indice associé à la Room actuelle (en cours d'exécution).
- La variable prédéfinie `Room_first` contient l'indice associé à la première Room dans la liste du panneau `Resources`.
- La variable prédéfinie `Room_last` contient l'indice associé à la dernière Room dans la liste du panneau `Resources`.

La fonction `Room_exist` prend un indice en paramètre et renvoie une booléen indiquant si une Room associé à l'indice existe bien ou non.

```js
if (Room_exist(indice_de_Room))
{
    Room_goto(indice_de_Room);
}
```

La fonction `Room_next` prend un indice de Room en paramètre et renvoie l'indice de la Room suivante ou `-1` s'il n'y a pas de Room suivante.

```js
if (Room_next(Room) != -1)
{
    Room_goto_next();
}
```

La fonction `Room_previous` prend un indice de Room en paramètre et renvoie l'indice de la Room précédente ou `-1` s'il n'y a pas de Room précédente.

```js
if (Room_previous(Room) != -1)
{
    Room_goto_previous();
}
```

La fonction `Room_restart` redémarre la Room actuelle comme si elle venait de se charger.

```js
Room_restart();
```

**Remarque :** Cette instruction prend effet une fois que l'évènement qui la contient se termine. Le script exécute donc les instructions qui suivent avant de redémarrer l'écran de jeu.

La fonction `Room_goto` vous permet de passer à une Room spécifique en passant l'indice associé à une Room en paramètre.

```js
Room_goto(indice_de_Room);
```

La fonction `Room_goto_next` vous permet de passer à la Room suivant celle actuelle dans le panneau `Resources`. Vérifiez qu'une Room existe bien après celle actuelle avant d'appeler cette fonction ou une erreur se produira.

```js
if (Room_exists(Room_next(Room)))
{
    Room_goto_next();
}
```

La fonction `Room_goto_previous` vous permet de passer à la Room précédant celle actuelle dans le panneau `Resources`. Vérifiez qu'une Room existe bien avant celle actuel avant d'appeler cette fonction ou une erreur se produira.

```js
if (Room_exists(Room_previous(Room)))
{
    Room_goto_previous();
}
```

## Evènements

### Clavier

- Les évènements de la catégorie `Key Down` se déclenchent à chaque frame si une touche est enfoncée.
- Les évènements de la catégorie `Key Pressed` se déclenchent une seule fois lorsqu'une touche est enfoncée.

## Sons et musiques

### Lecture

La fonction `audio_play_sound` vous permet de lancer la lecture d'un son ou d'une musique.  Elle renvoie un entier correspondant à un indice associé au son lu.

- Le premier paramètre est le nom du son ou de la musique à jouer.
- Le deuxième paramètre est un entier indiquant la priorité du son.
- Le dernier paramètre est un booléen indiquant si le son ou la musique doit jouer en boucle ou non.

```js
indice_de_son = audio_play_sound(nom_de_son, 1, true);
```

### Modifier le gain

La fonction `audio_sound_gain` vous permet de faire une interpolation sur le gain (l'amplitude) d'un son en lecture.

- Le premier paramètre correspond à l'indice associé à un son lu.
- Le deuxième paramètre est un nombre compris entre 0 et 1 et il correspond au nouveau gain à atteindre depuis le gain actuel.
- Le dernier paramètre indique la durée de l'interpolation en millisecondes.

```js
audio_sound_gain(indice_de_son, gain_cible, durée);
```

**Remarque :** Pour changer le gain instantannément, donnez une durée de 0.

## Déterminer le nombre d'instances d'un Object contenues dans une Room

La fonction `instance_number` vous permet de savoir combien d'instances d'un game object spécifique passé en paramètre existent dans la Room.

```js
if (instance_number(nom_game_object) > limite)
{
    // instructions
}
```

## Déterminer si une instance est située en dehors de la Room

L'évènement `Outside Room` se déclenche lorsqu'une instance sort des limites de la Room.

## L'évènement Draw

Avant toute chose, appelez la fonction `draw_self` sinon le game object ne s'affichera pas.

```js
draw_self();
```




```js
draw_set_font(font_hud);
draw_set_halign(fa_center);
draw_set_colour(c_black);
draw_text(250, 280, "Highscore: " + string(global.highscore));
```




La fonction `draw_sprite` affiche un Sprite.

- Le premier paramètre correspond au Sprite à afficher.
- Le deuxième paramètre correspond à l'indice de l'image de l'animation du Sprite à afficher. Si c'est une image fixe, passez la valeur `0`.
- Le troisième paramètre correspond à la position horizontale où afficher le Sprite.
- Le dernier paramètre correspond à la position verticale où afficher le Sprite.

```js
draw_sprite(nom_sprite, indice, position_x, position_y);
```

La fonction `draw_sprite_ext` affiche un Sprite. Elle possède plus de paramètres que la fonction précédente.

- Le premier paramètre correspond au Sprite à afficher.
- Le deuxième paramètre correspond à l'indice de l'image de l'animation du Sprite à afficher. Si c'est une image fixe, passez la valeur `0`.
- Le troisième paramètre correspond à la position horizontale où afficher le Sprite.
- Le quatrième paramètre correspond à la position verticale où afficher le Sprite.
- Le cinquième paramètre correspond à l'échelle horizontale du Sprite.
- Le sixième paramètre correspond à l'échelle verticale du Sprite.
- Le septième paramètre correspond à l'angle d'inclinaison du Sprite.
- Le huitième paramètre correspond à la teinte à attribuer au Sprite.
- Le dernier paramètre correspond à la transparence du Sprite.

```js
draw_sprite_ext(nom_sprite, indice, position_x, position_y, echelle_x, echelle_y, angle, couleur, alpha);
```

## Déplacer automatiquement une instance vers un point

La fonction `move_towards_point` (à placer dans un évènement `Create` par exemple) déplace automatiquement une instance vers un point.

- Le premier paramètre correspond à la position horizontale du point vers lequel doit se diriger l'instance.
- Le deuxième paramètre correspond à la position verticale du point vers lequel doit se diriger l'instance.
- Le dernier paramètre correspond à la vitesse à laquelle doit se déplacer l'instance.

```js
move_towards_point(position_x, position_y, vitesse);
```

## Barre de vie

La fonction `draw_healthbar` affiche une barre de vie. Elle doit être utilisée dans les évènements `Draw`.

- Le premier paramètre correspond à la position gauche du rectangle de la barre de vie.
- Le deuxième paramètre correspond à la position haute du rectangle de la barre de vie.
- Le troisième paramètre correspond à la position droite du rectangle de la barre de vie.
- Le quatrième paramètre correspond à la position basse du rectangle de la barre de vie.
- Le cinquième paramètre correspond à la quantité de vie (de 0 à 100).
- Le sixième paramètre correspond à la couleur arrière.
- Le spetième paramètre correspond à la couleur de la valeur minimale.
- Le huitième paramètre correspond à la couleur de la valeur maximale.
- Le neuvième paramètre correspond à la direction d'ancrage de la barre de vie.
  - `0` indique que la barre de vie est alignée à gauche.
  - `1` indique que la barre de vie est alignée à droite.
  - `2` indique que la barre de vie est alignée en haut.
  - `3` indique que la barre de vie est alignée en bas.
- Le dixième paramètre définit si la couleur arrière doit être visible (`true`) ou si la barre de vie doit être transparente (`false`).
- Le onzième paramètre définit si une bordure noire de un pixel d'épaisseur doit être visible (`true`) ou non (`false`).

```js
var pourcent_vie = (vie_actuelle / vie_max) * 100;
draw_healthbar(
    position_gauche,
    position_haute,
    position_droite,
    position_basse,
    pourcent_vie,
    couleur_arrière,
    couleur_valeur_minimale,
    couleur_valeur_maximale,
    direction_ancrage,
    couleur_arrière_visible,
    couleur_bordure_visible
    );
```

## Easing

La fonction `lerp` vous permet d'effectuer une interpolation linéaire entre deux valeurs. Le premier paramètre est la valeur minimale. Le deuxième paramètre est la valeur maximale. Le troisième paramètre est une nombre compris entre 0 et 1. Si cette valeur est 0, la fonction renvoie la valeur minimale. Si cette valeur est 1, la fonction renvoie la valeur maximale. Si c'est une valeur quelconque, la fonction renvoie une valeur proportionnelle relative à la valeur minimale et la valeur maximale.

Utiliser cette fonction pour déplacer une élément vers un point permet de faire ralentir progressivement l'objet à mesure qu'il se rapproche de l'objectif.

```js
x = lerp(x, objectif_x, 0.1)
y = lerp(y, objectif_y, 0.1)
```



```js
#define Default_Ease_Algorithms
/*
* TERMS OF USE - EASING EQUATIONS
* Open source under the BSD License.
* Copyright (c)2001 Robert Penner
* All rights reserved.
* Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:
* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
* Neither the name of the author nor the names of contributors may be used to endorse or promote products derived from this software without specific prior written permission.
* THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
*/

ease-linear #define EaseLinear
/// EaseLinear(inputvalue,outputmin,outputmax,inputmax)

return argument2 * argument0 / argument3 + argument1;


ease-inquad #define EaseInQuad
/// EaseInQuad(inputvalue,outputmin,outputmax,inputmax)

argument0 /= argument3;
return argument2 * argument0 * argument0 + argument1;


ease-outquad #define EaseOutQuad
/// EaseOutQuad(inputvalue,outputmin,outputmax,inputmax)

argument0 /= argument3;
return -argument2 * argument0 * (argument0 - 2) + argument1;


ease-inoutquad #define EaseInOutQuad
/// EaseInOutQuad(inputvalue,outputmin,outputmax,inputmax)

argument0 /= argument3 * 0.5;

if (argument0 < 1)
{
    return argument2 * 0.5 * argument0 * argument0 + argument1;
}

return argument2 * -0.5 * (--argument0 * (argument0 - 2) - 1) + argument1;


ease-incubic #define EaseInCubic
/// EaseInCubic(inputvalue,outputmin,outputmax,inputmax)

return argument2 * power(argument0/argument3, 3) + argument1;


ease-outcubic #define EaseOutCubic
/// EaseOutCubic(inputvalue,outputmin,outputmax,inputmax)

return argument2 * (power(argument0/argument3 - 1, 3) + 1) + argument1;


ease-inoutcubic #define EaseInOutCubic
/// EaseInOutCubic(inputvalue,outputmin,outputmax,inputmax)

argument0 /= argument3 * 0.5;

if (argument0 < 1)
{
   return argument2 * 0.5 * power(argument0, 3) + argument1;
}

return argument2 * 0.5 * (power(argument0 - 2, 3) + 2) + argument1;


ease-inquart #define EaseInQuart
/// EaseInQuart(inputvalue,outputmin,outputmax,inputmax)

return argument2 * power(argument0 / argument3, 4) + argument1;


ease-outquart #define EaseOutQuart
/// EaseOutQuart(inputvalue,outputmin,outputmax,inputmax)

return -argument2 * (power(argument0 / argument3 - 1, 4) - 1) + argument1;


ease-inoutquart #define EaseInOutQuart
/// EaseInOutQuart(inputvalue,outputmin,outputmax,inputmax)

argument0 /= argument3 * 0.5;

if (argument0 < 1) 
{
    return argument2 * 0.5 * power(argument0, 4) + argument1;
}

return argument2 * -0.5 * (power(argument0 - 2, 4) - 2) + argument1;


ease-inquint #define EaseInQuint
/// EaseInQuint(inputvalue,outputmin,outputmax,inputmax)

return argument2 * power(argument0 / argument3, 5) + argument1;


ease-outquint #define EaseOutQuint
/// EaseOutQuint(inputvalue,outputmin,outputmax,inputmax)

return argument2 * (power(argument0 / argument3 - 1, 5) + 1) + argument1;


ease-inoutquint #define EaseInOutQuint
/// EaseInOutQuint(inputvalue,outputmin,outputmax,inputmax)

argument0 /= argument3 * 0.5;

if (argument0 < 1)
{
    return argument2 * 0.5 * power(argument0, 5) + argument1;
}

return argument2 * 0.5 * (power(argument0 - 2, 5) + 2) + argument1;


ease-insine #define EaseInSine
/// EaseInSine(inputvalue,outputmin,outputmax,inputmax)

return argument2 * (1 - cos(argument0 / argument3 * (pi / 2))) + argument1;


ease-outsine #define EaseOutSine
/// EaseOutSine(inputvalue,outputmin,outputmax,inputmax)

return argument2 * sin(argument0 / argument3 * (pi / 2)) + argument1;


ease-inoutsine #define EaseInOutSine
/// EaseInOutSine(inputvalue,outputmin,outputmax,inputmax)

return argument2 * 0.5 * (1 - cos(pi * argument0 / argument3)) + argument1;


ease-incirc #define EaseInCirc
/// EaseInCirc(inputvalue,outputmin,outputmax,inputmax)
// This is a really radical curve... haha hidden programmer joke.

argument0 /= argument3;
return argument2 * (1 - sqrt(1 - argument0 * argument0)) + argument1;


ease-outcirc #define EaseOutCirc
/// EaseOutCirc(inputvalue,outputmin,outputmax,inputmax)

argument0 = argument0 / argument3 - 1;
return argument2 * sqrt(1 - argument0 * argument0) + argument1;


ease-inoutcirc #define EaseInOutCirc
/// EaseInOutCirc(inputvalue,outputmin,outputmax,inputmax)

argument0 /= argument3 * 0.5;

if (argument0 < 1)
{
    return argument2 * 0.5 * (1 - sqrt(1 - argument0 * argument0)) + argument1;
}

argument0 -= 2;
return argument2 * 0.5 * (sqrt(1 - argument0 * argument0) + 1) + argument1;


ease-inexpo #define EaseInExpo
/// EaseInExpo(inputvalue,outputmin,outputmax,inputmax)

return argument2 * power(2, 10 * (argument0 / argument3 - 1)) + argument1;


ease-outexpo #define EaseOutExpo
/// EaseOutExpo(inputvalue,outputmin,outputmax,inputmax)

return argument2 * (-power(2, -10 * argument0 / argument3) + 1) + argument1;


ease-inoutexpo #define EaseInOutExpo
/// EaseInOutExpo(inputvalue,outputmin,outputmax,inputmax)

argument0 /= argument3 * 0.5;

if (argument0 < 1) 
{
    return argument2 * 0.5 * power(2, 10 * --argument0) + argument1;
}

return argument2 * 0.5 * (-power(2, -10 * --argument0) + 2) + argument1;


ease-inelastic #define EaseInElastic
/// EaseInElastic(inputvalue,outputmin,outputmax,inputmax)

var _s = 1.70158;
var _p = 0;
var _a = argument2;

if (argument0 == 0 || _a == 0) 
{
    return argument1; 
}

argument0 /= argument3;

if (argument0 == 1) 
{
    return argument1+argument2; 
}

if (_p == 0) 
{
    _p = argument3*0.3;
}

if (_a < abs(argument2)) 
{ 
    _a = argument2; 
    _s = _p*0.25; 
}
else
{
    _s = _p / (2 * pi) * arcsin (argument2 / _a);
}

return -(_a * power(2,10 * (--argument0)) * sin((argument0 * argument3 - _s) * (2 * pi) / _p)) + argument1;


ease-outelastic #define EaseOutElastic
/// EaseOutElastic(inputvalue,outputmin,outputmax,inputmax)

var _s = 1.70158;
var _p = 0;
var _a = argument2;

if (argument0 == 0 || _a == 0)
{
    return argument1;
}

argument0 /= argument3;

if (argument0 == 1)
{
    return argument1 + argument2;
}

if (_p == 0)
{
    _p = argument3 * 0.3;
}

if (_a < abs(argument2)) 
{ 
    _a = argument2;
    _s = _p * 0.25; 
}
else 
{
    _s = _p / (2 * pi) * arcsin (argument2 / _a);
}

return _a * power(2, -10 * argument0) * sin((argument0 * argument3 - _s) * (2 * pi) / _p ) + argument2 + argument1;


ease-inoutelastic #define EaseInOutElastic
/// EaseInOutElastic(inputvalue,outputmin,outputmax,inputmax)

var _s = 1.70158;
var _p = 0;
var _a = argument2;

if (argument0 == 0 || _a == 0)
{
    return argument1;
}

argument0 /= argument3*0.5;

if (argument0 == 2)
{
    return argument1+argument2; 
}

if (_p == 0)
{
    _p = argument3 * (0.3 * 1.5);
}

if (_a < abs(argument2)) 
{ 
    _a = argument2; 
    _s = _p * 0.25; 
}
else
{
    _s = _p / (2 * pi) * arcsin (argument2 / _a);
}

if (argument0 < 1)
{
    return -0.5 * (_a * power(2, 10 * (--argument0)) * sin((argument0 * argument3 - _s) * (2 * pi) / _p)) + argument1;
}

return _a * power(2, -10 * (--argument0)) * sin((argument0 * argument3 - _s) * (2 * pi) / _p) * 0.5 + argument2 + argument1;


ease-inback #define EaseInBack
/// EaseInBack(inputvalue,outputmin,outputmax,inputmax)

var _s = 1.70158;

argument0 /= argument3;
return argument2 * argument0 * argument0 * ((_s + 1) * argument0 - _s) + argument1;


ease-outback #define EaseOutBack
/// EaseOutBack(inputvalue,outputmin,outputmax,inputmax)

var _s = 1.70158;

argument0 = argument0/argument3 - 1;
return argument2 * (argument0 * argument0 * ((_s + 1) * argument0 + _s) + 1) + argument1;


ease-inoutback #define EaseInOutBack
/// EaseInOutBack(inputvalue,outputmin,outputmax,inputmax)

var _s = 1.70158;

argument0 = argument0/argument3*2

if (argument0 < 1)
{
    _s *= 1.525;
    return argument2 * 0.5 * (argument0 * argument0 * ((_s + 1) * argument0 - _s)) + argument1;
}

argument0 -= 2;
_s *= 1.525

return argument2 * 0.5 * (argument0 * argument0 * ((_s + 1) * argument0 + _s) + 2) + argument1;


ease-inbounce #define EaseInBounce
/// EaseInBounce(inputvalue,outputmin,outputmax,inputmax)

return argument2 - EaseOutBounce(argument3 - argument0, 0, argument2, argument3) + argument1


ease-outbounce #define EaseOutBounce
/// EaseOutBounce(inputvalue,outputmin,outputmax,inputmax)

argument0 /= argument3;

if (argument0 < 1/2.75)
{
    return argument2 * 7.5625 * argument0 * argument0 + argument1;
}
else
if (argument0 < 2/2.75)
{
    argument0 -= 1.5/2.75;
    return argument2 * (7.5625 * argument0 * argument0 + 0.75) + argument1;
}
else
if (argument0 < 2.5/2.75)
{
    argument0 -= 2.25/2.75;
    return argument2 * (7.5625 * argument0 * argument0 + 0.9375) + argument1;
}
else
{
    argument0 -= 2.625/2.75;
    return argument2 * (7.5625 * argument0 * argument0 + 0.984375) + argument1;
}


ease-inoutbounce #define EaseInOutBounce
/// EaseInOutBounce(inputvalue,outputmin,outputmax,inputmax)

if (argument0 < argument3*0.5) 
{
    return (EaseInBounce(argument0*2, 0, argument2, argument3)*0.5 + argument1);
}

return (EaseOutBounce(argument0*2 - argument3, 0, argument2, argument3)*0.5 + argument2*0.5 + argument1);
```

Voici un exemple d'animation utilisant l'*Easing* :

That’s the end of all the easing functions I have. Let’s look at how you can use that in an example.

This is the code to animate this button bounce.
GameMaker Easing Animation

Dans l'évènement `Create` :

```js
/// animation engine 

buttonwidth = 120 
buttonheight = 26

frame = 0 
framesmax[1] = 20 // heading towards the button
framesmax[2] = 20 // squishing against the button 
framesmax[3] = 20 // going back 
framesmax[4] = 20 // bouncing out

part = 1 // what part of the animation we are on 

distancebounce = 30
strechamountx = 0.4
strechamounty = 1.0
```

Dans l'évènement `Step` :

```js
frame++;
if (frame >= framesmax[part]) { // this part of the animation has finished move onto the next one
    part++;
    frame = 0;
    if (part >= array_length_1d(framesmax)) { // the whole animation has finished so reset the whole thing
        part = 1;
    }
}
```

Dans l'évènement `Draw` :

```js
switch (part)
{
    case 1: 
        var distance = distancebounce-EaseInCubic(frame, 0, distancebounce, framesmax[part])
        draw_sprite_ext(spr_buttonselect, 0,x-distance,y,1,1,0,c_white,1)
    break;
    case 2: 
        var strechh = 1-(EaseOutCubic(frame,1,100,framesmax[part])/100)*strechamountx
        var strechv = EaseOutCubic(frame,1,strechamounty/2,framesmax[part])
        draw_sprite_ext(spr_buttonselect, 0,x,y,strechh,strechv,0,c_white,1)
    break;
    case 3: 
        var strechh = (1-(EaseOutCubic(framesmax[part]-frame,1,100,framesmax[part])/100)*strechamountx)
        var strechv = EaseOutCubic(framesmax[part]-frame,1,strechamounty/2,framesmax[part])
        draw_sprite_ext(spr_buttonselect, 0,x,y,strechh,strechv,0,c_white,1)
    break;
    case 4: 
        var distance = EaseOutCubic(frame, 0, distancebounce, framesmax[part])
        draw_sprite_ext(spr_buttonselect, 0,x-distance,y,1,1,0,c_white,1)
    break;
}
```

## Fichiers

### Fichiers INI

*GameMaker Studio 2* vous permet d'utiliser des fichiers *INI* pour sauvegarder des petites données (maximum 64 Ko). Si vous souhaitez utiliser des caractères accentués ou créez manuellement ce fichier et sauvegardez-le au format *UTF-8* car *GameMaker Studio 2* sauvegarde par défaut un fichier *INI* inexistant au format *ANSI*.

Un fichier *INI* est simplement un fichier texte avec la structure suivante :

```
[section1]
cle1 = valeur1
cle2 = valeur2
[section2]
cle3 = valeur3
cle4 = valeur4
...
```

Pour résumer, une valeur est associée à une clé dans une section particulière.

#### Ouvrir un fichier *INI*

La fonction `ini_open` ouvre un fichier *INI*. Elle prend une chaîne de caractère correspondant au nom du fichier *INI*. Si le fichier n'existe pas et que vous utilisez des fonctions d'écriture, le fichier sera créé. Un seul fichier *INI* peut être ouvert à la fois.

```js
ini_open("nom_de_fichier.ini");
```

Vous pouvez également ouvrir un fichier *INI* virtuel en passant à la fonction `ini_open_from_string` une chaîne avec une structure identique au contenu d'un fichier *INI*.

```js
ini_open_from_string("[section]\ncle1 = valeur1\ncle2 = valeur\n");
```

**Attention !** Pensez toujours à refermer un fichier ouvert.

#### Lecture d'un fichier *INI*

Utilisez la fonction `ini_read_real` pour accéder à un nombre que vous pouvez affecter à une variable.

```js
nombre = ini_read_real("section", "cle", nombre_par_defaut);
```

Utilisez la fonction `ini_read_string` pour accéder à une chaîne que vous pouvez affecter à une variable.

```js
chaine = ini_read_string("section", "cle", "defaut");
```

#### Ecriture dans un fichier *INI*

Utilisez la fonction `ini_write_real` pour sauvegarder un nombre.

```js
ini_write_real("section", "cle", nombre_a_sauvegarder);
```

Utilisez la fonction `ini_write_string` pour sauvegarder une chaîne.

```js
ini_write_string("section", "cle", "chaine_a_sauvegarder");
```

#### Fermeture d'un fichier *INI*

Une fois que vous n'avez plus besoin d'utiliser le fichier *INI*, n'oubliez pas de le refermer avec la fonction `ini_close`. Si vous avez sauvegardé des données, elles sont réellement sauvegardées dans le fichier lors de la fermeture.

```js
ini_close();
```

## Divers

### Redémarrer le jeu

La fonction `game_restart` vous permet de redémarrer votre jeu.

```js
game_restart();
```

### Quitter le jeu

La fonction `game_end` vous permet de quitter le jeu.

```js
if keyboard_check_pressed(vk_escape)
{
    game_end();
}
```
