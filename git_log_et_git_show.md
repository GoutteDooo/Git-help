# Différences entre git log et git show

---

## git log

- Permet de parcourir l'historique des commits d'une branche.
- Montre seulement un résumé de chaque commit, sans détail sur les modifs.

Commande :
`git log`

Options populaires :

- `git log --oneline` (histo plus court)
- `git log -p` (diffs entre chaque commit (= git show))
- `git log --graph --oneline --all` (histo graphique)

---

## git show

- Utilisé pour examiner en détail **un commit unique**.
- Affiche les **infos de bases** et les **modifs exacts** (diff) apportées par ce commit.

Commande :
`git show <commit_id>`

Autres utilisations :

- `git show` (voir les détails du dernier commit)
- `git show v1.0` (voir les détails du commit ou de l'objet nommé v1.0)

---

### Conclusion

- git show se concentre sur un unique commit
- git log se concentre sur l'historique complet des commits
- A noter qu'il y a des commandes annexes et que ce n'est pas simplement ça.
