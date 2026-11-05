# Suivi Bourse (version bêta)

Logiciel **Windows gratuit** pour suivre toutes tes enveloppes d'investissement (PEA, CTO, assurance-vie, PER…) au même endroit, sans fichier Excel. **Tes données restent sur ton ordinateur.**

## Télécharger

➡️ **[Dernière version](../../releases/latest)** → section *Assets* :

- **`SuiviBourse-Setup.exe`** (recommandé) : double-clique, suis l'assistant. Il propose de créer une **icône sur le Bureau** et ajoute le logiciel au menu Démarrer. Aucun droit administrateur n'est nécessaire. Pour mettre à jour, il suffit de lancer le nouvel installateur : tes données sont conservées.
- **`SuiviBourse.exe`** : version portable, sans installation. Double-clique dessus pour l'utiliser (pour une icône sur le Bureau : clic droit › *Envoyer vers* › *Bureau (créer un raccourci)*).

> **Avertissement Windows** : le programme n'est pas signé numériquement. Si Windows affiche « Windows a protégé votre ordinateur », clique sur **Informations complémentaires**, puis **Exécuter quand même**.

### Vérifier ton téléchargement

Ne télécharge Suivi Bourse **que depuis ce dépôt**. Pour t'assurer que ton fichier est bien l'original :

1. Sur la page de la release, repère l'empreinte **sha256** affichée à droite du fichier téléchargé (elle commence par `sha256:`).
2. Sur ton ordinateur, ouvre **PowerShell** dans le dossier du fichier téléchargé et tape : `Get-FileHash .\SuiviBourse-Setup.exe`
3. Compare : les deux séries de lettres et de chiffres doivent être **identiques**. Sinon, supprime le fichier et retélécharge-le.

## Ce qu'il fait

- Enveloppes illimitées, avec une vue globale de tout ton patrimoine boursier.
- Achats, ventes, dividendes, versements, retraits, frais.
- Colonnes au choix dans l'onglet Positions : variation depuis la veille, objectif de cours (saisi à la main) et écart à l'objectif, performance annualisée sur 5 ans.
- Actualisation des cours au démarrage, et en option automatique toutes les 30 min, 1 h ou 2 h (menu Outils).
- Cours automatiques via Yahoo Finance (saisie manuelle possible pour les fonds sans cours).
- Valeur, net investi, gain, plus-value latente, plus-values réalisées, **TRI annualisé**, courbe d'évolution.
- Import CSV de l'historique de ton courtier, export, sauvegarde.
- Mode clair et mode sombre.

## À savoir (bêta)

- Version de test : des erreurs sont possibles. **Fais des sauvegardes** (menu *Fichier › Sauvegarder la base*).
- Les cours viennent de Yahoo Finance et sont donnés à titre indicatif.
- Au démarrage, le logiciel vérifie sur GitHub si une nouvelle version existe (simple lecture, aucune donnée personnelle envoyée). Désactivable dans Aide › Vérifier automatiquement au démarrage.
- Aucun calcul fiscal. Ce logiciel ne constitue pas un conseil en investissement.
- Tes données sont dans `%APPDATA%\SuiviBourse` (menu *Outils › Ouvrir le dossier des données*). La désinstallation **ne les supprime pas**.

## Un problème, une idée ?

Ouvre un sujet dans l'onglet **Issues** de ce dépôt (décris ce que tu faisais et le message affiché).

## Licence

Freeware : gratuit pour un usage personnel, tous droits réservés. Voir le fichier [LICENCE](LICENCE).
