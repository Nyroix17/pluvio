# Revue du README

Relecteur : Nyroix17
Auteur relu : Nyroix17 (titre à Utilisation) et dyltan (Tests à Contact)
Date : 2026-11-06

| N° | Critère | Note (0 à 2) | Preuve (numéro de ligne ou extrait) |
|---|---|---|---|
| 1 | Titre et accroche | 2 | l.1 `# pluvio`, seul titre de niveau 1 ; l.3-4 citation « données de ce projet sont fictives » ; l.8-11 description de 4 lignes (quoi : statistiques de pluie ; pour qui : étudiants et développeurs) |
| 2 | Prérequis explicites | 2 | l.15 « Python 3.10 ou plus récent » ; l.16 Git ; l.17 pytest 7 ou plus récent |
| 3 | Installation reproductible | 2 | l.23-29 bloc `bash`, l.33-39 bloc `powershell`, dans l'ordre clone, venv, activation, pip ; l.24 et l.34 adresse réelle `https://github.com/Nyroix17/pluvio`, copiable telle quelle |
| 4 | Usage avec exemples exécutables | 2 | 4 exemples l.51-103, chacun suivi de sa sortie réelle dans un bloc `text` (l.55, 68, 85, 98) ; vérifié dans le terminal |
| 5 | Blocs de code balisés | 2 | tous les blocs ont un langage (`bash`, `powershell`, `text`) ; aucune invite `$` ni `PS>` |
| 6 | Structure et titres | 2 | 9 sections de niveau 2 dans l'ordre (l.6, 13, 19, 42, 116, 127, 161, 174, 178) ; seulement des niveaux 1 et 2 |
| 7 | Éléments visuels utiles | 2 | l.47 image avec texte alternatif « Flux : CSV, puis stats.py… » ; l.107-111 tableau des options ; l.129-159 arborescence |
| 8 | Tests | 2 | l.120-122 commande `pytest` ; l.124-125 résultat attendu « 40 passed » |
| 9 | Maintenance et contribution | 2 | l.163-172 procédure en 5 étapes ; l.176 licence MIT et lien `[LICENSE](LICENSE)` ; l.180-181 contact par les Issues |
| 10 | Lisibilité du source | 2 | aucune ligne de texte de plus de 80 caractères (la plus longue, l.11, en fait 79) ; aucun espace en fin de ligne |

Total : 20 / 20

## Trois améliorations proposées

1. Section Tests (l.116-125) : ajouter la commande
   `python verifier_readme.py README.md` et sa sortie « README conforme. »
   pour montrer comment contrôler le README.
2. Section Contact (l.180-181) : remplacer la description de l'onglet par le
   lien direct `https://github.com/Nyroix17/pluvio/issues`.
3. Section Utilisation, tableau l.109 : l'option `--commune` exige
   l'orthographe exacte du fichier, mais les communes disponibles ne sont
   listées nulle part. `--commune "Schoelcher"` répond « Aucun relevé pour
   ces critères. » alors que la commune existe (elle s'écrit « Schœlcher »).
   Proposition : lister les 6 communes du fichier sous le tableau.
