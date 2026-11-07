# TP Git / GitHub - Emna Samchi

Dépôt : https://github.com/emnasamchi/TP_GITPYTHON

Dans ce TP, j'ai fait évoluer un seul fichier `main.py` en 4 versions (V1 à V4), en utilisant Git en local et GitHub.

## Ce que j'ai fait

J'ai créé un dossier pour le projet, je l'ai ouvert dans VS Code et j'ai créé le fichier `main.py`. J'y ai écrit le programme de la V1, qui affiche juste un message de bienvenue.

Ensuite j'ai ouvert Git Bash dans le dossier, j'ai configuré mon nom et mon email, puis j'ai initialisé le dépôt et fait mon premier commit :

```bash
git config --global user.name "Emna Samchi"
git config --global user.email "mon-email"
git init
git add main.py
git commit -m "V1 - creation du programme Python"
```

Pour la V2, j'ai modifié `main.py` pour demander le prénom à l'utilisateur avec `input()` et l'afficher dans un message. J'ai testé avec `py main.py`, puis j'ai fait un deuxième commit :

```bash
git add main.py
git commit -m "V2 - ajout du prenom utilisateur"
git log
```

J'ai ensuite créé un dépôt vide sur GitHub (sans README ni .gitignore), je l'ai relié à mon dossier local et j'ai envoyé mes commits :

```bash
git branch -M main
git remote add origin https://github.com/emnasamchi/TP_GITPYTHON.git
git push -u origin main
```

Pour la V3, j'ai modifié `main.py` directement sur GitHub (bouton crayon) pour ajouter la question sur la matière, avec le message de commit `V3 - ajout de la matiere`. Cette modification n'existait donc que sur GitHub, pas sur mon PC. Je l'ai récupérée avec :

```bash
git pull origin main
```

Pour la V4, j'ai modifié `main.py` sur mon PC pour ajouter la durée de révision (2 lignes à la fin), j'ai testé le programme, puis :

```bash
git add main.py
git commit -m "V4 - ajout de la duree de revision"
git push
```

À la fin j'ai vérifié avec `git status` (dossier propre) et `git log` (les 4 commits V1 à V4).

## Problèmes que j'ai rencontrés

**1. Le premier push a été refusé.** Git Bash affichait `Invalid username or token. Password authentication is not supported for Git operations`. GitHub n'accepte plus le mot de passe du compte pour `git push`. J'ai créé un Personal Access Token (Settings > Developer settings > Personal access tokens > Tokens classic, avec le droit `repo`) et je l'ai collé à la place du mot de passe. Le push a alors fonctionné.

**2. Mon programme ne s'affichait pas comme prévu.** Après la modification sur GitHub, `py main.py` affichait encore `{nom}` au lieu du prénom. C'était parce que mon fichier local n'avait pas été mis à jour : modifier sur GitHub ne change pas le fichier sur le PC. J'ai résolu ça avec `git pull origin main`.

## Différence entre git push et git pull

`git push` envoie mes commits du PC vers GitHub. `git pull` récupère les commits qui sont sur GitHub et les met dans mon dossier local. Dans ce TP, V1, V2 et V4 ont été faites sur le PC (push), et V3 a été faite sur GitHub (pull).

## Questions

1. **Où V3 a été créée et quelle commande la récupère ?** Sur GitHub, avec `git pull origin main`.
2. **Pourquoi `git add` avant `git commit` ?** `git add` choisit les modifications à enregistrer, et `git commit` enregistre ensuite ce qui a été ajouté.
3. **Que veut dire `origin` ?** C'est le nom du dépôt distant, ici mon dépôt GitHub.
4. **Que se passe-t-il si on fait `git pull` et que tout est déjà à jour ?** Git affiche « Already up to date » et ne change rien.

## Captures

- [ ] `git log` avec les 4 commits
- [ ] `git status` après le dernier push
.LES REPONSES AU QUESTIONS:
 1. git pull origin main
 2. git add permet d'enregistrer /git commit permet d'enregistrer les modifications
 3. Ca signifie mon dépot sur github
 4. git affiche "already up to date "
