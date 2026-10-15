# Carp Session — prototype iPhone

## Fonctions incluses
- Géolocalisation uniquement sur action de l'utilisateur (« Me localiser »), avec la permission iOS.
- Recherche d'un lieu par nom.
- Prévisions météo horaires Open-Meteo (température, ressenti, pluie, vent, rafales, pression, couverture nuageuse).
- Carte OpenStreetMap avec repères de postes ajoutés manuellement.
- Analyse cartographique expérimentale via Overpass/OpenStreetMap : plans d’eau, géométries de rive comme points à inspecter, quelques tags de pêche, accès et éventuelles restrictions cartographiées.
- Affichage des profondeurs uniquement si un attribut correspondant existe dans les données retournées.
- Conseils indicatifs selon saison et type de plan d'eau.
- Carnet de session enregistré dans le navigateur, avec export JSON.

## Pour l'ouvrir sur iPhone
La géolocalisation et l'installation comme application web nécessitent une adresse HTTPS. Le fichier `index.html` ouvert directement depuis Fichiers peut ne pas permettre le GPS.

1. Héberger ces fichiers sur un hébergement HTTPS (par exemple GitHub Pages ou un hébergement web statique).
2. Ouvrir l'URL dans Safari sur l'iPhone.
3. Appuyer sur Partager → Sur l'écran d'accueil.
4. Appuyer sur « Me localiser » et autoriser la position uniquement si souhaité.

## Services externes
- Open-Meteo : météo, sans clé API pour cet usage.
- OpenStreetMap : tuiles cartographiques.
- Nominatim / OpenStreetMap : recherche de lieux et adresse approximative depuis le GPS.

Une connexion Internet est nécessaire pour les données météo, les cartes et la recherche de lieux. Le carnet et les repères sont stockés localement dans le navigateur : exporte régulièrement tes données. Ne considère pas les repères ajoutés comme des spots confirmés ni les conseils météo comme une prédiction de captures.

## Limites du prototype
- Pas de comptes utilisateurs ni de synchronisation entre appareils.
- Pas de données bathymétriques garanties, ni de validation automatique des accès/droits de pêche. Les points de rive suggérés sont des hypothèses de repérage, pas des spots confirmés. Un chemin ou un lieu de pêche cartographié ne prouve pas l’autorisation de pêcher.
- Les prévisions sont limitées à la fenêtre fournie par le service météo.
- Avant publication publique, il faut ajouter des icônes PWA, une politique de confidentialité, des tests mobiles et vérifier les conditions d'utilisation des services cartographiques et de géocodage.


## Version 4 — photo du poste
- Depuis l’onglet Carte & postes, appuie sur « Prendre une photo » pour ouvrir la caméra ou choisir une image sur iPhone.
- La photo est réduite puis associée au prochain poste placé sur la carte, avec une observation facultative.
- Les photos et postes sont enregistrés localement dans le navigateur de l’appareil. L’analyse visuelle automatique par intelligence artificielle n’est pas incluse ; l’application aide à noter les indices observés, sans inventer profondeur ou présence de carpes.


## Version 5 — comparaison de plusieurs spots

- Classe les postes enregistrés sur une échelle de 0 à 100.
- Le score s’appuie sur les observations renseignées (activité de poissons, herbiers, obstacles, baie/pointe, abri et accessibilité), avec un ajustement saisonnier simple.
- Le contexte météo peut être repris depuis les données chargées, ou choisi manuellement.
- Chaque classement explique les indices retenus et les limites de l’évaluation.
- Les photos ne sont pas analysées automatiquement par une IA. La météo chargée est celle du lieu de session sélectionné et s’applique à toute la comparaison.
- Le score est une aide pratique pour comparer les notes, jamais une probabilité de capture. L’accès, le droit de pêche et la sécurité doivent toujours être vérifiés sur place.


## Version 6 — appâts et montage

Pour chaque nouveau poste, tu peux enregistrer le type d’appâts utilisés, la stratégie d’amorçage et le type/taille d’hameçon. Ces informations apparaissent dans la fiche du poste, la fenêtre du marqueur sur la carte et le classement comparatif. Elles sont enregistrées localement avec les postes et incluses dans l’export JSON. Les champs sont facultatifs.


## Version 7 — album photo des prises par poste

- Chaque poste possède son propre album de prises photographiées.
- Ajoute une photo depuis l’appareil photo ou la photothèque ; la photo est compressée avant enregistrement.
- Chaque photo peut comporter une date, un poids facultatif et des notes.
- Les photos apparaissent dans la fiche du poste et sont conservées localement dans le navigateur, avec les autres données.
- Les images prennent de la place : exporte régulièrement tes données et supprime les photos inutiles si le stockage est plein. Les données locales ne se synchronisent pas automatiquement entre appareils.


## Version 7 — album photo des prises par poste

- Chaque poste possède son propre album de prises photographiées.
- Ajoute une photo depuis l’appareil photo ou la photothèque ; la photo est compressée avant enregistrement.
- Chaque photo peut comporter une date, un poids facultatif et des notes.
- Les photos apparaissent dans la fiche du poste et sont conservées localement dans le navigateur, avec les autres données.
- Les images prennent de la place : exporte régulièrement tes données et supprime les photos inutiles si le stockage est plein. Les données locales ne se synchronisent pas automatiquement entre appareils.


## Version 8 — placement de poste corrigée

- Le clic sur la carte permet désormais de placer un poste même si le GPS ou un lieu météo n’a pas été sélectionné au préalable.
- Le GPS ou la recherche de lieu restent disponibles pour centrer la carte et obtenir la météo.
- Les marqueurs sont conservés dans la fiche de poste pour permettre de recentrer la carte sur un poste.


## Version 9 — ajout de poste fiabilisé

Le clic sur la carte affiche désormais un formulaire intégré à la page au lieu d’une fenêtre JavaScript prompt. Après avoir touché la carte, saisis un nom puis appuie sur « Enregistrer le poste ». Les informations d’appâts, amorçage, hameçon et la photo du spot sont associées au poste. Cache service worker mis à jour en v9.


## Version 10 — prise de vue dans l’aide au choix du spot

- Ajout d’un bouton « Prendre une photo pour évaluer le spot » directement dans « Aide au choix du spot ».
- La photo s’affiche dans cette section, puis peut être associée au prochain poste placé sur la carte.
- Les indices visibles doivent être confirmés manuellement ; aucune analyse automatique par IA n’est effectuée.
- Cache du service worker versionné en v10.


## Version 11 — onglet « Aide au poste »

- Ajout d’un onglet dédié « Aide au poste » dans la navigation principale.
- Regroupe la comparaison des postes, la photo d’aide au choix, la grille d’indices, l’analyse cartographique et les rappels pratiques.
- L’onglet « Carte & postes » reste dédié à la carte, à l’enregistrement des postes et à leurs informations.
- Cache du service worker mis à jour en v11 pour faciliter le chargement de la nouvelle interface.


## Version 12 — Analyse IA des photos (configuration requise)

Cette archive ajoute une interface « Analyse IA de la photo » dans l'onglet « Aide au poste » et une fonction Supabase Edge Function qui appelle l'API OpenAI. **L'analyse ne fonctionne pas tant que Supabase et le secret OpenAI ne sont pas configurés.**

### Mise en place

1. Publier le contenu de `carp_session/` à la racine du dépôt GitHub Pages, comme pour la version précédente.
2. Créer un projet sur https://supabase.com/ et activer l'authentification par e-mail/mot de passe.
3. Dans `supabase/functions/analyze-spot/index.ts`, déployer la fonction `analyze-spot` avec Supabase CLI depuis la racine de ce paquet :
   - `supabase login`
   - `supabase link --project-ref VOTRE_PROJECT_REF`
   - `supabase secrets set OPENAI_API_KEY=VOTRE_CLE_API_OPENAI`
   - `supabase functions deploy analyze-spot`
4. Conserver la vérification JWT activée. Dans Carp Session, saisir l'URL du projet Supabase et la clé publique `anon` (ou publishable) ; ne jamais saisir une clé `service_role` dans le navigateur.
5. Créer un compte utilisateur dans l'interface, puis se connecter et lancer une analyse photo. La première connexion peut nécessiter la confirmation de l'e-mail selon les paramètres Supabase.
6. Vérifier dans les paramètres d'authentification Supabase que les URL autorisées incluent l'adresse GitHub Pages du site.

### Important

- La clé `OPENAI_API_KEY` doit rester dans les secrets serveur Supabase, jamais dans les fichiers HTML ou JavaScript publics.
- Les appels à l'IA peuvent entraîner des coûts OpenAI. Configurez des limites et surveillez l'usage.
- Cette version analyse une photo à la demande, mais ne synchronise pas encore les postes ni les photos entre les membres. La base partagée des postes est une étape séparée.
- Les données locales de la version précédente restent stockées dans le navigateur si le même site et la même origine sont conservés. Faites un export de sauvegarde avant la mise à jour.
- La photo est redimensionnée côté navigateur avant envoi à l'IA. Ne transmettez que des photos que vous acceptez d'envoyer à un service en ligne.


## Version 13 — GPS et orientation automatiques des photos

- Lors de la prise d'une photo depuis le bouton dédié, l'application tente de récupérer une position GPS haute précision et la direction du compas du téléphone.
- Si le GPS est disponible, le formulaire du nouveau poste est prérempli avec les coordonnées de la photo ; elles restent modifiables avant l'enregistrement.
- Les postes conservent localement la date/heure, latitude, longitude, précision GPS et cap en degrés lorsqu'ils sont disponibles.
- La carte affiche une ligne directionnelle indicative de 80 m pour les postes dont le cap est disponible.
- Les données restent dans le stockage local de l'appareil. Le GPS et le compas dépendent des autorisations, du navigateur, du matériel et des conditions de réception ; le cap n'est pas garanti sur tous les iPhone/navigateurs.


## Correctif v17
Cette version incrémente le cache du service worker et supprime les anciens caches à l'activation afin d'éviter que l'iPhone continue à afficher une ancienne version de l'interface. Le champ « Température de l’eau » se trouve dans l’onglet « Préparer » ; il est enregistré localement avec le bouton « Enregistrer ».


Version 19 : les conseils croisés (météo, saison, photos/observations, postes, température de l’eau et carnet) sont regroupés dans l’onglet « Aide au poste ». Le bouton « Conseils » séparé a été supprimé pour éviter la dispersion.


## Version 22 — historique complet et profils de pêcheur

- Profil manuel à trois niveaux : Débutant, Intermédiaire et Expert. Le niveau sélectionné est conservé localement et adapte les conseils généraux.
- Suggestions de progression fondées sur le nombre de sessions et la qualité des comptes rendus. Carp Session ne modifie jamais le niveau sans action de l’utilisateur ; le nombre de captures seul ne définit pas l’expertise.
- Le carnet conserve le lieu, la date, la durée, les prises, le poids maximal, le poste associé, la température de l’eau et de l’air si renseignées, les appâts/montages, l’amorçage, l’hameçon, la météo observée, les notes, la saison, le type de plan d’eau et un instantané météo disponible.
- Export JSON complet et import/restauration d’une sauvegarde. L’import remplace les sessions et postes présents sur l’appareil : exporter d’abord les données actuelles.
- Les données sont conservées dans le stockage local du navigateur sur le même appareil et la même origine. Elles ne sont pas synchronisées dans le cloud. Exporter régulièrement la sauvegarde ; une suppression des données Safari ou de l’application web peut les effacer.
