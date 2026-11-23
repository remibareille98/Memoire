# TP 3 — Passer sur GitHub : le remote

**Durée : 35 min**
**Prérequis :** le dépôt `memoire` du TP 2 et un compte GitHub.

## Objectif

Mettre le mémoire en ligne, récupérer des modifications faites ailleurs et travailler depuis un « deuxième ordinateur ».

```
        Votre ordinateur                         GitHub
  ┌──────────────────────┐   git push    ┌──────────────────┐
  │  dépôt local memoire │ ────────────► │  dépôt distant   │
  │                      │ ◄──────────── │  (origin)        │
  └──────────────────────┘   git pull    └──────────────────┘
```

---

## Partie 1 — Créer le dépôt sur GitHub (5 min)

1. Sur GitHub, créez un nouveau dépôt nommé `memoire`, en **public**.
2. **Ne cochez rien** : ni README, ni .gitignore, ni licence.
3. Copiez l'URL HTTPS du dépôt (elle se termine par `.git`).

**Question 1 :** pourquoi faut-il créer le dépôt GitHub vide ?

---

## Partie 2 — Relier le local au distant et pousser (10 min)

1. Dans votre dossier `memoire`, ajoutez le dépôt GitHub comme remote, sous le nom `origin`.
2. Vérifiez que le remote est bien enregistré.
3. Envoyez la branche `main` sur GitHub, en la liant à `origin/main`.

> **Authentification au premier push :**
> - **Windows** : une fenêtre GitHub s'ouvre. Choisissez *Sign in with your browser* et validez.
> - **Mac / Linux** : Git demande `Username` puis `Password`. Le mot de passe GitHub **ne fonctionne pas** : il faut un *token*.
>   Pour le créer : sur GitHub, photo de profil → *Settings* → *Developer settings* → *Personal access tokens* → *Tokens (classic)* → *Generate new token (classic)*. Cochez `repo`, générez, puis copiez le token et collez-le à la place du mot de passe.

4. Rafraîchissez la page GitHub : vos fichiers et vos commits sont en ligne.

**Question 2 :** à quoi sert l'option `-u` ?

---

## Partie 3 — Ignorer des fichiers : `.gitignore` (5 min)

1. Créez un fichier `notes_perso.txt` contenant `à ne jamais publier`.
2. Tapez `git status` : `brouillon.txt` et `notes_perso.txt` apparaissent.
3. Créez à la racine du dépôt un fichier `.gitignore` qui contient :

   ```
   brouillon.txt
   notes_perso.txt
   ```

4. Tapez `git status`.

**Question 3 :** quels fichiers apparaissent maintenant ? Pourquoi faut-il commiter le `.gitignore` ?

5. Commitez le `.gitignore` avec le message `Ajout du .gitignore`, puis poussez.

---

## Partie 4 — Le README (3 min)

1. Créez un fichier `README.md` :

   ```markdown
   # Mémoire de fin d'études

   **Sujet :** l'impact de l'IA sur le métier de data analyst.

   ## Contenu
   - `memoire.txt` : le mémoire
   - `bibliographie.txt` : les références
   ```

2. Commitez avec le message `Ajout du README`, puis poussez.
3. Regardez la page d'accueil du dépôt sur GitHub.

---

## Partie 5 — Votre tuteur modifie le mémoire (7 min)

1. **Sur GitHub**, ouvrez `memoire.txt` et cliquez sur le crayon (*Edit*).
2. À la fin du fichier, ajoutez la ligne :

   ```
   Remarque du tuteur : appuyer la conclusion avec des chiffres.
   ```

3. Validez avec *Commit changes*, message `Remarque du tuteur`.
4. Dans votre terminal, tapez `git status`.

**Question 4 :** Git affiche `Your branch is up to date with 'origin/main'`. Pourquoi, alors que GitHub contient un commit de plus ?

5. Récupérez les informations du dépôt distant **sans modifier vos fichiers**, puis retapez `git status`.
6. Récupérez la modification du tuteur et intégrez-la à votre branche.
7. Vérifiez le contenu de `memoire.txt`.

---

## Partie 6 — Travailler depuis un deuxième ordinateur (5 min)

On simule un deuxième ordinateur avec un deuxième dossier.

1. Sortez du dossier `memoire` (remontez d'un niveau).
2. Clonez votre dépôt GitHub dans un dossier nommé `memoire-pc2`, puis placez-vous dedans.
3. Dans `bibliographie.txt`, ajoutez :

   ```
   - Kelleher & Tierney, Data Science, 2018
   ```

4. Commitez avec le message `Ajout d'une référence depuis le PC2`, puis poussez.
5. Retournez dans le dossier `memoire` et récupérez cette modification.

**Question 5 :** avez-vous eu besoin de faire `git remote add` dans `memoire-pc2` ? Pourquoi ?

---

## Livrable

Postez dans le chat **le lien de votre dépôt GitHub**.

On doit y voir le README affiché, le `.gitignore` et le commit `Remarque du tuteur`.

---

## Bonus

- Affichez toutes les branches, locales **et** distantes.
- Sur GitHub, ouvrez l'onglet *Commits* : retrouvez-vous le même historique que `git log` ?
