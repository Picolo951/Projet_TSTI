# Guide : Comment renommer un fichier

## En utilisant Git (recommandé)

### Méthode 1 : Utiliser `git mv` (préserve l'historique)
```bash
git mv ancien_nom.html nouveau_nom.html
git commit -m "Renommer ancien_nom.html en nouveau_nom.html"
git push
```

### Méthode 2 : Renommer manuellement puis utiliser Git
```bash
# 1. Renommer le fichier
mv ancien_nom.html nouveau_nom.html

# 2. Ajouter les changements à Git
git add ancien_nom.html nouveau_nom.html
git commit -m "Renommer ancien_nom.html en nouveau_nom.html"
git push
```

## En utilisant l'interface GitHub

1. Naviguez vers le fichier sur GitHub
2. Cliquez sur l'icône crayon (éditer)
3. Modifiez le nom du fichier dans le champ en haut
4. Ajoutez un message de commit
5. Cliquez sur "Commit changes"

## En utilisant l'explorateur de fichiers

### Windows
```
Clic droit sur le fichier > Renommer
```

### Linux/Mac
```bash
mv ancien_nom.html nouveau_nom.html
```

## ⚠️ Important : Mettre à jour les références

Après avoir renommé un fichier, pensez à mettre à jour toutes les références dans les autres fichiers :

### Exemple : Si vous renommez `main.html` en `accueil.html`

**Fichiers à vérifier et modifier :**
- `catalogue.html` - mettre à jour les liens `<a href="./main.html">`
- `informations.html` - mettre à jour les liens
- `contact.html` - mettre à jour les liens
- `navigation-test.html` - mettre à jour les références

**Rechercher toutes les occurrences :**
```bash
grep -r "main.html" *.html
```

**Remplacer dans tous les fichiers (Linux/Mac) :**
```bash
sed -i 's/main.html/accueil.html/g' *.html
```

**Remplacer dans tous les fichiers (Windows avec PowerShell) :**
```powershell
Get-ChildItem *.html | ForEach-Object {
    (Get-Content $_.FullName) -replace 'main.html', 'accueil.html' | Set-Content $_.FullName
}
```

## Exemple concret : Ce qui a été fait dans ce projet

Dans ce projet, nous avons **créé** un nouveau fichier `index.html` qui sert de point d'entrée au site. Ce fichier redirige automatiquement vers `catalogue.html`.

### Pourquoi créer plutôt que renommer ?

- Le fichier `test.html` et `navigation-test.html` sont des fichiers de test à garder
- Le fichier `main.html` contient l'ancienne page d'accueil qui peut être utile
- Créer `index.html` permet de garder tous les fichiers existants intacts

### Structure finale du site :

```
index.html           → Point d'entrée (redirige vers catalogue)
catalogue.html       → Page principale avec les véhicules
main.html           → Ancienne page d'accueil (conservée)
informations.html   → Page À propos
contact.html        → Page Contact
test.html           → Fichier de test
navigation-test.html → Fichier de test navigation
```

## Conseils

1. **Toujours faire un backup** avant de renommer des fichiers importants
2. **Tester les liens** après avoir renommé un fichier
3. **Utiliser `git mv`** pour que Git suive le changement de nom
4. **Commiter fréquemment** pour pouvoir revenir en arrière si nécessaire
5. **Documenter les changements** dans le message de commit

## Questions fréquentes

**Q : Puis-je renommer plusieurs fichiers en même temps ?**
R : Oui, mais faites-le un par un pour mieux suivre les changements.

**Q : Que faire si j'ai cassé des liens après avoir renommé ?**
R : Utilisez `git log` pour voir l'ancien nom, puis `git revert` pour annuler le commit.

**Q : Comment voir l'historique d'un fichier renommé ?**
R : Utilisez `git log --follow nom_du_fichier.html`
