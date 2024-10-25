# Différences entre git reset et git revert

---

En premier lieu, il est bon de savoir que ces deux commandes sont deux façons de revenir en arrière dans l'historique Git.
Cependant, elles fonctionnent différemment et sont utilisées dans des situations distinctes.

---

- **git reset :** Permet de **réécrire l'historique** en supprimant des commits de l'historique de la branche actuelle. Il est particulièrement utile pour **annuler des commits locaux** qui n'ont pas encore été poussés vers un dépôt distant.

  <u>Exemple :</u> Supposons qu'on ait les commits `A -- B -- C -- D (HEAD)`  
   On peut revenir au commit B et annuler C et D en utilisant :  
   `git reset --hard B`.  
   Cela supprime C et D de l'histo.  
   **Cette action est detructive, donc attention avant de l'utiliser !**
  <br />
  <br />

- **git revert :** Permet d'**annuler un commit spécifique en créant un nouveau commit** qui applique l'inverse des modifications d'un commit donné. git revert ne réécrit pas l'historique comme git reset, mais **il ajoute plutôt un nouveau commit "d'annulation"**.

  <u>Exemple :</u> Reprenons l'exemple des commits `A -- B -- C -- D (HEAD)`  
  Nous allons annuler les changements du commit C sans supprimer C de l'histo en faisant : `git revert C`  
  Cela créera un nouveau commit après D qui inverse les modifs de C : `A -- B -- C -- D -- E (HEAD)`

**En d'autres termes,** git reset est une commande **non sécurisée**,
tandis que git revert est une commande **sécurisée**.

- Il est conseillé d'utiliser **git reset** lorsqu'on veut supprimer un/des commits locaux qui n'ont **pas encore partagés avec d'autres collaborateurs**.
- Il est conseillé d'utiliser **git revert** lorsque l'on veut annuler un commit dans une branche partagée, comme main ou master.

---

## Commandes utiles

- `git reset --soft <commit>`
  - Annule les commits, mais garde les modifications dans la zone de staging (index).
  - Utilisé pour revenir en arrière dans l’historique sans perdre les modifications et pour recommencer un nouveau commit.
- `git reset --mixed <commit>` (par défaut)
  - Annule les commits et garde les modifications dans le répertoire de travail (non indexées).
  - Utilisé pour annuler des commits tout en gardant les changements non commit pour des modifications futures.
- `git reset --hard <commit>`
  - Annule les commits et supprime les modifications dans le répertoire de travail.
  - Utilisé pour revenir à un état antérieur et supprimer définitivement les changements.

<br />
-
