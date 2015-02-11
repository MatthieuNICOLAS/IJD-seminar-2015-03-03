* Contexte du projet
	* Qu'est-ce que PLM ?
		* Outil pour apprendre la programmation
		* Vise à permettre à chacun d'avancer à son rythme, tout en laissant l'encadrant libre pour aider les étudiants.
		* Utilisé dans le cadre de la formation d'ingénieurs informaticiens à *TELECOM Nancy* depuis 2008.
	* L'existant
		* Client lourd réalisé en **Java**
		* 200 exercices, répartis parmi une quinzaine de leçons, allant des bases de la programmation à l'alunissage d'un vaisseau spatial en passant par les tours de Hanoï.
		* Plusieurs langages de programmation supportés: **Java**, **Scala** et **Python**
	 	* Outil disponible en plusieurs langues: français, anglais, italien et portugais
	* Objectifs de l'ADT
		* Amélioration de l'outil
			* Correction des bugs connus
			* Ajout de tests unitaires et mise en place d'un processus d'intégration continue
			* Refactoring du code
		* Intéresser les apprenants...
			* Proposer du contenu pédagogique...
			* ... tout en étant attrayant
		* ... les enseignants...
			* Suivre le travail de leurs étudiants
			* Adapter le contenu existant à leurs besoins...
			* ... mais aussi d'ajouter leurs propres exercices
		* ... et les chercheurs
			* Collecter les données d'utilisation de l'application
			* Détection des élèves "en difficulté"
			* Détection des erreurs communes
* Travail réalisé
	* Prise en main du projet
		* Encadrement des séances de TP utilisant l'outil à *TELECOM Nancy*
		* Correction des bugs mineurs relevés par les étudiants
		* Débuggage des exercices du **BatWorld**.
	* Refactoring de la collecte de données
		* Utilise [GitHub](http://github.com) comme base de données...
		* ...mais pertes de traces constatées
		* Correction et amélioration du code existant.
		* Réalisation d'un moissonneur permettant de parcourir le dépôt GitHub et d'en extraire des statistiques.
	* Tests et intégration continue
		* 
	* Migration vers une application WEB
		* Mise en place d'un serveur avec [Play framework](http://playframework.com).
		* Développement d'une version "librairie" de PLM.
		* Réalisation d'une interface cliente en utilisant [AngularJS](http://angularjs.org) et [Foundation](http://foundation.zurb.com/).
		* Implémentation d'un protocole de communication entre les 2 composants.
* Difficultés rencontrés, solutions proposées
* Bilan et prochains objectifs