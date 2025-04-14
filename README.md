# 🧠 PS3 Error Code Database

Ce projet fournit une base de données simple au format **JSON** listant les **codes d’erreur** courants rencontrés sur le système d’exploitation de la **PlayStation 3**, accompagnés de leur **signification** et **solution** possible.
Source: logic-sunrise.com

## 🗂️ Format du fichier

Le fichier `DataBase.json` contient une liste d’erreurs représentées sous forme d'objets JSON. Exemple :

```json
{
  "erreur": [
    {
      "8013030": {
        "erreur": "8013030",
        "solution": "Erreur système - échec de mise à jour."
      }
    },
    {
      "80010001": {
        "erreur": "80010001",
        "solution": "Erreur majeure, lecture du jeu impossible (disque détérioré)."
      }
    }
  ]
}
```

## ✅ Objectif

- Fournir une base de référence rapide pour les développeurs ou moddeurs qui souhaitent diagnostiquer des erreurs PS3.
- Peut être utilisée dans des **interfaces graphiques**, **scripts de diagnostic** ou **applications web**.

## 💡 Exemple de lecture (Python)

```python
import json

with open('DataBase.json', 'r') as file:
    data = json.load(file)
    code = "80010001"
    for err in data["erreur"]:
        if code in err:
            print(f"Erreur {code} : {err[code]['solution']}")
```

## 🧹 Extensions possibles

- Ajout de nouveaux codes d’erreurs régulièrement.
- Création d’une API ou d’un site web pour les rechercher en ligne.

