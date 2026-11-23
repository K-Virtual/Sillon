# Sillon, version GitHub Pages

Ta version perso de Sillon, avec les vraies pochettes et tes 50 derniers morceaux récupérés à chaque ouverture. Elle s'installe comme une appli sur ton PC et ton tel.

## 1. Mettre le site en ligne (5 min)

1. Sur github.com, crée un nouveau dépôt, par exemple `sillon`, en **public** (GitHub Pages gratuit ne marche qu'avec un dépôt public).
2. Dans le dépôt : **Add file → Upload files**, puis glisse tous les fichiers de ce dossier : `index.html`, `config.js`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`, `icon-512-maskable.png`. Clique **Commit changes**.
3. **Settings → Pages** : dans « Build and deployment », choisis **Deploy from a branch**, branche `main`, dossier `/ (root)`, puis **Save**.
4. Une ou deux minutes plus tard, ton site est en ligne à l'adresse `https://TON-PSEUDO.github.io/sillon/`.

## 2. Récupérer tes données de la version Claude

Ici, tes données restent dans le navigateur de chaque appareil.

1. Dans la version Claude : **Données → Sauvegarde (.json)**. Ça télécharge tout ton historique, comptes fusionnés compris.
2. Dans la version GitHub : **Données**, puis dépose ce fichier `.json`. Tu peux aussi redéposer tes ZIP Spotify directement.
3. À refaire sur chaque appareil où tu ouvres le site, ou alors importe le ZIP sur chacun.

## 3. Brancher Spotify (pochettes + derniers morceaux)

Spotify demande un compte **Premium** pour créer une app perso.

1. Va sur https://developer.spotify.com/dashboard et connecte-toi.
2. **Create app** : un nom (Sillon), une description, et dans **Redirect URIs** colle l'adresse **exacte** de ton site, avec le `/` final, par exemple `https://TON-PSEUDO.github.io/sillon/`. Coche **Web API**, accepte les conditions, **Save**.
3. Dans l'app, **Settings** : copie le **Client ID**.
4. Dans ton dépôt GitHub, ouvre `config.js`, clique le crayon (Edit), colle le Client ID entre les guillemets : `window.SILLON = { spotifyClientId: 'ton-client-id' };`, puis **Commit changes**.
5. Sur ton site : **Données → Connexion à Spotify → Connecter Spotify**, et accepte.

Ensuite, à chaque ouverture :
- tes 50 derniers morceaux s'ajoutent à tes stats (quand tu réimportes un export, il remplace ces écoutes-là, sans doublons) ;
- les pochettes s'affichent au fur et à mesure et restent en mémoire.

Bon à savoir : Spotify ne donne que les 50 derniers morceaux. Si t'en écoutes plus entre deux ouvertures, les plus anciens passent à la trappe jusqu'au prochain export. Le rappel mensuel est là pour ça.

## 4. Partager avec tes potes

1. Envoie-leur simplement l'adresse du site.
2. Chacun importe son propre export Spotify. Les données restent dans son navigateur : personne ne voit celles des autres, toi non plus.
3. Pour qu'un pote ait les pochettes : dans ton app Spotify, onglet **User Management**, ajoute le nom et l'adresse mail de son compte Spotify. Il n'a plus qu'à cliquer **Connecter Spotify**.
4. Spotify limite une app perso à **5 comptes** (toi compris). Au-delà, tes potes ont tout le site sauf les pochettes et les derniers morceaux. Ceux qui ont Premium peuvent aussi créer leur propre app et la brancher via « Utiliser ma propre app Spotify ».
5. Sur téléphone, le bouton **Partager** du récap envoie l'image directement sur Insta, WhatsApp, etc.

## 5. L'installer comme une appli

- **PC (Chrome ou Edge)** : l'icône d'installation à droite de la barre d'adresse.
- **Android (Chrome)** : menu ⋮ → **Ajouter à l'écran d'accueil**.
- **iPhone (Safari)** : bouton Partager → **Sur l'écran d'accueil**.

## 6. Mettre à jour

Quand tu reçois une nouvelle version, remplace seulement `index.html` dans le dépôt (Add file → Upload files, même nom). Garde ton `config.js`. Le site se met à jour à la prochaine ouverture, chez toi comme chez tes potes, et les données de chacun ne bougent pas.

## Ce qui change par rapport à la version Claude

- Pas de Claude : le jeu du pourcentage ne marche que sur les albums déjà écoutés, et il n'y a plus d'estimations de discographie.
- Pas de synchro entre appareils : chaque navigateur a ses propres données.
- Les photos d'artistes restent des visuels générés.
