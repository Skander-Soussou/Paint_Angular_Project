# **Correction Sprint 2**

# Fonctionnalité

## Exporter le dessin /6 - 0.96

- [x] Il est possible d'exporter le dessin localement via une fenêtre d'export de fichier.
- [x] Il est possible d'ouvrir la fenêtre d'export avec le raccourci `CTRL + E`.
- [x] Une seule fenêtre modale parmi: (sauvegarder, carrousel et exporter) peut être affichée en même temps (pas de _stack_ non plus).
- [x] Les différent raccourcis ne sont pas disponibles lorsque cette fenêtre est affichée.
- [x] Il est possible d'exporter une image en format JPG.
- [x] Il est possible d'exporter une image en format PNG.
- [x] Il est possible d'appliquer un filtre à l'image exportée.
- [x] Un choix d'au moins 5 filtres _sensiblement_ différents est offert.
- [x] Les différents filtres sont clairement identifiés pour leur sélection.
- [x] Un seul filtre est appliqué à l'image exportée.
- [x] Il est possible d'entrer un nom pour le fichier exporté.
- [x] Il est possible de voir une vignette de prévisualisation de l'image à exporter.
- [x] Un bouton de confirmation doit être présent pour exporter l'image.

### Commentaires

On peut modifier l'extension de l'export de fichier en ajoutant un .ext dans le nom !

## Carrousel de dessins 7.23/8 - 0.9

- [x] Il est possible de voir les dessins sauvegardés sur un serveur via le carrousel de dessins.
- [x] Il est possible d'ouvrir la fenêtre du carrousel avec le raccourci `CTRL + G`.
- [x] Le carrousel doit présenter 3 fiches à la fois.
- [x] Le carrousel doit gérer les cas oũ moins de 3 dessins sont disponibles.
- [x] Il est possible de faire défiler le carrousel en boucle avec les touches du clavier.
- [x] Il est possible de faire défiler le carrousel en boucle avec des boutons présents dans l'interface.
- [x] Une seule fenêtre modale parmi: (sauvegarder, carrousel et exporter) peut être affichée en même temps (pas de _stack_ non plus).
- [x] Les différent raccourcis ne sont pas disponibles lorsque cette fenêtre est affichée.
- [x] Chaque fiche de dessin comporte un nom, des étiquettes (s'il y en a) et un aperçu du dessin en format réduit.
- [x] Le nom, les étiquettes et l'aperçu doivent être ceux qui ont été définis lorsque l'utilisateur les a sauvegardé.
- [x] Lors des requêtes pour charger les dessins dans la liste, un élément de chargement doit indiquer que la requête est en cours.
- [x] La liste doit être chargeable sans délai excessif.
- [x] Il est possible de filtrer les dessins par leurs étiquettes. Voir la carte **Filtrage par étiquettes**.
- [x] Il est possible de charger un dessin en cliquant sur sa fiche.
- [ ] Si un dessin choisi ne peut pas être ouvert, l'utilisateur doit être invité à choisir un autre via la même fenêtre modale.
- [x] Si un dessin présent non-vide est sur la zone de travail, l'utilisateur doit recevoir une alerte confirmant ou non vouloir abandonner ses changements.
- [x] Il est possible de supprimer un dessin à l'aide d'un bouton de suppression.
- [x] Lorsqu'un dessin est supprimé, le carrousel doit se mettre automatiquement à jour et ne doit plus contenir ce dessin .
- [ ] Si un dessin choisi ne peut pas être supprimé, l'utilisateur doit être informé de la raison et le carrousel doit être mis à jour.
- [x] Lorsqu'un dessin est sauvegardé, _au moins à_ la prochaine ouverture, le carrousel doit pouvoir afficher le nouveau dessin sauvegardé.
- [x] Les anciens paramètres d'ouverture ne sont plus visibles lors de la réouverture du carrousel (les paramètres sont remis à leur état original). _ie: pas de filtre d'activé_

### Commentaires

Si le dessin ne peut pas être ouvert, rien ne se passe. Aucun message d'erreur si la suppression échoue.
La moitié des fonctions sont testés ! 0.6

## Base de données 5.5/6 - 0.91

- [x] Il est possible de sauvegarder le nom et les tags d'un nouveau dessin sur une base de données MongoDB.
- [x] La base de données est à distance et non localement sur la machine du serveur.
- [x] Lorsqu'un dessin est supprimé par un utilisateur, la base de données est mise à jour.
- [x] Le client est capable de récupérer l'information d'un ou plusieurs dessins à partir de la base de données.
- [x] La récupération de données se fait à partir de la base de données et non des fichiers locaux.
- [x] Si la base de données contient des informations sur des dessins non-existants sur le serveur, ces dessins ne sont pas montrés à l'utilisateur.

### Commentaires

Votre route api/drawing/add ne retourne pas de réponse.
Aucun test serveur 0

## Sauvegarder le dessin sur serveur 6.28/8 - 0.78

- [x] Il est possible de sauvegarder le dessin sur un serveur via une fenêtre de sauvegarde.
- [x] Il est possible de sauvegarder le dessin en formant PNG.
- [x] Il est possible d'ouvrir la fenêtre de sauvegarde avec le raccourci `CTRL + S`.
- [x] Une seule fenêtre modale parmi: (sauvegarder, ouvrir et exporter) peut être affichée en même temps (pas de _stack_ non plus)
- [x] Les différent raccourcis ne sont pas disponibles lorsque cette fenêtre est affichée.
- [x] Il est possible d'associer un nom au dessin à sauvegarder.
- [x] Il est possible d'associer zéro ou plusieurs étiquettes au dessin.
- [x] Il est possible d'enlever les étiquettes si elles sont choisies dans la fenêtre.
- [x] Il est possible de sauvegarder des dessins avec le même nom et avec les mêmes étiquettes (cette condition simultanément ou non) dans le serveur.
- [ ] Les règles de validation pour les étiquettes sont clairement présentées dans l'interface.
- [ ] Des vérifications (client ET serveur) sont présentes pour la sauvegarde. _Vérification minimale: nom non vide et étiquettes valides_
- [ ] S'il est impossible de sauvegarder le dessin, l'utilisateur se fait mettre au courant avec un message pertinent (message d'erreur).
- [x] Un bouton de confirmation doit être présent pour sauvegarder le dessin.
- [x] La modale de sauvegarde (ou du moins le bouton de confirmation) est mise non disponbile lorsque le dessin est en pleine sauvegarde.

### Commentaires

Le champs ne montre pas une validation claire des étiquettes et je peux doubler des étiquettes (allo,allo). Aucun message d'erreur si on fait une sauvegarde sur un serveur éteint ! Aucune vérification côté serveur.

Vos tests au niveau du service sont insufisant. Un de vos deux tests vérifies si la constante est égale à une constante. 0.5 Aucun test serveur

## Filtrage par étiquettes 4.5/6 - 0.75

- [x] Il doit être possible de filtrer les dessins en utilisant des étiquettes.
- [x] Pour chaque dessin de la liste, les étiquettes, si présentes, doivent toutes être visibles (via un mécanisme de votre choix).
- [ ] Le filtrage par étiquette - Lorsque vide, tous les dessins doivent être possibles d'être chargés. _ie: pas d'étiquette, pas de filtre_.
- [x] Le filtrage par étiquette - Lorsqu'une étiquette est sélectionnée pour filtrage, seulement les dessins sur le serveur avec cette étiquette sont visibles dans le carrousel.
- [x] Le filtrage par étiquette - Lorsque mutliples étiquettes sont sélectionnées pour filtrage, seulement les dessins sur le serveur qui contiennent au moins une des étiquettes doivent être visibles dans la liste (_OU_ logique).
- [ ] Il doit être possible d'accéder à tous les dessins du carrousel, pour un critère de recherche donné.
- [x] Si aucun dessin n'est trouvable par les étiquettes sélectionnées, l'utilisateur doit en être informé.
- [x] Les anciens paramètres d'ouverture ne sont plus visibles lors de la réouverture du carrousel (les paramètres sont remis à leur état original). _ie: pas de filtre d'activé_

### Commentaires

Si on recherche sur un liste de filtre vide on a aucun dessin. Si on fait plusieurs recherche on perds des dessins.
Il manque certaine branche à tester : 0.9

## Selection

- 0.05 pas de bouton lattéral
- 0.05 manque des 8 points de controles

## Deplacement

- 0.1 ne compte pas comme une action de annuler-refaire
- 0.1 peut pas déplacer en diagonal
- 0.05 déplacement avec souris fais un déplacement non-voulu au tout début

## Guide

- 0.05 manque polygone
- 0.1 les items dans divers doit etre dans dessiner et vice-versa

## Annuler-refaire

- Vos tests devraient inclure une vérification de l'état des piles de undo et redo.

## Anciennes fonctionnalités brisées ou non réglées

- Après un redimensionnement, lorsqu'on créé un nouveau dessin la surface de dessin n'est pas remise aux dimensions initiales
- Lorsqu'on entre manuellement des couleurs ça change l'outil utilisé (par exemple si je suis sur le sceau de peinture et que j'écris '111111' on passe à rctangle)

# QA

## Qualité des classes /14

### La classe n'a qu'une responsabilitée et elle est non triviale.

**3/3**  
_Commentaires :_

### Le nom de la classe est approprié. Utilisation appropriée des suffixes ({..}Component,{..}Controller, {..}Service, etc.). Le format à utiliser est le PascalCase

**1.75/2**  
_Commentaires :_

GuideUtilsateurComponent guide-utilisateur.component.ts -> UserGuideComponent

### La classe ne comporte pas d'attributs inutiles (incluant des getter/setter inutiles). Les attributs ne représentent que des états de la classe. Un attribut utilisé seulement dans les tests ne devrait pas exister.

**1.5/3**  
_Commentaires :_

galleryIsOpen drawing.component.ts
returnCurrentTool sidebar.service.ts
filter export.component.ts
drawingService drawing.serice.ts
urldelete and urladd sont des constantes save-drawing.service.ts
set radius line.service.ts setter pour un attribut publique
set setSides pour un attribut publique polygone.service.ts

### La classe minimise l'accessibilité des membres (public/private/protected)

**x/2**  
_Commentaires :_

loadImage gallery.component.ts
previewHue, previewColor color-picker.component.ts
plusieurs attributs drawing.component.ts
plusieurs drawing.service.ts
getPixelPos, matchPixel, colorPixel et autres paint-bucket.service.ts
drawShape polygone.service.ts
verifier private pour selection-ellipse.service.ts
database.controller.ts verifier l'accessibilités des variables

### Les valeurs par défaut des attributs de la classe sont initialisés de manière consistante (soit dans le constructeur partout, soit à la définition)

**3/4**  
_Commentaires :_

Quelques endroits inconsistant

## Qualité des fonctions /13

### Les noms des fonctions sont précis et décrivent les tâches voulues. Le format à utiliser doit être uniforme dans tous les fichiers (camelCase, PascalCase, ...)

**0/2**  
_Commentaires :_
fillFlod paint-bucket.ts
rigthClick color-panel.component.ts
showPenAtt,showFeatherAtt,showSpraypaintAtt drawing-tools.component.ts showPenAttribute ,showFeatherAttribute, showSprayPaintAttribute
changefilter export.component.ts changeFilter
add et remove manque une indiquation de l'entité sur lequel l'action est appliqué save-drawing.component.ts
isCliked dans drawing.service.ts
getImage dams drawing.service.ts getImageSrc
getImage dans brush.service.ts retourne un canvas
annonceColor, getCurentColor color-selector.service.ts
getImageDatatAtPosition picker.service.ts getImageDataAtPosition
getToolBykey tools-selector.service.ts getToolByKey

### Chaque fonction n'a qu'une seule utilité, elle ne peut pas être fragmentée en plusieurs fonctions et elle est facilement lisible.

**1.25/3**  
_Commentaires :_

ngOnInit drawing.component.ts
exportAsPng et exportAsJpg ne difère que d'une seul ligne, il pourrait être la même fonction
drawShape ellipse.service.ts pourrait être scindé
paint-bucket.service.ts hexadecimalToDecimal -> parseint(hexnumber, 16)
drawShape polygone.service.ts
drawShape rectangle.service.ts
onMouseDown, onMouseUp, onKeyDown selection-rectangle.service.ts

### Les fonctions minimisent les paramètres en entrée (pas plus de trois). Utilisation d'interfaces ou de classe pour des paramètres pouvant être regroupé logiquement.

**2.75/3**  
_Commentaires :_

drawPreviewPerimeter utilise toujours un attributs de classe en parametre rectangle.service.ts

### Les fonctions sont pures lorsque possible. Les effets secondaires sont minimisés

**3/3**  
_Commentaires :_

### Tous les paramètres de fonction sont utilisés

**2/2**  
_Commentaires :_

## Exceptions /4

### Les exceptions sont claires et spécifiques (Pas d'erreurs génériques). Les messages d'erreur affichés à l'utilisateur sont compréhensible pour l'utilisateur moyen (pas de code d'erreur serveur, mais plutôt un message descriptif du genre "Un problème est survenu lors de la sauvegarde du dessin")

**1.5/2**  
_Commentaires :_

addData save-drawing.service.ts ne lance pas d'erreur

### Toute fonction doit gérer les valeurs limites de leurs paramètres

**x0.5/1**  
_Commentaires :_

draw loaded-image.ts ne vérifie pas que src n'est pas null

### Tout code asynchrone (Promise, Observable ou Event) doit être géré adéquatement.

**0/1**  
_Commentaires :_

gallery.component.ts aucune gestion des subscribe
ellipse.service.ts aucune gestion des subscribes

## Qualité générale

- #27: Les constantes varient entre variable locale, variable de classe et variable globale. Pas de fichier .env pour le url de la database
- #29: drawing.component.ts(184), export.component.ts(165)
- #30: format de constante non uniforme: save-drawing.component.ts(59), constants.ts(10-18), certain enum n'ont pas le même convention de nom (mouse-button.ts, color-type.ts, et d'autres)
- #33: color-palette.component.ts(35), undo-redo.service.ts(42)
- #35: export.component.ts(136, 143), gallery.component.ts(98, 108), color-selector.service.ts(41), paint-bucket.service.ts(70)
- #39: Un fichier dans le dossier classe s'appelle ".ts"
- #43: un peu de code commenté
- #47: no-any disabled dans database.controller pas valable le type de Promise peut-être précisé; no empty disabled dans save-drawing.service
- #48: Jamais utilisé
