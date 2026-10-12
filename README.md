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
