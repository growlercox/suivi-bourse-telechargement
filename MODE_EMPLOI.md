# Suivi Bourse : mode d'emploi

Suivi Bourse rassemble tous tes placements (PEA, PEA-PME, compte-titres, assurance-vie, PER, crypto…) au même endroit, sur ton ordinateur. Ce guide t'accompagne de la première ouverture jusqu'aux fonctions avancées. Rien n'est envoyé sur internet, à part le téléchargement des cours de bourse.

## 1. Installer et ouvrir le logiciel

1. Télécharge **`SuiviBourse-Setup.exe`** depuis la page des téléchargements, double-clique dessus et suis l'assistant. Il peut créer une icône sur le Bureau.
2. Si Windows affiche « Windows a protégé votre ordinateur », clique sur **Informations complémentaires**, puis **Exécuter quand même** (le programme n'est pas signé numériquement, ce qui est normal pour un logiciel gratuit).
3. Au premier lancement, le logiciel est vide : tu vas créer tes enveloppes.

Il existe aussi une version **sans installation** (`SuiviBourse.exe`) : tu la lances directement par double-clic.

**Tes données** sont dans un fichier sur ton ordinateur (dossier `%APPDATA%\SuiviBourse`). Tu peux l'ouvrir par le menu **Outils › Ouvrir le dossier des données**. Désinstaller le logiciel ne les supprime pas.

## 2. Comprendre l'écran

- **À gauche :** la liste de tes enveloppes, avec en haut la **Vue globale** (toutes les enveloppes additionnées). Les boutons en dessous servent à créer, modifier, supprimer une enveloppe ou corriger son solde d'espèces.
- **En haut :** le nom de l'enveloppe choisie, les boutons **Thème**, **Actualiser les cours** et **+ Opération**, puis six cartes d'indicateurs (voir section 8).
- **Les onglets :** Évolution, Positions, Opérations, Répartition, Benchmark, Actifs vendus et Listes (voir section 9).
- **En bas à droite :** la date et l'heure des derniers cours téléchargés.

## 3. Créer une enveloppe

Clique sur **+ Nouvelle enveloppe** (en bas de la liste à gauche) et renseigne :

- **Nom :** par exemple « PEA Boursorama » ou « AV Generali ».
- **Type :** PEA, PEA-PME, CTO, Assurance-vie, PER, Crypto, ou Livret / autre. Tu peux aussi taper ton propre type.
- **Suivre aussi l'argent versé / retiré :** c'est le choix le plus important, à faire dès le départ.

**Quel mode choisir ?**

| Mode | Quand le choisir | Ce que tu saisis |
|---|---|---|
| **Sans suivi des espèces** (case décochée, conseillé pour débuter) | Tu veux juste suivre tes achats et tes ventes. | Achats, ventes, dividendes. Le calcul du rendement part de ces mouvements. |
| **Avec suivi des espèces** (case cochée) | Tu veux suivre l'argent que tu mets sur le compte et ce qu'il te reste en liquidités. | En plus : versements et retraits. Les liquidités comptent dans la valeur de l'enveloppe. |

Le mode se choisit à la création. Tu peux le changer ensuite avec **Modifier l'enveloppe**, mais il faudra alors ajuster tes opérations (par exemple ajouter les versements).

## 4. Saisir tes opérations

Clique sur **+ Opération** (en haut à droite). Choisis l'enveloppe, la date, le type d'opération, puis les informations demandées.

| Type | Ce que tu renseignes |
|---|---|
| **Achat** | L'actif, la quantité, le prix unitaire, les frais éventuels. |
| **Vente** | L'actif, la quantité vendue, le prix unitaire, les frais éventuels. |
| **Dividende / coupon** | L'actif concerné et le montant reçu. |
| **Versement** (apport d'argent) | Le montant que tu as mis sur le compte. Pour les enveloppes avec suivi des espèces. |
| **Retrait** | Le montant que tu as sorti du compte. Pour les enveloppes avec suivi des espèces. |
| **Frais** | Le montant des frais prélevés (droits de garde, frais de gestion…). |

**Créer un actif :** dans la fenêtre d'opération, clique sur **Nouvel actif…**. Tape le nom, l'ISIN ou le ticker dans la recherche : le logiciel interroge Yahoo Finance et te propose des résultats. Choisis la bonne ligne : le ticker (par exemple `AIR.PA`) et la devise se remplissent seuls.

**Actifs en devise étrangère :** si l'actif est coté en dollars, le logiciel convertit en euros avec le taux de change du jour. Si tu saisis le prix en euros alors que l'actif est coté dans une autre devise, le montant sera faussé : saisis le prix dans la devise de cotation de l'actif.

**Modifier ou supprimer :** dans l'onglet **Opérations**, sélectionne la ligne puis utilise **Modifier**, **Dupliquer** ou **Supprimer**. Dupliquer sert pour les achats réguliers (la date du jour est reprise).

## 5. Importer un historique (fichier CSV)

Si ton courtier te fournit un export de ton historique, tu peux l'importer au lieu de tout saisir : menu **Fichier › Importer un historique CSV…**.

1. Choisis le fichier, puis l'enveloppe dans laquelle importer.
2. **Associe les colonnes :** le logiciel devine la correspondance (date, type, actif, quantité, prix, frais, montant, devise). Corrige-la si besoin.
3. Si certains types d'opération ne sont pas reconnus, indique à quoi ils correspondent.
4. Si des actifs sont inconnus, le logiciel te propose de les rechercher sur Yahoo. Tu peux en ignorer certains.
5. Vérifie l'aperçu, puis valide.

**Format conseillé du fichier** (séparateur point-virgule, dates `jj/mm/aaaa`, virgule décimale) :

`Date;Type;Actif;Ticker;Quantité;Prix unitaire;Frais;Montant;Devise`

- Types reconnus : Achat, Vente, Dividende, Versement, Retrait, Frais.
- Pour un versement, un retrait, un dividende ou des frais, remplis **Montant** (et **Actif** pour un dividende).
- Pour un achat ou une vente, remplis **Quantité** et **Prix unitaire** (le montant se calcule).

**Attention aux doublons :** le logiciel ignore les lignes strictement identiques (même date, type, actif, quantité, prix, montant). Si tu as réellement deux opérations identiques le même jour, regroupe-les en une seule ligne avant d'importer, ou ajoute la seconde à la main.

**Importer plusieurs fois le même fichier** ne crée pas de doublons, pour la même raison.

## 6. Les cours de bourse

- **Actualiser les cours :** bouton en haut à droite, ou **Outils › Actualiser les cours**. Les cours viennent de Yahoo Finance.
- **Automatiquement :** **Outils › Actualisation automatique des cours** (désactivée, toutes les 30 minutes, toutes les heures, toutes les 2 heures).
- **Actifs sans ticker** (fonds d'assurance-vie, fonds en euros, certains fonds) : le logiciel ne peut pas télécharger leur cours. Saisis-le à la main avec **Outils › Mes actifs…**, puis sélectionne l'actif et **Saisir un cours…**. Tant qu'aucun cours n'est saisi, l'actif est valorisé à son prix de revient (une astérisque l'indique).
- **Fonds en euros :** saisis-les comme un actif de quantité 1, dont le prix est le montant actuel du fonds. Mets à jour ce prix quand tu reçois un nouveau relevé.
- **Cours indicatifs :** Yahoo peut avoir du retard ou se tromper, et son service peut être limité temporairement. En cas de refus, le logiciel réessaie plus tard.

## 7. Gérer tes actifs

Menu **Outils › Mes actifs…** : la liste de tous tes actifs, avec leur ticker, leur devise, leur classement et leur secteur.

- **Ajouter / Modifier :** change le nom, le ticker, la devise, le secteur.
- **Saisir un cours… :** pour un actif sans ticker (voir section 6).
- **Objectif de cours :** dans l'onglet Positions, double-clique sur la colonne « Objectif » pour saisir le cours que tu vises. Une colonne indique ensuite l'écart restant.

## 8. Lire les indicateurs

Les six cartes en haut de l'écran :

| Carte | Signification |
|---|---|
| **Valeur totale** | Ce que vaut l'enveloppe aujourd'hui : titres au dernier cours, plus les espèces si elles sont suivies. |
| **Net investi** | L'argent que tu as réellement mis, moins ce que tu as retiré. |
| **Gain total** | Valeur totale moins le net investi, en euros et en pourcentage. |
| **TRI annualisé** | Le rendement par an, qui tient compte des dates de tes versements. Il n'apparaît que lorsqu'il y a assez de recul (« pas assez de recul » sinon). |
| **Plus-value latente** | Le gain ou la perte « sur le papier » des positions encore détenues. |
| **Réalisé + dividendes** | Les plus-values encaissées sur tes ventes, plus les dividendes reçus. |

**Si le gain te paraît faux**, vérifie dans l'ordre : le cours de chaque actif (un actif valorisé « au prix de revient » signale un cours manquant), les versements et retraits oubliés, les actifs en devise étrangère, et les doublons ignorés à l'import.

## 9. Les onglets

**Évolution :** la courbe de la valeur de ton enveloppe dans le temps. Choisis la période : 1 mois, 3 mois, 6 mois, 1 an ou tout l'historique.

**Positions :** chaque actif détenu, avec ses chiffres.
- **Colonnes :** le bouton « Colonnes » choisit celles à afficher. Tu les classes dans l'ordre que tu veux en les faisant **glisser** (un trait bleu montre où elles se placeront). Les largeurs s'ajustent seules.
- **Principales colonnes :** quantité, prix de revient (PRU), cours, Montant, +/- value en euros et en pourcentage, Poids (part dans l'enveloppe, liquidités comprises), variation de la veille, objectif, écart à l'objectif, secteur.
- **Perf. 3 mois/an, Perf. 1 an, Perf. 5 ans/an :** les performances du cours (hors dividendes). La première est la tendance des 3 derniers mois **transposée sur un an**, pour la comparer aux autres. Les flèches et les couleurs indiquent si la période récente fait mieux (⇑ ↗) ou moins bien (↘ ⇓) que la tendance sur 5 ans, ou à peu près pareil (→).

**Opérations :** l'historique complet de l'enveloppe, que tu peux modifier, dupliquer ou supprimer.

**Répartition :** trois camemberts, par classe d'actifs, par zone géographique et par secteur économique, avec le détail en tableau.
- Le classement est **automatique** : Yahoo Finance d'abord, puis, si tu le souhaites, une intelligence artificielle pour les actifs restants. Tu **valides ou corriges toujours** les propositions avant qu'elles soient enregistrées.
- Pour l'IA, ouvre **Outils › Réglages IA** et saisis une clé gratuite Gemini ou Groq. Elle est facultative : Yahoo suffit pour la plupart des actifs.
- Un fonds diversifié peut être réparti sur plusieurs secteurs ou zones.

**Benchmark :** compare ta performance à celle d'un indice ou d'un ETF de référence. Saisis son symbole Yahoo (par exemple `CW8.PA`), puis **Appliquer**. **Retirer** supprime la comparaison.

**Actifs vendus :** pour chaque vente, le prix de vente, la quantité, la valeur vendue, le cours actuel et l'**écart** : ce que la vente t'a fait gagner ou manquer par rapport au cours d'aujourd'hui. Elle montre aussi les performances de l'actif depuis.

**Listes :** des listes de surveillance pour suivre des actions et ETF que tu ne détiens pas.
1. **Nouvelle liste…**, puis **Ajouter un actif…** (même recherche que pour un actif).
2. Pour chaque actif : secteur, cours, variation de la veille, performances, objectif et écart à l'objectif (double-clic sur l'objectif pour le saisir).
3. Les cours se mettent à jour avec le reste. Ces actifs n'entrent pas dans tes totaux.
4. **Retirer de la liste** n'efface pas l'actif de tes données.

## 10. Corriger le solde des espèces

Pour les enveloppes avec suivi des espèces : si le solde affiché par le logiciel diffère de celui de ton courtier, sélectionne l'enveloppe puis clique sur **Corriger le solde espèces**. Tu indiques le solde réel, et le logiciel crée une ligne « Régularisation » qui comble l'écart, sans effet sur le rendement.

## 11. Sauvegarder, restaurer, exporter

- **Sauvegarder :** **Fichier › Sauvegarder la base…** crée une copie complète de tes données. **Fais-le régulièrement, et toujours avant une mise à jour.**
- **Restaurer :** **Fichier › Restaurer une sauvegarde…** remplace tes données par celles d'une sauvegarde.
- **Exporter :** **Fichier › Exporter les opérations (CSV)…** crée un fichier lisible dans Excel, pour une ou plusieurs enveloppes.

## 12. Mettre à jour le logiciel

Au démarrage, le logiciel regarde si une nouvelle version existe (aucune donnée personnelle n'est envoyée). Tu peux le faire à la main avec **Aide › Rechercher une mise à jour…**, ou désactiver la vérification automatique dans ce même menu.

Pour mettre à jour : **ferme** Suivi Bourse, télécharge le nouvel installateur et lance-le. Tes données sont conservées.

## 13. Apparence

Le menu **Affichage** propose le thème clair, le thème sombre, ou automatique (qui suit Windows). Le bouton **Thème** en haut à droite alterne entre les deux.

## 14. Questions fréquentes

**Le cours d'un actif n'apparaît pas.** Son ticker est vide ou incorrect : ouvre **Outils › Mes actifs…**, modifie l'actif et utilise la recherche pour trouver le bon ticker. S'il n'en existe pas (fonds d'assurance-vie), utilise **Saisir un cours…**.

**La valeur d'un actif américain semble fausse.** Vérifie la devise : le prix de tes opérations doit être dans la devise de cotation de l'actif (en dollars pour une action américaine cotée aux États-Unis).

**Le TRI affiche « pas assez de recul ».** C'est normal quand les opérations sont très récentes, ou toutes à la même date (cas d'un import sans historique).

**J'ai importé un fichier et il manque des opérations.** Les lignes strictement identiques sont ignorées (section 5). Ajoute les opérations manquantes à la main.

**Où sont mes données ?** Dans `%APPDATA%\SuiviBourse` (menu **Outils › Ouvrir le dossier des données**). Pense à les sauvegarder.

**Les cours ne se mettent plus à jour.** Yahoo Finance limite parfois les demandes. Attends un peu et réessaie. Le logiciel n'est pas en panne.

**Y a-t-il des calculs fiscaux ?** Non. Suivi Bourse est un outil de suivi personnel : il ne constitue pas un conseil en investissement, et les cours sont donnés à titre indicatif.

---

*Suivi Bourse est un logiciel gratuit. Tes retours et idées sont les bienvenus dans l'onglet Issues du dépôt de téléchargement.*
