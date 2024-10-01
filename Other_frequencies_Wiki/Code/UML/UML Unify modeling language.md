### dates: 30/09/2024
### prof: Benjamin Vitis (Naval Groupe)



# Diagramme de cas utilisation
## Définition

 - Permet de modéliser les besoins
 - Regrouper les différentes fonctionnalités attendues
 - Organiser et mettre des relations entre les différentes fonctionnalités

## Quand?

 - 90% avant la phase de conception
 - 10% pour la doc
 - Lors de l'analyse du besoin

## Composants

- Acteurs
	- représente un rôle possédé par un utilisateur ou un système (souvent représenté par un stick man et de manière général par des symbole personnalisés)
	
- cas d'utilisation
	- il s'agit de fonctionnalités spécifiques effectués par un ou plusieurs acteurs
	- cas d'utilisation représente un scénario spécifique
	- généralement représenté par des ovales
	
- association
	- Les acteurs et les cas d'utilisation sont reliés par des associations pour désigner quelle fonctionnalité est accessible à quel acteur.
	- Les associations sont représentés par des lignes entre les acteurs et les cas d'utilisation.


[[UML_CasUtilisation_TP1]]

- héritage
	- L’héritage permet à un acteur d'hériter de la liste des fonctionnalités et dont des   possibilités réalisables par un autre acteur.
	-  L’héritage est en cascade, c’est-à-dire que si un acteur C hérite d’un acteur B qui lui-même hérite d’un acteur A, alors, dans ce cas, l’acteur C pourra effectuer les mêmes actions que les acteurs B et A.
[[UML_CasUtilisation_TP2]]

- inclusion
	- L’inclusion est utilisée afin de montrer qu’un cas d’utilisation en nécessite un autre avant l'exécution de celui-ci.
	- Une inclusion est une contrainte forte, ce qui signifie que si une inclusion est placé entre le cas A et pointe sur le cas B, alors le cas A ne pourra être effectué que si le cas B est effectué avant.
	![[Inclusion.png]]

- Extension
	- L’extension permet de spécifier des cas d’utilisation avec des cas d’utilisation optionnel.
	- Attention à ne pas confondre avec l’héritage. En langage objet, on appelle aussi l’héritage « Extension »
	
			Ici, les extensions signifient qu’il sera possible
			de se connecter soit avec Compte Meta,
			son compte Google ou encore
			un compte LDAP interne
			
	![[extension.png]]
	


## Inclusion & Extension - Exemple

![[Inclusion - extension - héritage -exemple.png]]
## Inclusion – Extension – Héritage - Exemple

![[Inclusion – Extension – Héritage - Exemple.png]]

# Les étapes pour créer un diagramme de cas d’utilisation

## Etape 1 – Identification des acteurs
- Identifier l’ensemble des acteurs qui seront présents dans les cas d’utilisation.

## Etape 2 – Identification des cas d’utilisation
- Etablir une liste des cas d’utilisation. Il faut aller le plus loin possible dans le détail des cas d’utilisation.

## Etape 3 – Relier les acteurs et les cas d’utilisation
- Relier les acteurs aux cas d’utilisations auquel ils peuvent interagir en fonction de leur différents droits.

- Mettre en place de l’héritage entre les acteurs si nécessaire.
## Etape 4 – Ajouter les inclusions et extensions
- Ajouter les inclusions pour spécifier les contraintes des cas d’utilisations.
- Ajouter les extensions pour détailler et ajouter les cas d’utilisations optionnels.


[[UML_CasUtilisation_TP3]]
[[UML_CasUtilisation_TP4]]

# Diagramme de Séquence

## composant

- Ligne de vie
	- Pour chaque objet présent dans le diagramme de séquence, une ligne de vie associé.
	- La ligne de vie prendra fin lorsque l'objet terminera l'ensemble de ses interactions avec les autres objets.
	- Il est possible de personnaliser le symbole de l'objet  afin de l'objet, du sous-objet ou d'une couche particulière.
	
- Messages synchrones
	- Les objets peuvent communiquer entre eux à l'aide de messages dit synchrones.
	- Les messages sont des actions utilisateur/ Système, etc...
	- Les messages peuvent être écrit de manière détaillés comme en POO ou de manière simple
	- Fleche noire pleine
	
- Messages asynchrones
	- l'envoi d'un message asynchrone signifie que le receveur n'est pas dans l'obligation de lui répondre ou de lui répondre immédiatement
	- il est possible d'envoyer plusieurs messages asynchrones à un même objet en même temps. 
	- Il est possible d'envoyer plusieurs message asynchrone à plusieurs messages asynchrone à plusieurs objet en même temps. 
	- Fleche noire ouverte
	  
- Messages de retour
	- Ils permettent d'obtenir la réponse aux messages envoyés synchrone ou asynchrone.
	- Ils est important de noter que pour certains messages asynchrone, les réponses ne sont pas toujours nécessaire pour ne pas altérer la lisibilité du diagramme. 
	- Fleche pointillée ouverte
	
- Messages récursifs
	- il est possible pour un objet de s'autoenvoyer un message. 
	- Les messages récursifs sont utilisés pour la vérifications de données et les enregistrements ou sauvegardes de données
	
- Barres d'activations
	- Les barres d'activation indique qu'un objet est instancié/ en cours d'interaction et qu'il est prêt à communiquer avec objets. 
	- Pour que deux objets communiquent ensemble, il est nécessaire que les deux objets aient leur barre d'activation. 
	- forme de rectangle.
	- Elle doivent être obligatoirement placées sur les lignes de vie
	- il est possible 
	
[[ ]] [[UML_Diagramme_séquence_TP4]]
	  


## Les fragments

-  Les fragments sont utilisés pour utiliser des boucles, des opérateurs conditionnels ou encore des traitements parallèles durant l'interaction entre deux objets.
- Un fragment est représenté sous la forme d’un rectangle avec une étiquette en haut à gauche précisant son type.

## Les types de fragment

-  Fragment alternative -> Représente une alternative conditionnelle.
						 ![[Ex fragment 1.png]]
	 ![[Ex fragment 2.png]]
- Fragment option -> Représente une option conditionnelle.
					![[Ex fragment 4.png]]
					
		
- Fragment boucle -> Représente une boucle.
					![[Ex fragment 3.png]]


[[UML_Diagramme_séquence_TP5]]
[[UML_Diagramme_séquence_TP6]]




