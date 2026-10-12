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
