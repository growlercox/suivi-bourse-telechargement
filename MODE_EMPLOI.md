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
- **Les onglets :** Évolution, Positions, Opérations, Répartition, Benchmark, Actifs vendus, Listes et Airbag (voir section 9).
- **En bas à droite :** la date et l'heure des derniers cours téléchargés.

## 3. Créer une enveloppe

Clique sur **+ Nouvelle enveloppe** (en bas de la liste à gauche) et renseigne :

- **Nom :** par exemple « PEA Boursorama » ou « AV Generali ». **Astuce :** commence le nom par le type de compte (PEA, CTO, AV, PER…) : avec le classement alphabétique (menu **Affichage**), tes enveloppes se regroupent alors proprement par type.
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

Menu **Outils › Mes actifs…** : la liste de tous tes actifs, avec leur ticker, leur devise, leur classement et leur secteur. **Recherche au clavier :** tape les premières lettres du nom d'un actif pour le retrouver (accents et majuscules ignorés) ; les lettres s'accumulent tant que tu ne fais pas de pause de plus d'une seconde et demie. Si tu as sélectionné une ligne dans Positions (ou dans Listes) avant de l'ouvrir, cet actif apparaît en tête de liste, déjà sélectionné ; sinon la liste est par ordre alphabétique.

**Doublons :** si le même actif apparaît deux fois sous des noms différents (par exemple après l'import du fichier d'un courtier), ouvre **Outils › Mes actifs…**, sélectionne les deux lignes (Ctrl + clic) puis clique sur **Fusionner des doublons…**. Tu choisis l'actif à conserver (le plus complet est présélectionné). Toutes les opérations de l'autre sont rattachées à celui que tu gardes, dans leurs enveloppes : rien n'est perdu. Les cours, le classement et l'objectif manquants sont repris. Sans sélection, le bouton propose les doublons évidents (même ticker ou même nom). Les deux actifs doivent avoir la même devise. Ensuite, vérifie dans **Opérations** qu'une même opération n'apparaît pas deux fois.

**Actualiser un seul actif :** dans **Outils › Mes actifs…**, sélectionne l'actif puis clique sur **Actualiser le cours**. Le logiciel retélécharge sur Yahoo tout l'historique de cet actif depuis ton premier achat (utile si une courbe te semble incomplète). La fenêtre se ferme et le téléchargement se déroule en arrière-plan.

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
- **Colonnes :** le bouton « Colonnes » choisit celles à afficher. Tu les classes dans l'ordre que tu veux en les faisant **glisser** (un trait bleu montre où elles se placeront). Les largeurs s'ajustent seules. Le choix est **mémorisé par enveloppe** : ouvre une enveloppe, règle ses colonnes avec « Colonnes », et elle les gardera. Une enveloppe que tu n'as jamais réglée, comme la vue globale, utilise le réglage général (celui de la vue globale). Le bouton **« Revenir au réglage général »**, dans la boîte « Colonnes » d'une enveloppe réglée, efface son réglage propre.
- **Principales colonnes :** quantité, prix de revient (PRU), cours, Montant, +/- value en euros et en pourcentage, Poids (part dans l'enveloppe, liquidités comprises), variation de la veille, objectif, écart à l'objectif, secteur.
- **Perf. 3 mois/an, Perf. 1 an, Perf. 3 ans/an, Perf. 5 ans/an :** les performances du cours (hors dividendes), annualisées pour pouvoir les comparer. La première est la tendance des 3 derniers mois **transposée sur un an**. Les flèches et les couleurs indiquent si la période récente fait mieux (⇑ ↗) ou moins bien (↘ ⇓) que la tendance longue, ou à peu près pareil (→). La tendance longue est celle sur **5 ans** ; pour un actif qui a moins de 5 ans mais plus de 3, c'est celle sur **3 ans**. **Pastilles :** devant « Perf. 3 mois/an » ou « Perf. 1 an » (dans Positions et dans Listes), une pastille **🟢** signale une colonne qui vient de passer au vert (↗ ⇑) alors que la veille elle était rouge ou neutre ; une pastille **🟠** signale une colonne qui passe de ↗ (vert) à ⇑ (vert fort, au moins 20 points au-dessus de la tendance longue). La comparaison se fait avec la clôture précédente et l'infobulle donne la valeur de la veille. Les pastilles disparaissent à la séance suivante si la situation change. **Résumé :** sous le titre de la fenêtre, une ligne « Pastilles du jour » liste les actifs concernés (positions de toutes les enveloppes et listes de suivi), avec la colonne. **Filtre :** la case « Pastilles seulement », en bas de l'onglet Positions, n'affiche que les positions qui ont une pastille. **Historique :** le bouton « Historique des pastilles… » liste celles des 60 derniers jours (date, actif, colonne, valeur de la veille), pour retrouver ce qui a bougé pendant ton absence ; il n'est alimenté que les jours où le logiciel a été ouvert ou les cours actualisés. La colonne Perf. 3 ans/an est masquée par défaut : affiche-la avec le choix des colonnes. Après la mise à jour, une actualisation des cours est nécessaire pour la remplir.
- **ROCE :** la rentabilité des capitaux employés de l'entreprise, calculée avec les états financiers de Yahoo : résultat d'exploitation (EBIT) ÷ capitaux investis (fonds propres + dettes financières). Plus il est élevé, plus l'entreprise gagne d'argent avec le capital qu'elle utilise. La cellule affiche le dernier exercice avec une flèche (↑ ↓ →) comparée à l'exercice précédent ; **l'infobulle** (survole la cellule) donne l'évolution année par année, avec pour chaque exercice le résultat d'exploitation et les capitaux investis utilisés (en millions, devise de publication de la société) et, quand il diffère nettement, l'« EBIT normalisé » calculé par Yahoo. La colonne est masquée par défaut (bouton « Colonnes ») et existe aussi dans l'onglet Listes. Elle est vide pour les ETF, les cryptos, les banques et les assurances (pas de dettes à court terme dans leurs bilans) et quand Yahoo n'a pas les données. Quand les exercices sont irréguliers (un ROCE négatif, ou plus de 35 points d'écart entre le meilleur et le pire, signe d'éléments exceptionnels comme des gains ou pertes sur couvertures de change dans le résultat d'exploitation de Yahoo), la cellule affiche **la moyenne** sur les exercices disponibles, précédée de ≈ et suivie d'un ⚠, sans flèche ; l'infobulle l'explique. Les chiffres restent à titre indicatif.

**Opérations :** l'historique complet de l'enveloppe, que tu peux modifier, dupliquer ou supprimer.

**Répartition :** trois camemberts, par classe d'actifs, par zone géographique et par secteur économique, avec le détail en tableau.
- Le classement est **automatique** : Yahoo Finance d'abord, puis, si tu le souhaites, une intelligence artificielle pour les actifs restants. Tu **valides ou corriges toujours** les propositions avant qu'elles soient enregistrées.
- Pour l'IA, ouvre **Outils › Réglages IA** et saisis une clé gratuite Gemini ou Groq. Elle est facultative : Yahoo suffit pour la plupart des actifs. Yahoo est toujours interrogé en premier ; l'IA ne sert que pour ce qu'il ne sait pas classer. Chaque proposition indique sa source : « Yahoo », « IA Groq » ou « IA Gemini » (dans la fenêtre de validation du classement automatique, et dans le titre de la fenêtre de classement quand tu cliques sur « Proposer le classement »). Si tu as plusieurs clés, choisis dans « IA interrogée(s) après Yahoo » : l'une des deux seulement, ou les deux dans l'ordre que tu veux (par exemple Groq, puis Gemini si Groq ne donne rien).
- Un fonds diversifié peut être réparti sur plusieurs secteurs ou zones.

**Benchmark :** compare ta performance à celle d'un indice ou d'un ETF de référence. Saisis son symbole Yahoo (par exemple `CW8.PA`), puis **Appliquer**. **Retirer** supprime la comparaison. Le bouton **Ma liste…** te permet de choisir les ETF proposés dans la liste déroulante : coche ceux que tu veux parmi tes propres actifs (ceux qui ont un ticker) et les propositions standard, ou ajoute n'importe quel symbole Yahoo. Ton choix est mémorisé.

**Actifs vendus :** pour chaque vente, le prix de vente, la quantité, la valeur vendue, le cours actuel et le verdict **Sauvé / Loupé** : *sauvé* (vert) si le cours a baissé depuis ta vente, *loupé* (rouge) s'il a monté. La ligne de résumé donne le total sauvé, le total loupé et le bilan net. Elle montre aussi les performances de l'actif depuis. Le bouton **Colonnes…** choisit les colonnes affichées et leur ordre (Date de vente et Actif restent en tête), comme dans Positions : le réglage est mémorisé par enveloppe, avec le bouton « Revenir au réglage général ».

**Listes :** des listes de surveillance pour suivre des actions et ETF que tu ne détiens pas.
1. **Nouvelle liste…**, puis **Ajouter un actif…** (même recherche que pour un actif).
2. Pour chaque actif : secteur, cours, variation de la veille, performances, objectif et écart à l'objectif (double-clic sur l'objectif pour le saisir).
3. Les cours se mettent à jour avec le reste. Ces actifs n'entrent pas dans tes totaux.
4. **Retirer de la liste** n'efface pas l'actif de tes données.

**Airbag :** un outil de money management pour préparer un trade avant de passer l'ordre. Ce sont des **simulations** : les projets de trade forment une liste à part et ne créent aucune opération dans tes enveloppes.

Le principe : tu vends une partie de ta position à l'objectif (le *target*), et le gain encaissé couvre exactement la perte du reste si le stop est touché ensuite. Une fois la vente partielle faite, le trade ne peut plus te coûter d'argent.

1. **Enveloppe :** choisis le compte concerné. Le **capital** proposé est la valeur actuelle de cette enveloppe (ou de toutes en vue globale). Tu peux taper un autre montant ; le bouton **↺** reprend la valeur de l'enveloppe.
2. **Titre :** choisis un de tes actifs (son dernier cours est proposé comme prix d'achat) ou tape librement un nom. Raccourci : sélectionne la ligne d'un actif dans **Positions** (ou **Listes**, **Répartition**) puis clique sur l'onglet **Airbag** : l'actif y est mis tout seul.
3. **Je connais :** *mon stop* (ton support graphique) et le logiciel calcule le target minimum à atteindre, ou *mon target* (ton objectif graphique) et il calcule le stop à placer.
4. **Part de la position vendue au target :** 50 % par défaut. Plus tu vends, plus le target à atteindre est proche.
5. **Capital risqué :** la part du capital que tu acceptes de perdre si le stop est touché (0,5 % par défaut). Le logiciel en déduit le **nombre de titres** à acheter, arrondi à l'unité inférieure. Coche **Fractions de titres** pour les cryptos.
6. **Frais par ordre :** tes frais de courtage en %, comptés à l'achat et à la vente dans tous les calculs. Ils sont mémorisés pour chaque enveloppe.

Les sept cartes donnent le résultat : le target (ou le stop) calculé, le ratio **gain / risque** (favorable à partir de 2, acceptable à partir de 1), le **stop en ATR** (voir plus bas), le nombre de titres, le montant investi, le **risque maximum** (perte si toute la position sort au stop) et le **gain encaissé au target** (sur la part vendue seulement ; l'infobulle donne le gain si tout était vendu). Un message te prévient si la position dépasse ton capital (stop trop proche) ou si le risque choisi ne permet pas d'acheter un seul titre.

**Stop en ATR :** l'ATR est l'amplitude moyenne d'une séance du titre (moyenne de Wilder sur 14 séances, écarts d'ouverture compris). Le logiciel le demande à Yahoo quand tu choisis un de tes actifs, puis le garde pour la journée. La carte indique à combien d'ATR du prix d'achat se trouve ton stop : au-dessus de 1,5 ATR (vert), il est hors du bruit habituel du titre ; entre 1 et 1,5 ATR (orange), il peut être touché par une séance ordinaire ; sous 1 ATR (rouge), il est très serré. Un message l'indique aussi sous la carte. L'ATR est dans la devise de cotation de l'actif. Il n'est pas disponible pour un titre saisi librement ni pour un fonds sans ticker : la carte affiche alors « — ».

**Acheter…** : quand ton projet te convient, ce bouton ouvre la saisie d'une opération d'achat déjà remplie (enveloppe, actif, quantité calculée, prix d'achat, frais d'après ton taux, et le stop et le target en note). Passe d'abord ton ordre chez ton courtier, puis corrige le prix et les frais réels dans la fenêtre si besoin, et valide : l'achat entre dans tes comptes et le projet est enregistré dans la liste avec un **✓** (« acheté »). Si tu annules la fenêtre, rien n'est enregistré. Le logiciel n'envoie aucun ordre : le stop se règle toujours chez ton courtier. Pour le garder sous les yeux, affiche dans l'onglet Positions la colonne facultative **Stop (Airbag)** (bouton « Colonnes ») : elle montre le stop du dernier achat préparé dans l'Airbag, avec son écart au cours.

**Alerte « stop touché ».** Pour chaque position achetée via le bouton « Acheter… », le logiciel vérifie si le stop du projet a pu être atteint : le dernier cours est au stop ou en dessous, **ou le plus bas de séance depuis ton achat** (demandé à Yahoo après chaque actualisation) y est descendu, même si le cours est remonté ensuite ; le message donne alors la date et le niveau de ce plus bas. Dans ces cas, un **bandeau rouge** s'affiche en haut de la fenêtre tant que la position est détenue, la cellule « Stop (Airbag) » passe en gras avec un ⚠, et après une actualisation des cours une **fenêtre d'avertissement** s'ouvre (une seule fois par jour et par position). Le logiciel ne passe aucun ordre : c'est un rappel pour vérifier chez ton courtier que la vente a bien eu lieu, puis saisir la vente avec « Vendre ». L'alerte disparaît dès que la position est soldée. Un plus bas sous le stop prouve que le stop a **pu** se déclencher, pas qu'il l'a été (écart d'ouverture, type d'ordre, plus bas de la place principale) : confirme toujours chez ton courtier. Elle n'est active que si les cours sont actualisés : pense à « Actualiser les cours » ou à laisser l'actualisation automatique.

**Ajouter à la liste** enregistre le projet. Double-clique sur une ligne pour le modifier. En vue globale, tu vois les projets de toutes les enveloppes ; dans une enveloppe, seulement les siens.

**Scénario cygne noir :** sous la liste, la jauge additionne les pertes si **tous les stops sautaient en même temps**, en % du capital. Au-delà de 15 % (seuil prudent), un avertissement s'affiche ; au-delà de 20 %, l'exposition est jugée excessive.

**Exporter (CSV)** crée un fichier pour Excel. **Fiche imprimable** crée une page à imprimer ou à enregistrer en PDF depuis ton navigateur : celle du projet sélectionné, ou de toute la liste si aucune ligne n'est sélectionnée.

**Comment placer son stop avec l'Airbag (et l'ATR) :**

1. **Pars du graphique.** Repère le support (un creux récent, une zone où le cours a déjà rebondi) et place le stop juste en dessous, avec un coussin d'environ 0,5 à 1 ATR. S'il casse, ton idée de départ n'est plus valable.
2. **Saisis-le :** choisis l'actif, puis « Je connais : mon stop (support) » et tape le stop. Tu peux aussi taper le stop **en ATR** dans le champ « Stop en ATR » à droite (par exemple 2 pour un stop à 2 ATR) : le stop en euros est calculé pour toi, et inversement, quand tu modifies le stop, le champ ATR se met à jour. Si tu changes ensuite le prix d'achat, le stop en euros reste où il est. Le champ est grisé tant que l'ATR du titre n'est pas connu (titre saisi librement ou fonds sans ticker) et masqué en mode « mon target ».
3. **Contrôle la carte « Stop en ATR ».** Sous 1 ATR (rouge), le stop est trop serré : le simple bruit du titre le touchera. Entre 1 et 1,5 ATR (orange), c'est limite et il faut une raison graphique. Au-dessus de 1,5 ATR (vert), c'est correct ; entre 2 et 3 ATR, c'est courant pour quelques semaines de détention. Bien au-delà de 3 ATR, le stop est large : tu achètes moins de titres et le gain/risque se dégrade.
4. **Regarde le nombre de titres** (tu peux aussi le **taper toi-même** dans la carte : le risque réel et son pourcentage du capital sont alors recalculés, et un avertissement s'affiche s'il dépasse le capital risqué choisi ; vide le champ pour revenir au calcul automatique) **:** plus le stop est loin, moins tu en achètes, car le risque reste fixé à ton « capital risqué ». Vérifie que le montant investi reste raisonnable.
5. **Règle le target** avec le curseur de la part vendue (ou **tape directement le nombre de titres à vendre** dans le champ à droite du curseur : le curseur se place sur la part correspondante, et inversement ; vide le champ pour revenir au curseur), puis compare-le à une résistance du graphique ou à 4 à 6 ATR du prix d'achat. Si le target est irréaliste, vends une part plus grande ou relève le stop. Le gain/risque est favorable à partir de 1 : 2.
6. **Décide :** stop sous un vrai support, entre 1,5 et 3 ATR, target atteignable et gain/risque favorable : enregistre le projet. Sinon, ajuste le stop ou renonce au trade.

L'ATR est un garde-fou : il ne dit pas où est le bon stop, il dit si ton stop est trop serré ou trop large pour la volatilité du titre.

Pour un actif en devise étrangère, saisis les prix dans sa devise de cotation : les montants sont convertis en euros. Attention, un stop n'est pas une garantie : si le cours ouvre en fort écart, la perte réelle peut dépasser le risque calculé.

## 10. Corriger le solde des espèces

Pour les enveloppes avec suivi des espèces : si le solde affiché par le logiciel diffère de celui de ton courtier, sélectionne l'enveloppe puis clique sur **Corriger le solde espèces**. Tu indiques le solde réel, puis la **nature de l'écart**, que le logiciel ne peut pas deviner : **dividende ou coupon** (avec, si tu veux, l'actif concerné), **versement**, **retrait**, **frais**, ou **écart non expliqué**. Le logiciel crée alors l'opération correspondante, du montant exact de l'écart : un dividende, un versement, un retrait ou des frais comptent dans le résultat ou dans le TRI comme si tu les avais saisis toi-même, alors que « écart non expliqué » (arrondis, petits intérêts) crée une ligne « Régularisation » sans effet sur le rendement. Un écart positif ne peut être qu'un dividende, un versement ou un écart non expliqué ; un écart négatif, qu'un retrait, des frais ou un écart non expliqué.

## 11. Sauvegarder, restaurer, exporter

- **Sauvegarder :** **Fichier › Sauvegarder la base…** crée une copie complète de tes données. **Fais-le régulièrement, et toujours avant une mise à jour.**
- **Restaurer :** **Fichier › Restaurer une sauvegarde…** remplace tes données par celles d'une sauvegarde.
- **Exporter :** **Fichier › Exporter les opérations (CSV)…** crée un fichier lisible dans Excel, pour une ou plusieurs enveloppes.

## 12. Mettre à jour le logiciel

Au démarrage, le logiciel regarde si une nouvelle version existe (aucune donnée personnelle n'est envoyée). Tu peux le faire à la main avec **Aide › Rechercher une mise à jour…**, ou désactiver la vérification automatique dans ce même menu.

Pour mettre à jour : **ferme** Suivi Bourse, télécharge le nouvel installateur et lance-le. Tes données sont conservées.

## 13. Apparence et classement

Le menu **Affichage** propose le thème clair, le thème sombre, ou automatique (qui suit Windows). Le bouton **Thème** en haut à droite alterne entre les deux.

**Bande des indices :** en haut de la fenêtre, une ligne affiche la variation du jour des grands indices (par défaut CAC 40, DAX, S&P 500 et Nasdaq 100), en vert ou en rouge. Survole-la pour voir les niveaux des indices. Elle se met à jour toutes les 10 minutes et à chaque clic sur **Actualiser les cours** ; les cotations de Yahoo sont retardées d'environ 15 minutes. Dans le menu **Affichage**, **Choisir les indices affichés…** te permet de cocher d'autres indices (Euro Stoxx 50, STOXX Europe 600, FTSE 100, Dow Jones, Nikkei 225, Hang Seng) ou d'ajouter n'importe quel symbole Yahoo, et tu peux masquer la bande.

Le même menu propose **Classer les enveloppes par ordre alphabétique** (dans la liste de gauche). Désactivé, les enveloppes restent dans l'ordre où tu les as créées.

**Acheter et vendre depuis un tableau.** Sélectionne la ligne d'un actif puis clique sur **Acheter** (onglets Positions, Listes, Actifs vendus) ou **Vendre** (Positions) : la saisie d'opération s'ouvre déjà réglée sur le bon type, avec l'actif et son dernier cours ; il ne reste qu'à saisir la quantité. Dans une enveloppe, c'est elle qui est utilisée ; en vue globale, choisis l'enveloppe dans le menu de la fenêtre (celle de la ligne, ou de la vente d'origine, est proposée). Un **double-clic** sur une ligne de Listes (hors colonnes Objectif) ou d'Actifs vendus ouvre aussi l'achat. Le bouton **Airbag** (Listes, Actifs vendus) ouvre l'onglet Airbag avec l'actif choisi.

**Recherche au clavier dans les tableaux.** Dans Positions, Listes, Actifs vendus et Opérations, tape les premières lettres du nom d'un actif : la ligne correspondante est sélectionnée. Les lettres s'accumulent tant que tu ne fais pas de pause de plus d'une seconde et demie ; accents et majuscules sont ignorés.

**Confort de saisie.** Dans tous les champs de montants, taper « . » donne automatiquement une virgule. En entrant dans un champ, son nombre est sélectionné : tu tapes directement la nouvelle valeur. Dans un champ vide (par exemple « Stop en ATR »), le curseur se place avant « ATR », « % » ou « € », où que tu cliques. La molette de la souris ne change un montant que si le champ est sélectionné ; sinon elle fait défiler la page. Les grands nombres sont écrits avec des espaces (226 052,66). Dans l'onglet Airbag, **Entrée** ajoute le projet à la liste quand il est valide, **Tab** suit l'ordre de lecture, et les flèches ↑ ↓ font varier le « Stop en ATR » de 0,1. Le capital risqué et la part vendue sont mémorisés pour chaque enveloppe.

**Montants exacts.** Les totaux sont arrondis à l'euro pour rester lisibles ; **survole** un total ou une cellule pour voir le montant au centime.

## 14. Questions fréquentes

**Le cours d'un actif n'apparaît pas.** Son ticker est vide ou incorrect : ouvre **Outils › Mes actifs…**, modifie l'actif et utilise la recherche pour trouver le bon ticker. S'il n'en existe pas (fonds d'assurance-vie), utilise **Saisir un cours…**.

**La valeur d'un actif américain semble fausse.** Vérifie la devise : le prix de tes opérations doit être dans la devise de cotation de l'actif (en dollars pour une action américaine cotée aux États-Unis).

**Le TRI affiche « pas assez de recul ».** C'est normal quand les opérations sont très récentes, ou toutes à la même date (cas d'un import sans historique).

**J'ai importé un fichier et il manque des opérations.** Les lignes strictement identiques sont ignorées (section 5). Ajoute les opérations manquantes à la main.

**Où sont mes données ?** Dans `%APPDATA%\SuiviBourse` (menu **Outils › Ouvrir le dossier des données**). Pense à les sauvegarder.

**Les cours ne se mettent plus à jour.** Yahoo Finance limite parfois les demandes. Attends un peu et réessaie. Le logiciel n'est pas en panne.

**Les projets de l'onglet Airbag modifient-ils mes comptes ?** Non. Ce sont des simulations, rangées à part. Quand tu passes réellement l'ordre chez ton courtier, saisis l'achat avec **+ Opération** comme d'habitude.

**Y a-t-il des calculs fiscaux ?** Non. Suivi Bourse est un outil de suivi personnel : il ne constitue pas un conseil en investissement, et les cours sont donnés à titre indicatif.

---

*Suivi Bourse est un logiciel gratuit. Tes retours et idées sont les bienvenus dans l'onglet Issues du dépôt de téléchargement.*
