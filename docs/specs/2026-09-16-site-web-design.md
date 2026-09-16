# Conception du site web — Guillaume Lejeune, Ostéopathe D.O.

Date : 16 septembre 2026 — Statut : validé en brainstorm, en relecture.

## 1. Objectif

Convertir les visiteurs en rendez-vous et améliorer la visibilité locale sur Google, dans le cadre du plan [strategie/plan-action.md](../../strategie/plan-action.md) (passer de 6 à 20 patients par semaine).

- **Action principale** : prise de rendez-vous sur Doctolib.
- **Actions secondaires** : appel (07 61 77 40 82), e-mail (lejeuneguillaume5@gmail.com). Pas de formulaire de contact.
- **Positionnement** : ostéopathe des sportifs (musculation, cross-training, gymnastique, bras de fer) et des douleurs du quotidien liées au travail de bureau, ouvert à tous.
- **Ton** : vouvoiement, sobre, précis, rassurant. Aucune promesse de guérison.

Le site est construit de zéro ; l'ancien site Google Sites sert uniquement de source d'informations.

## 2. Technique

| Choix | Décision |
|---|---|
| Générateur | Astro, sortie 100 % statique |
| Emplacement du code | [site/](../../site/) |
| Domaine | lejeune-osteopathe.fr (conservé) |
| Hébergement | Hébergeur existant, à retrouver ; déploiement traité après la construction |
| Cookies / traceurs | Aucun, donc pas de bandeau cookies |
| Polices | Hébergées localement (pas d'appel aux serveurs Google) |
| Mises à jour | Réalisées par Claude à la demande, versionnées sur GitHub |

### Organisation du code

- **Données centralisées** : un fichier unique contient nom, titre, téléphone, e-mail, lien Doctolib, et pour chaque lieu : adresse, horaires, tarifs, accès. Toutes les pages lisent ce fichier.
- **Composants réutilisables** : en-tête, bouton RDV, barre RDV mobile, carte de lieu, tableau d'horaires, liste d'avis, FAQ, pied de page.
- **Contenus textuels** (avis, FAQ, « qui suis-je ») séparés des composants pour être modifiés sans toucher la mise en page.

## 3. Pages

| URL | Page |
|---|---|
| `/` | Accueil |
| `/osteopathe-vendenheim` | Cabinet de Vendenheim |
| `/osteopathe-schiltigheim` | Cabinet de Schiltigheim (Gym Concordia) |
| `/mentions-legales` | Mentions légales |

### 3.1 Accueil — structure « Confiance directe »

1. **En-tête** : logo GL, liens vers les deux lieux, bouton « Prendre RDV ».
2. **Bandeau principal** : « Ostéopathe D.O. à Vendenheim et Schiltigheim », accroche sportifs et douleurs du quotidien, portrait, note et nombre d'avis Google, bouton Doctolib, téléphone.
3. **Ce que je soigne** : sportifs ; douleurs du bureau (cervicales, dos, épaules, poignets) ; tous publics.
4. **Qui suis-je** : pratique de la musculation et du bras de fer ; passion pour l'anatomie et la biomécanique du sportif ; collaboration avec Jérémie Agius à Plobsheim (juillet 2025 – juillet 2026) ; partenariats actuels avec Gym Concordia et Bras de Fer Sportif Strasbourg ; mention discrète « formation à l'école OSCAR (Strasbourg) ».
5. **Les deux lieux** : carte par lieu (adresse, jours, tarif) avec lien vers sa page.
6. **Avis** : 6 avis Google sélectionnés (prénom + initiale, texte exact) et lien « Voir tous les avis sur Google ».
7. **FAQ** : remboursement mutuelle ; déroulement d'une séance ; quand consulter et fréquence ; moyens de paiement (carte bancaire, espèces, chèque).
8. **Contact** : Doctolib, téléphone, e-mail.
9. **Pied de page** : coordonnées des deux lieux, lien mentions légales, mention « L'ostéopathie ne se substitue pas à un avis médical ».

### 3.2 Page Vendenheim

- Centre de santé pluridisciplinaire, 19 rue de la Forêt, 67550 Vendenheim.
- Horaires : mardi, mercredi, jeudi 14h–20h ; vendredi 7h30–13h30.
- Tarif : 65 € la séance d'1 h.
- Accès : parking privé, accès PMR, bus C9, proche gare SNCF.
- Lien « Itinéraire » vers Google Maps (pas de carte intégrée, pour n'appeler aucun service tiers), bouton RDV.

### 3.3 Page Schiltigheim

- Gym Concordia (salle du Moulin), 22 rue du Tribunal, 67300 Schiltigheim. Nom et logo du club affichés (accord confirmé).
- Horaires : lundi 15h–19h ; mardi 8h–13h ; jeudi 8h–13h.
- Tarifs : 50 € (adhérents Concordia) / 60 € (non-adhérents), séance de 50 min.
- Accès, lien « Itinéraire » vers Google Maps, bouton RDV.

### 3.4 Mentions légales

Éditeur (nom, adresse professionnelle, contact), SIRET, numéro RPPS/ADELI, hébergeur, propriété intellectuelle, absence de cookies.

### 3.5 Mobile

Barre fixe en bas d'écran avec « Prendre RDV » et « Appeler ».

## 4. Identité visuelle

### Couleurs

| Rôle | Couleur |
|---|---|
| Logo, titres | Bleu nuit `#14284B` |
| Boutons, liens | Bleu acier `#2F6FDB` |
| Fond | Blanc cassé `#F7F8FA` |
| Texte | Gris ardoise `#5B6475` |

Toutes les combinaisons texte/fond respectent le contraste WCAG AA. Les couleurs sont définies une seule fois comme variables et jamais saisies en dur ailleurs.

### Logo

Monogramme « GL » en ligne continue, trait fin, évoquant un axe articulaire, accompagné de « Guillaume Lejeune — Ostéopathe D.O. ». Déclinaisons : logo complet (SVG), favicon, image carrée pour Google et Doctolib.

### Style

Sobre et aéré, typographie de titre nette et affirmée, typographie de texte très lisible, quelques traits fins et schémas biomécaniques. Pas d'effets décoratifs gratuits. Le skill hallmark sert de garde-fou contre le rendu générique.

### Photos

Disponible : portrait professionnel. Emplacements prévus pour : salle de soin de Vendenheim, entrée du centre de santé, salle de soin à Concordia. Photos compressées, avec texte alternatif. Aucune photo de patient sans autorisation écrite.

## 5. SEO local

- Balises titre et description uniques par page, ciblant « ostéopathe Vendenheim », « ostéopathe Schiltigheim », « ostéopathe sportif Strasbourg nord ».
- Un seul titre principal par page, hiérarchie de titres propre.
- Données structurées : praticien et deux établissements (adresse, horaires, téléphone, tarifs, lien Doctolib).
- Nom, adresses et téléphone strictement identiques au site, aux fiches Google et à Doctolib.
- Plan du site (sitemap), fichier robots, URL canoniques, aperçus de partage (Open Graph).
- Audit avec le skill claude-seo avant la mise en ligne.

## 6. Qualité et vérifications

Avant validation par Guillaume, puis avant la mise en ligne :

- Construction du site sans erreur ni avertissement.
- Aucun lien cassé.
- Validation HTML.
- Affichage vérifié sur mobile et ordinateur.
- Lighthouse ≥ 95 en performance, accessibilité, bonnes pratiques et SEO.
- Relecture de tous les textes (orthographe, exactitude des horaires et tarifs).

Guillaume valide le site sur son PC avant toute mise en ligne.

## 7. Informations à fournir avant la mise en ligne

- [ ] Lien exact du profil Doctolib (et, si disponible, lien direct par lieu).
- [ ] 6 avis Google sélectionnés.
- [ ] Liens des deux fiches Google (pour « voir tous les avis » et l'itinéraire).
- [ ] Note moyenne Google à afficher.
- [ ] Numéro SIRET.
- [ ] Numéro RPPS/ADELI.
- [ ] Portrait professionnel (fichier).
- [ ] Logo de Gym Concordia (fichier).
- [ ] Hébergeur (identifiants à ne jamais mettre dans le dépôt).

Des emplacements visibles marquent ces éléments tant qu'ils ne sont pas fournis ; le site ne peut pas être mis en ligne tant qu'il en reste.

## 8. Hors périmètre (pour plus tard)

Articles de blog, pages par public, version anglaise, formulaire de contact, prise de rendez-vous intégrée, déploiement.
