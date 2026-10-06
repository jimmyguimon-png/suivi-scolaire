# Suivi Scolaire

Page autonome (HTML unique) : le parent voit tous les profils, chaque élève ne voit que le sien.

## Mise en place

1. **Firebase** : créer un projet, puis *Authentication > Sign-in method* : activer **E-mail/Mot de passe**.
2. **Firestore** : créer la base, puis coller le contenu de `firestore.rules` dans l'onglet *Règles* et publier.
3. **Application web** : *Paramètres du projet > Vos applications > Web*, copier la configuration dans `firebaseConfig` en haut du script de `index.html`.
4. **GitHub Pages** : pousser `index.html` dans un dépôt, puis *Settings > Pages* (branche `main`, dossier racine).
5. **Domaine autorisé** : *Authentication > Paramètres > Domaines autorisés* : ajouter `<utilisateur>.github.io`.
6. **Compte parent** : ouvrir la page, créer son compte, puis copier son UID (*Authentication > Utilisateurs*). Dans Firestore, créer le document `family/config` avec le champ `parentUids` (tableau) contenant cet UID.
7. **Élèves** : le parent crée un profil (« + Enfant »). L'élève crée son compte ; l'écran « Compte non rattaché » affiche son identifiant, que le parent colle dans *Profil > Identifiant du compte élève*.
