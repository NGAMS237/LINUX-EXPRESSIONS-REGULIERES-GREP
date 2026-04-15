# 📘 Expressions Régulières & `grep` (Linux)

## 📌 Description
Ce projet présente une synthèse complète, claire et pratique des expressions régulières (Regex) ainsi que leur utilisation avec la commande `grep` sous Linux.

Il sert de :
- 📚 référence rapide
- 🧠 outil d’apprentissage
- 💼 preuve de compétence (portfolio IT)

---

## 🎯 Objectifs

- Comprendre les bases des expressions régulières  
- Maîtriser les différences entre ERb et ERe  
- Utiliser efficacement `grep`  
- Appliquer dans des cas réels (logs, fichiers système)  

---

## ⚙️ Types d’expressions régulières

| Type | Description | Utilisation |
|------|------------|------------|
| ERb | Expressions régulières basiques | `grep` |
| ERe | Expressions régulières étendues | `grep -E` |

---

## 🔤 Caractères spéciaux essentiels

| Symbole | Signification | Exemple | Résultat |
|--------|-------------|--------|---------|
| `^` | Début de ligne | `^root` | commence par root |
| `$` | Fin de ligne | `bash$` | finit par bash |
| `.` | N’importe quel caractère | `c.t` | cat, cut |
| `[abc]` | Un caractère parmi | `b[ae]t` | bat, bet |
| `[^abc]` | Exclusion | `b[^a]t` | bet, bit |
| `*` | 0 à ∞ répétitions | `lo*l` | ll, lol |
| `+` | 1 à ∞ (ERe) | `lo+l` | lol, loool |
| `?` | 0 ou 1 (ERe) | `colou?r` | color, colour |
| `{n}` | n fois | `a{3}` | aaa |
| `{n,m}` | entre n et m | `a{2,4}` | aa à aaaa |
| `|` | OU logique | `chat|chien` | chat ou chien |
| `()` | Groupement | `(ab)+` | abab |

---

## 🔎 Commande `grep`

### Syntaxe

```bash
grep [options] "motif" fichier
```

### Options principales

| Option | Description |
|-------|------------|
| `-i` | Ignore maj/min |
| `-n` | Numéro des lignes |
| `-v` | Exclut (NOT) |
| `-c` | Compte |
| `-r` | Recherche récursive |
| `-l` | Nom des fichiers |
| `-w` | Mot exact |
| `-x` | Ligne exacte |
| `-E` | Regex étendues |

---

## 💻 Exemples pratiques

```bash
grep "root" /etc/passwd
grep -i "alias" .bashrc
grep "^root" /etc/passwd
grep "bash$" /etc/passwd
grep -w "user" file.txt
grep -v "nologin" /etc/passwd
grep -r "password" /etc
```

---

## 🧪 Regex utiles

### Nombre entier
```bash
grep -E "^[+-]?[0-9]+$" file.txt
```

### Email
```bash
grep -E "^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-z]{2,}$" file.txt
```

### Adresse IP
```bash
grep -E "^([0-9]{1,3}\.){3}[0-9]{1,3}$" file.txt
```

---

## ⚠️ Pièges fréquents

- Oublier les guillemets  
- Confondre `*` et `+`  
- Oublier `-E`  
- Mauvais placement de `^` et `$`  

---

## ✅ Bonnes pratiques

- Tester ses regex  
- Commencer simple  
- Utiliser `-E`  
- Lire `man grep`  

---

## 🚀 Compétences développées

- Analyse de logs Linux  
- Recherche avancée  
- Automatisation Bash  
- Base cybersécurité  

---

## 📌 Auteur

Projet réalisé dans le cadre de formation en administration systèmes et réseaux.

---

## 💡 Conclusion

Les regex + `grep` sont des outils essentiels pour tout administrateur système ou technicien IT.
