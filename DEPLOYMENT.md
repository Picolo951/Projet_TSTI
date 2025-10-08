# 🚀 Guide de Publication du Site Jules Ferry Car

Ce guide vous explique **comment publier votre site web** en ligne pour qu'il soit accessible à tout le monde sur Internet.

## 📋 Table des matières

1. [Publication avec GitHub Pages (Recommandé)](#1-github-pages-recommandé)
2. [Publication avec Netlify](#2-netlify)
3. [Publication avec Vercel](#3-vercel)
4. [Publication avec hébergement traditionnel](#4-hébergement-traditionnel)

---

## 1. GitHub Pages (Recommandé) ⭐

**GitHub Pages** est gratuit et parfait pour les sites statiques comme le vôtre. C'est la méthode la plus simple !

### Étapes de publication :

#### Option A : Depuis l'interface GitHub (Le plus simple)

1. **Aller dans les paramètres du repository**
   - Ouvrez votre repository sur GitHub : https://github.com/Picolo951/Projet_TSTI
   - Cliquez sur l'onglet **Settings** (Paramètres)

2. **Activer GitHub Pages**
   - Dans le menu latéral gauche, cliquez sur **Pages**
   - Sous "Source", sélectionnez :
     - Branch: `main` (ou `master`)
     - Folder: `/ (root)`
   - Cliquez sur **Save**

3. **Attendez quelques minutes**
   - GitHub va construire votre site
   - Vous verrez un message : "Your site is published at https://picolo951.github.io/Projet_TSTI/"

4. **Visitez votre site !**
   - Votre site sera accessible à l'adresse : **https://picolo951.github.io/Projet_TSTI/**
   - Partagez cette URL avec qui vous voulez !

#### Option B : Avec GitHub Actions (Automatique)

Si vous voulez un déploiement automatique à chaque modification, un workflow GitHub Actions a été préparé. Il se trouve dans `.github/workflows/deploy.yml`.

### 🔧 Résolution de problèmes

- **Le site ne s'affiche pas ?** Vérifiez que :
  - GitHub Pages est bien activé dans Settings > Pages
  - La branche sélectionnée est bien `main`
  - Attendez 2-3 minutes après l'activation

- **Les images ne s'affichent pas ?** 
  - Vérifiez que le dossier `img/` contient bien les images
  - Les chemins relatifs (`./img/...`) fonctionnent automatiquement

---

## 2. Netlify

**Netlify** offre un déploiement simple avec drag & drop et est gratuit pour les projets personnels.

### Étapes :

1. **Créer un compte**
   - Allez sur https://www.netlify.com/
   - Créez un compte gratuit

2. **Déployer votre site**
   
   **Méthode 1 : Connexion GitHub (Recommandé)**
   - Cliquez sur "New site from Git"
   - Connectez votre compte GitHub
   - Sélectionnez le repository `Projet_TSTI`
   - Build settings :
     - Build command : (laisser vide)
     - Publish directory : `.` (ou laisser vide)
   - Cliquez sur "Deploy site"

   **Méthode 2 : Drag & Drop**
   - Téléchargez tous les fichiers du projet sur votre ordinateur
   - Glissez-déposez le dossier complet sur Netlify
   - C'est fait !

3. **Personnaliser l'URL (optionnel)**
   - Dans Site settings > Domain management
   - Vous pouvez changer le sous-domaine : `votre-nom.netlify.app`

**Votre site sera disponible à :** `https://votre-site.netlify.app`

---

## 3. Vercel

**Vercel** est similaire à Netlify, très rapide et simple d'utilisation.

### Étapes :

1. **Créer un compte**
   - Allez sur https://vercel.com/
   - Inscrivez-vous avec GitHub (recommandé)

2. **Importer le projet**
   - Cliquez sur "New Project"
   - Importez `Projet_TSTI` depuis GitHub
   - Vercel détecte automatiquement qu'il s'agit d'un site statique
   - Cliquez sur "Deploy"

3. **C'est terminé !**
   - Vercel génère automatiquement une URL : `https://projet-tsti.vercel.app`
   - Chaque push sur GitHub mettra à jour le site automatiquement

---

## 4. Hébergement Traditionnel

Si vous avez un hébergement web (OVH, Ionos, etc.), vous pouvez y uploader les fichiers.

### Étapes :

1. **Préparer les fichiers**
   - Téléchargez tous les fichiers du projet
   - Assurez-vous d'avoir :
     - `index.html`
     - `catalogue.html`
     - `main.html`
     - `informations.html`
     - `contact.html`
     - `style.css`
     - Le dossier `img/` avec toutes les images

2. **Se connecter via FTP**
   - Utilisez un client FTP (FileZilla recommandé)
   - Connectez-vous avec vos identifiants d'hébergement

3. **Uploader les fichiers**
   - Uploadez tous les fichiers dans le dossier `public_html` ou `www`
   - Conservez la structure des dossiers

4. **Accéder au site**
   - Votre site sera accessible à : `https://votre-domaine.com`

---

## 🎯 Quelle méthode choisir ?

| Méthode | Difficulté | Coût | Recommandation |
|---------|-----------|------|----------------|
| **GitHub Pages** | ⭐ Très facile | Gratuit | ✅ Meilleur choix pour commencer |
| **Netlify** | ⭐⭐ Facile | Gratuit | ✅ Bon pour les projets avancés |
| **Vercel** | ⭐⭐ Facile | Gratuit | ✅ Alternative à Netlify |
| **Hébergement classique** | ⭐⭐⭐ Moyen | Payant | Pour domaine personnalisé |

---

## 📱 Structure du Site

Votre site démarre automatiquement sur le **catalogue** (`index.html` → `catalogue.html`).

Pages disponibles :
- 🏠 **Page d'accueil** : `index.html` (redirige vers catalogue)
- 🚗 **Catalogue** : `catalogue.html` (page principale)
- ℹ️ **Informations** : `informations.html`
- 📞 **Contact** : `contact.html`
- 🏠 **Ancienne page** : `main.html`

---

## ✅ Checklist avant publication

- [ ] Vérifier que tous les fichiers sont présents
- [ ] Vérifier que les images dans `/img` sont correctes
- [ ] Tester la navigation entre les pages localement
- [ ] Vérifier que `index.html` existe
- [ ] Pousser tous les changements sur GitHub

---

## 🆘 Besoin d'aide ?

Si vous rencontrez des problèmes :

1. **GitHub Pages ne fonctionne pas ?**
   - Vérifiez Settings > Pages
   - Attendez 2-3 minutes après activation
   - Vérifiez que la branche `main` est sélectionnée

2. **Les liens ne fonctionnent pas ?**
   - Vérifiez les chemins relatifs (`./`) dans le code
   - Tous les liens utilisent des chemins relatifs

3. **Les images ne s'affichent pas ?**
   - Assurez-vous que le dossier `img/` contient les images
   - Vérifiez que les noms de fichiers correspondent

---

## 🎉 Félicitations !

Une fois publié, votre site **Jules Ferry Car** sera accessible à tout le monde sur Internet !

**URL GitHub Pages** : https://picolo951.github.io/Projet_TSTI/

Partagez cette URL et votre site automobile est en ligne ! 🚗✨
