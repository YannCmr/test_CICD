# Exercice 1

## a) 
RAS

## b)
**Quelles étapes (steps) sont réalisées par cette action ?**
1. **Check-out du code source :** Utilise l'action `actions/checkout@v3` pour cloner le repository dans l'environnement de build de GitHub Actions.
2. **Configuration de Python :** Utilise l'action `actions/setup-python@v3` avec la spécification `python-version: "3.10"` pour installer et configurer Python 3.10 sur l'environnement de build.
3. **Installation des dépendances :** Exécute des commandes shell pour mettre à jour `pip` et installer deux paquets (`flake8` et `pytest`) ainsi que les dépendances listées dans `requirements.txt`, si ce fichier existe.
4. **Lint avec flake8 :** Utilise `flake8` pour effectuer un linting du code, d'abord pour identifier les erreurs critiques de syntaxe ou les noms non définis, puis pour évaluer la qualité du code sans échouer pour des erreurs moins sévères.
5. **Tests avec pytest :** Exécute les tests unitaires du projet en utilisant `pytest`.



**Une étape est définie au minimum par 2 éléments, lesquels sont-ils et à quoi servent-ils ?**
Une étape est au minimum définie par les éléments suivants :

- **name :** Un nom descriptif pour l'étape. Cela permet une meilleure lisibilité et compréhension de ce que fait l'étape lors de l'exécution de l'action.
- **uses ou run :** 
    - **uses :** Sert à indiquer qu'une action partagée sur le marketplace de GitHub ou un référentiel doit être utilisée. Elle est souvent utilisée pour intégrer des actions réutilisables comme `actions/checkout@v3` ou `actions/setup-python@v3`.
    - **run :** Permet d'exécuter des commandes shell directement dans l'environnement de build. Ces commandes peuvent être des scripts shell, des commandes Python, ou toute autre commande disponible dans l'environnement.




**La première étape contient le mot-clé 'with', a quoi sert-il ?**

Le mot-clé `with` est utilisé pour passer des paramètres supplémentaires à l'action ou à l'étape en cours d'exécution. Dans le contexte de l'étape de configuration de Python, `with` sert à spécifier la version de Python à installer et à configurer (dans ce cas, Python 3.10). Cela permet de personnaliser le comportement des actions utilisées, en fournissant des configurations spécifiques nécessaires à l'exécution de l'étape.