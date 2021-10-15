# Supprimer une branche
git branch -D nombranche

# Créer une nouvelle branche
git checkout -b nombranche

# Mettre à jour la branche "nombranche" avec "main"
git fetch
git checkout nombranche
git rebase origin/main
git push origin nombranche --force

# Merge de la branche "nombranche" sur "main" (Pensez à mettre à jour nombranche avec main avant"
git fetch
git branch -D main # On supprime main en local
git checkout main # On récupère main du remote
git merge nombranche --ff-only # Le ff-only permet de bloquer le merge dans le cas où nombranche n'est pas correctement à jour
git push origin main # On ajoute le code de la branche nombranche

# Fusionner des commits 
git add .
git commit -m "nouveau nom"
git rebase -i HEAD~2