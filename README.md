# 🧵 Filament Tracker

Application web (PWA) mono-fichier pour gérer ton inventaire de filaments d'impression 3D. Bilingue (FR/EN), fonctionne hors ligne, synchronisation cloud optionnelle et intégration Klipper/Moonraker.

**Version actuelle : v2.0.0**

---

## ✨ Fonctionnalités

### Inventaire
- Ajout, édition, duplication et suppression de filaments
- Champs détaillés : couleur (avec opacité), marque, type, code, températures (buse/lit), séchage, vitesse, nombre de rouleaux, statut, avis, notes, photo
- Détection automatique des doublons (fusion des quantités)
- Valeurs par défaut de température pré-remplies selon le type de filament
- Statut cliquable (Neuf / En cours / Terminé) et système d'avis (👎 👍 ⭐)
- Contrôle de quantité et pourcentage restant avec estimation du poids en grammes

### Vues et organisation
- Deux modes d'affichage : liste détaillée et grille compacte
- Recherche instantanée avec bouton d'effacement
- Filtres multi-sélection : marque, type, statut, % restant
- Tri : teinte, couleur, marque, type, % restant, rouleaux, statut, avis
- Sélection multiple pour export/suppression par lot

### Projets
- Création de plusieurs projets nommés
- Sélection de filaments par projet (mode 📌)
- Vue palette avec pastilles de couleur et détails complets
- Sur grand écran : inventaire et projet affichés côte à côte
- Sur mobile : navigation par onglets

### Import / Export
- Import de fichiers `.json` et `.csv`
- Export CSV (inventaire complet ou sélection)
- Export JSON de la sélection

### Synchronisation cloud (optionnelle)
- Données synchronisées via [JSONBin.io](https://jsonbin.io) (gratuit)
- Images hébergées via [ImgBB](https://api.imgbb.com) (gratuit)
- Sync automatique à chaque sauvegarde + au chargement
- Push/Pull manuel disponible

### Intégration Klipper / Moonraker
- Connexion à ton imprimante pour déduire automatiquement le filament utilisé
- Match automatique via le nom du profil slicer (OrcaSlicer)
- Mise à jour du % restant après chaque impression terminée

### Autres
- Application installable (PWA) sur mobile et desktop
- Fonctionne hors ligne
- Bilingue français / anglais (toggle ou paramètre URL `?lang=fr`)
- Sauvegarde automatique dans le navigateur

---

## 🚀 Installation

C'est un fichier HTML unique — aucune dépendance, aucune installation de serveur nécessaire.

1. Télécharge le fichier `index.html`
2. Héberge-le sur n'importe quel hébergement statique (GitHub Pages, Netlify, Vercel, etc.) ou ouvre-le directement dans ton navigateur
3. C'est prêt !

Pour l'installer comme application, ouvre le site puis utilise « Installer » depuis ton navigateur (bannière automatique ou menu du navigateur).

---

## ⚙️ Configuration

### Synchronisation cloud

1. Clique sur le bouton ☁️
2. Crée un compte gratuit sur [jsonbin.io](https://jsonbin.io) et copie ta clé API (X-Master-Key)
3. Laisse le champ Bin ID vide et clique « Créer un Bin & Activer »
4. (Optionnel) Ajoute une clé [ImgBB](https://api.imgbb.com) pour synchroniser aussi les images
5. Sur tes autres appareils, entre la même clé API + le Bin ID affiché

### Intégration Klipper

1. Ajoute le nom du profil slicer (ex : `Bambu Lab PLA Matte @Snapmaker`) dans le champ « Profil Slicer » de chaque filament
2. Clique sur le bouton 🖨️ et entre l'URL de ton Moonraker (ex : `http://192.168.1.50:7125`)
3. Autorise ton domaine dans `cors_domains` de `moonraker.conf`
4. Clique « Sauvegarder & Tester »

Le filament utilisé sera déduit automatiquement du % restant après chaque impression complétée.

---

## 🎨 Utilisation des projets

**Grand écran :** L'inventaire et le projet s'affichent côte à côte. Clique directement sur les filaments pour les ajouter au projet actif.

**Mobile :** Utilise les onglets 📦 Inventaire / 🎨 Projet. Active le bouton 📌 dans l'inventaire pour sélectionner des filaments.

- Crée plusieurs projets avec « + Nouveau »
- Renomme chaque projet directement dans le champ texte
- Change de projet actif en cliquant sur sa pastille

---

## 🛠️ Stack technique

- HTML / CSS / JavaScript vanilla (aucun framework)
- Fichier unique, ~2500 lignes
- Stockage : `localStorage` (données + images en cache local)
- PWA avec service worker et manifest intégrés
- APIs externes optionnelles : JSONBin.io, ImgBB, Moonraker

---

## 📝 Notes

- Les données sont stockées localement dans ton navigateur. Sans synchronisation cloud, elles ne sont pas partagées entre appareils.
- La synchronisation cloud et Klipper sont entièrement optionnelles.
- Pour changer la version affichée, modifie la variable `APP_VERSION` en haut du script.

---

*Développé pour la communauté de l'impression 3D 🖨️*
