# Suivi Bourse

Logiciel Windows **100 % local** pour suivre toutes tes enveloppes d'investissement (PEA, CTO, assurance-vie, PER…) sans fichier Excel. Tes données restent sur ton ordinateur.

## Ce qu'il fait

- **Enveloppes** : crée autant d'enveloppes que tu veux (PEA, CTO, AV, PER, crypto…).
- **Actifs et opérations** : achats, ventes, dividendes, versements, retraits, frais.
- **Cours automatiques** via Yahoo Finance (actualisation au lancement, une fois par jour, ou à la demande). Pour un actif sans cours Yahoo (fonds d'assurance-vie, fonds euros…), tu saisis le cours à la main.
- **Suivi** par enveloppe **et** global : valeur, net investi, gain, plus-value latente, plus-values réalisées, dividendes, **TRI annualisé** (équivalent de `XIRR` d'Excel), courbe d'évolution.
- **PRU** (prix de revient unitaire) calculé en méthode du coût moyen pondéré, frais inclus.
- **Actifs en devises** (USD, GBP…) : conversion en euros avec les taux Yahoo.
- **Import CSV** de l'historique de ton courtier (les colonnes sont devinées, tu les corriges si besoin), saisie manuelle pour les autres.
- **Mode clair / sombre** (menu Affichage ou bouton « Thème »), mémorisé d'une fois sur l'autre.
- **Export CSV** des opérations et **sauvegarde / restauration** de la base.

## Installation (utilisateur)

1. Télécharge `SuiviBourse-Setup.exe` (installateur, icône Bureau en option) ou `SuiviBourse.exe` (version portable, sans installation) depuis la page de téléchargement (dépôt public, section *Releases*).
2. Double-clique dessus. Rien d'autre à installer.

> **Avertissement Windows** : comme le programme n'est pas signé numériquement, Windows peut afficher « Windows a protégé votre ordinateur ». Clique sur **Informations complémentaires → Exécuter quand même**.

Tes données sont dans `%APPDATA%\SuiviBourse\suivi_bourse.db` (menu **Outils › Ouvrir le dossier des données**).

## Premiers pas

1. **+ Nouvelle enveloppe** (en bas à gauche) : donne un nom et un type.
   - *Case décochée* (conseillé) : tu saisis tes achats/ventes, le TRI part de ces flux.
   - *Case cochée* : tu saisis aussi les versements/retraits d'espèces ; utile pour une assurance-vie ou un PER où tu veux suivre l'argent versé.
2. **+ Opération** : choisis le type, l'actif (ou **Nouvel actif…** : recherche Yahoo par nom, ISIN ou symbole), la quantité, le prix, les frais.
   - Tickers Yahoo : `AIR.PA` (Paris), `.AS` (Amsterdam), `.DE` (Xetra), `.L` (Londres), `.MI` (Milan)…
3. **Fichier › Importer un historique CSV** si ton courtier propose un export.

### Cas particuliers

- **Fonds euros / fonds sans cours Yahoo** : crée l'actif sans ticker, saisis une quantité (ex. 8 000 parts à 1 €), puis **Positions › Saisir un cours à la main** quand tu veux mettre à jour la valeur.
- **Actif valorisé « * »** dans Positions : aucun cours n'est connu, la ligne est comptée au prix de revient.
- **TRI « n.s. »** : moins de 30 jours de recul, annualiser n'aurait pas de sens.

## Limites à connaître

- Les cours viennent de Yahoo Finance via la bibliothèque non officielle `yfinance` : ils sont **indicatifs**, parfois en retard ou absents (surtout pour les fonds). Ils peuvent cesser de fonctionner si Yahoo change son service.
- Le logiciel vérifie au démarrage s'il existe une version plus récente (lecture de la dernière release publique GitHub, aucune donnée envoyée). Désactivable dans Aide › Vérifier automatiquement au démarrage.
- **Pas de calcul fiscal** (flat tax, abattements, PFU…). 
- Le logiciel ne constitue **pas un conseil en investissement**.

## Pour les développeurs

```bash
pip install -r requirements-dev.txt
python -m pytest                 # tests
python run.py                     # lancer l'application
python tests/smoke_ui.py sortie  # captures d'écran hors écran
lancer.bat                        # lance l'application sans compiler (Windows)
build_windows.bat                # construit dist\SuiviBourse.exe (Windows)
```

Structure : `db.py` (SQLite), `calc.py` (PRU, valorisation, XIRR, historique), `prices.py` (Yahoo + cache), `importer.py` (CSV), `dialogs.py` / `mainwindow.py` / `widgets.py` (interface PySide6).

## Licence

Freeware : gratuit pour un usage personnel, **tous droits réservés** (modification, décompilation et redistribution interdites). Voir `LICENCE`. Composants tiers : voir `NOTICES.md`.

## Distribution

`PUBLIER.md` : code dans un dépôt GitHub privé, `.exe` publié dans un dépôt public de téléchargement (le dossier `depot-public/` contient le README et la licence de ce dépôt public).
`serveur/` : page de téléchargement avec clé de licence sur o2switch, pour plus tard (non utilisée pendant la bêta ; la clé est désactivée dans `suivi_bourse/licence.py`).
