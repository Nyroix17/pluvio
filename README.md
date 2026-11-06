# pluvio

> Attention : toutes les données de ce projet sont fictives. Elles ne
> proviennent d'aucune station de mesure.

## Description

`pluvio` est un outil Python en ligne de commande. Il lit un fichier CSV de
relevés de pluie de communes de Martinique et calcule des statistiques :
nombre de relevés, total, moyenne, maximum et total par commune. Il s'adresse
aux étudiants et aux développeurs qui veulent explorer ces relevés au terminal.

## Prérequis

- Python 3.10 ou plus récent
- Git, pour cloner le dépôt
- pytest 7 ou plus récent, installé avec `requirements.txt`

## Installation

Linux et macOS (bash) :

```bash
git clone https://github.com/Nyroix17/pluvio pluvio
cd pluvio
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Windows (PowerShell) :

```powershell
git clone ADRESSE_DU_DEPOT pluvio
cd pluvio
py -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Remplacez `ADRESSE_DU_DEPOT` par l'adresse de votre dépôt GitHub.

## Utilisation

Lancez les commandes depuis la racine du dépôt, environnement virtuel activé.
Le schéma ci-dessous montre le trajet des données dans l'outil.

![Flux : CSV, puis stats.py, cli.py et terminal](docs/schema_flux.svg)

Résumé de tous les relevés du fichier :

```bash
python -m pluvio.cli data/pluies_fictives.csv
```

```text
Relevés : 90
Total : 1076.5 mm
Moyenne : 12.0 mm
Maximum : 36.6 mm (2025-01-07)
```

Total de pluie de chaque commune :

```bash
python -m pluvio.cli data/pluies_fictives.csv --par-commune
```

```text
Commune           Total (mm)
Fort-de-France         115.6
La Trinité             171.4
Le Lamentin            170.4
Le Robert              203.3
Sainte-Anne            190.8
Schœlcher              225.0
```

Relevés d'une seule commune ; les guillemets sont nécessaires si le nom
contient une espace :

```bash
python -m pluvio.cli data/pluies_fictives.csv --commune "Le Robert"
```

```text
Relevés : 15
Total : 203.3 mm
Moyenne : 13.6 mm
Maximum : 34.6 mm (2025-01-02)
```

Les filtres se combinent, par exemple une commune sur un mois :

```bash
python -m pluvio.cli data/pluies_fictives.csv --commune "Fort-de-France" --mois 2025-02
```

```text
Relevés : 5
Total : 30.0 mm
Moyenne : 6.0 mm
Maximum : 27.0 mm (2025-02-01)
```

Options de la commande (aide complète : `python -m pluvio.cli --help`) :

| Option | Valeur attendue | Effet |
| :--- | :--- | :--- |
| `--commune NOM` | nom d'une commune, entre guillemets s'il contient une espace | garde seulement les relevés de cette commune (majuscules et minuscules confondues) |
| `--mois AAAA-MM` | un mois, par exemple `2025-01` | garde seulement les relevés de ce mois |
| `--par-commune` | aucune | affiche le total de pluie de chaque commune, classé par nom |

Si aucun relevé ne correspond aux filtres, l'outil affiche
« Aucun relevé pour ces critères. » et se termine avec le code 1.

## Tests

Depuis la racine du dépôt, environnement virtuel activé, lancez :

```bash
pytest
```

Résultat attendu : pytest se termine par une ligne `40 passed`, sans aucun
test en échec (`failed`).

## Arborescence

```text
.
├── .github/
│   └── pull_request_template.md   modèle de pull request
├── data/
│   └── pluies_fictives.csv        relevés de pluie fictifs
├── docs/
│   ├── revue_modele.md            modèle de revue du README
│   └── schema_flux.svg            schéma du flux de données
├── exercices/
│   ├── ex1_erreurs.md
│   ├── ex2_rendu.md
│   └── ex2_rendu_cible.png
├── pluvio/
│   ├── __init__.py
│   ├── cli.py                     interface en ligne de commande
│   └── stats.py                   lecture du CSV et calculs
├── tests/
│   ├── test_cli.py
│   ├── test_readme.py
│   ├── test_stats.py
│   └── test_verifier_readme.py
├── .gitignore
├── grille_qualite_readme.md       grille d'évaluation d'un README
├── LICENSE
├── pytest.ini
├── README.md
├── rendre_zip.py                  crée l'archive de secours rendu.zip
├── requirements.txt
└── verifier_readme.py             contrôle les sections et blocs de code
```

## Contribution

1. Mettez `main` à jour : `git switch main`, puis `git pull`.
2. Créez une branche dédiée, par exemple `git switch -c docs/ma-correction`.
3. Faites des commits courts au format `type: résumé`, avec un type parmi
   `docs`, `fix`, `test`, `feat` ou `chore`, par exemple
   `docs: corriger la section Tests`.
4. Lancez `pytest` : tous les tests doivent réussir. Ne modifiez ni `tests/`
   ni `pytest.ini`.
5. Faites `git pull --rebase`, poussez votre branche, puis ouvrez une pull
   request vers `main`. Elle est relue avec `grille_qualite_readme.md` avant
   d'être fusionnée.

## Licence

Ce projet est distribué sous licence MIT : voir le fichier [LICENSE](LICENSE).

## Contact

Pour une question ou un bogue, ouvrez une issue dans l'onglet « Issues » du
dépôt GitHub du projet.