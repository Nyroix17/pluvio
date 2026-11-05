# Ex.2

1. **Préparer l'environnement**
   - Créer l'environnement virtuel
     - Linux et macOS : `python3 -m venv .venv`
     - Windows : `py -m venv .venv`
   - Installer `pytest`

2. **Lancer un calcul**
   - Choisir le fichier CSV
   - Ajouter des **options** si besoin

| Option | Argument | Exemple |
|:---|:---:|---:|
| `--commune` | texte | `"Le Robert"` |
| `--mois` | AAAA-MM | `2025-01` |
| `--par-commune` | aucun | |

**Appel depuis Python :**

```python
from pluvio import stats

releves = stats.lire_releves("data/pluies_fictives.csv")
print(len(releves))
```

*Rappel :* les données sont fictives.