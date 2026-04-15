# LINUX-EXPRESSIONS-REGULIERES-GREP
Expression régulières et grep
📘 Expressions Régulières & grep (Linux)
📌 Description

Ce dépôt présente une explication complète et pratique des expressions régulières (Regex) ainsi que leur utilisation avec la commande grep sous Linux.

Objectifs :

Comprendre les bases des regex
Maîtriser les différences entre ERb et ERe
Utiliser grep efficacement
Appliquer dans des cas réels (logs, fichiers système, scripts)
🧠 1. Qu’est-ce qu’une expression régulière ?

Une expression régulière (regex) est une chaîne de caractères qui permet de décrire un modèle de recherche.

👉 Utilisée pour :

Rechercher du texte
Valider des formats (email, IP, etc.)
Filtrer des données
Manipuler du texte
⚙️ 2. Types d’expressions régulières
Type	Description	Commande
ERb (basique)	Syntaxe simple	grep
ERe (étendue)	Plus puissante	grep -E
🔤 3. Caractères spéciaux (essentiels)
📌 Tableau global
Symbole	Signification	Exemple	Résultat
^	Début de ligne	^root	commence par root
$	Fin de ligne	bash$	finit par bash
.	Un caractère quelconque	c.t	cat, cut
[abc]	Un caractère parmi	b[ae]t	bat, bet
[^abc]	Exclusion	b[^a]t	bet, bit
*	0 à ∞ répétitions	lo*l	ll, lol
+	1 à ∞ (ERe)	lo+l	lol, loool
?	0 ou 1 (ERe)	colou?r	color, colour
{n}	n fois	a{3}	aaa
{n,m}	entre n et m	a{2,4}	aa à aaaa
`	`	OU logique	`chat
()	Groupement	(ab)+	abab
\<	Début mot	\<test	test, tester
\>	Fin mot	test\>	test uniquement
🔢 4. Quantificateurs (très important)
Regex	Signification
a*	0 ou plusieurs
a+	1 ou plusieurs
a?	optionnel
a{3}	exactement 3
a{2,5}	entre 2 et 5
🔀 5. Groupement et alternatives
grep -E "(chat|chien)" file.txt

👉 Trouve "chat" ou "chien"

grep -E "(ab)+" file.txt

👉 Trouve : ab, abab, ababab...

🔎 6. Commande grep
📌 Syntaxe
grep [options] "motif" fichier
📌 Options principales
Option	Description
-i	Ignore maj/min
-n	Numéro de ligne
-v	Inverse (NOT)
-c	Compte
-r	Récursif
-l	Nom fichiers
-w	Mot exact
-x	Ligne exacte
-E	Regex avancée
💻 7. Exemples pratiques
📌 Recherche simple
grep "root" /etc/passwd
📌 Ignorer casse
grep -i "alias" .bashrc
📌 Début de ligne
grep "^root" /etc/passwd
📌 Fin de ligne
grep "bash$" /etc/passwd
📌 Mot exact
grep -w "user" file.txt
📌 Exclure un mot
grep -v "nologin" /etc/passwd
📌 Recherche récursive
grep -r "password" /etc
🧪 8. Regex avancées utiles
📌 Nombre entier
grep -E "^[+-]?[0-9]+$" file.txt
📌 Adresse email (simple)
grep -E "^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-z]{2,}$" file.txt
📌 Adresse IP
grep -E "^([0-9]{1,3}\.){3}[0-9]{1,3}$" file.txt
📌 Ligne contenant 3 chiffres
grep -E "[0-9]{3}" file.txt
📂 9. Cas réel (carnet d’adresses)
📄 fichier
olivier:29:Brest
marcel:13:Gardanne
myriam:30:Nimes
🔎 Trouver lignes commençant par m
grep "^m" carnet.txt
🔎 Trouver villes finissant par "es"
grep "es$" carnet.txt
🔎 Trouver âges à 2 chiffres
grep -E ":[0-9]{2}:" carnet.txt
⚠️ 10. Pièges courants
Erreur	Explication
Oublier les guillemets	Le shell interprète
Confondre * et +	* peut être 0
Oublier -E	Regex avancée ne marche pas
Mauvais placement de ^	doit être au début
🎯 11. Bonnes pratiques
Toujours tester ses regex
Utiliser -E pour plus de puissance
Mettre les regex entre guillemets
Commencer simple, puis complexifier
🧰 12. Outils utiles
Test regex en ligne
man grep
grep --help
🚀 13. Compétences acquises

✔ Recherche avancée de texte
✔ Analyse de logs
✔ Manipulation de fichiers Linux
✔ Base solide pour scripting (Bash, Python, etc.)

📌 14. Auteur

Projet réalisé dans le cadre de formation :

Administration systèmes & réseaux
Linux / CLI
Support technique
