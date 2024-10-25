# Git diff

- Permet d'afficher les différences entre les versions de fichiers dans un dépôt Git.
- Utile pour examiner les modifs faites dans le code avant des ajouter à la staging area ou avant de les commits.
- Permet de comparer des états différents du projet.

---

## Commandes

- `git diff`
- `git diff --cached` - Compare les modifs dans la staging area ( `--staged` fait la même chose)
- `git diff <commit_id>` - compare les modifs avec un commit précédent.
- `git diff <commit_a> <commit_b>` - compare deux commits
- `git diff branche1 branche2` - compare deux branches
- `git diff <path/vers/fichier>` - affiche les différences dans un fichier spécifique
