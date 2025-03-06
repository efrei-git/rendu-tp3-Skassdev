Reponses TP3
Exercice 1 : Création et navigation entre branches
J'ai créé les branches feature-1 et feature-2 avec les commandes : git branch feature-1
git branch feature-2

Pour voir la liste des branches, j'ai tapé : git branch

Ensuite, je suis passé sur feature-1 avec : git checkout feature-1

J'ai modifié le fichier README.md pour ajouter "Modification dans feature-1", puis j'ai commit le changement : echo "Modification dans feature-1" >> README.md
git add README.md
git commit -m "Modification dans feature-1"

Après, je suis retourné sur main avec : git checkout main

Sur main, la modification de feature-1 n'était pas présente, c'est normal, chaque branche est indépendante.

Exercice 2 : Fusion simple
J'ai créé la branche dev et ajouté un fichier notes.txt : git checkout -b dev
echo "Contenu de dev" > notes.txt
git add notes.txt
git commit -m "Ajout du fichier notes.txt"

Puis j'ai fusionné dev dans main avec : git checkout main
git merge dev

Le fichier notes.txt est bien présent après la fusion.

Enfin, j'ai supprimé la branche dev : git branch -d dev

Exercice 3 : Gestion des conflits
Sur main, j'ai modifié la première ligne de README.md : # Projet d'exercice - Version Main

Sur la branche conflit-test, j'ai modifié la même ligne différemment : # Projet d'exercice - Version Test

Quand j'ai essayé de fusionner conflit-test dans main, un conflit est apparu. Pour résoudre le conflit, j'ai modifié README.md comme ça : # Projet d'exercice - Version Main et Test

Puis j'ai ajouté et commit le fichier résolu : git add README.md
git commit -m "Résolution du conflit"

Exercice 4 : Rebase
J'ai créé la branche feature-rebase, ajouté un fichier feature.txt et fait plusieurs commits : git checkout -b feature-rebase
echo "Contenu de feature" > feature.txt
git add feature.txt
git commit -m "Ajout de feature.txt"

En même temps, j'ai modifié README.md sur main : git checkout main
echo "Modifications dans main" >> README.md
git add README.md
git commit -m "Modifications dans main"

Puis j'ai fait un rebase de feature-rebase sur main : git checkout feature-rebase
git rebase main

J'ai vérifié l'historique des commits avec : git log --oneline

Exercice 5 : Branches et historique
J'ai créé les branches feature-a, feature-b et feature-c : git branch feature-a
git branch feature-b
git branch feature-c

Dans chaque branche, j'ai fait 2 commits avec des fichiers différents pour éviter les conflits : Dans feature-a :
echo "Contenu de feature-a" > file-a.txt
git add file-a.txt
git commit -m "Ajout de file-a.txt"

Dans feature-b :
echo "Contenu de feature-b" > file-b.txt
git add file-b.txt
git commit -m "Ajout de file-b.txt"

Dans feature-c :
echo "Contenu de feature-c" > file-c.txt
git add file-c.txt
git commit -m "Ajout de file-c.txt"

Ensuite, j'ai fusionné chaque branche dans main : git checkout main
git merge feature-a
git merge feature-b
git merge feature-c

J'ai utilisé ces commandes pour visualiser l'historique des commits : git log --all --decorate --oneline --graph
git branch -v
git branch --merged
git branch --no-merged

Commit final pour la solution du TP
J'ai créé le fichier reponses.md et y ai ajouté toutes mes réponses.

J'ai ajouté le fichier et fait un commit : git add reponses.md
git commit -m "Solution TP3"

Enfin, j'ai fait le push de toutes mes branches sur le dépôt distant : git push origin HEAD --force
git push origin conflit-test
git push origin feature-rebase
git push origin feature-a
git push origin feature-b
git push origin feature-c

