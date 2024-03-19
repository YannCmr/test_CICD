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


# Exercice 2 

## a)
**Sur l’onglet Summary d’une analyse de code, SonarCloud fournit 4 indicateurs. Quels sont-ils et quelles sont leurs utilités ?**  
- Bugs : problème dans le code qui peut poser une erreur ou un comportement inattendu. Sert à cibler les corrections à faire en priorité pour la stabilité.
- Vulnérabilité : montre le nombres de points faibles détectés. Sert à protéger l'application des attaques.
- Code smells : cible le code rendant le code plus difficile à comprendre, à mainteneir, ou à étendre. Sert à améliorer la maintenabilité du code.
- Couverture : fournit un pourcentage indiquant quel % du code source est couvert par les tests automatisés. Sert à donner un indicateur de confiance dans la qualité et la fiabilité de l'application.

**À quoi sert l’indicateur Quality Gate ?**  
Le Quality Gate est un concept clé dans SonarCloud qui sert à évaluer automatiquement si un projet de code respecte un certain ensemble de critères de qualité avant qu'il ne soit considéré comme acceptable pour une étape suivante (par exemple, avant d'être déployé en production ou avant de fusionner une pull request). Un Quality Gate peut être personnalisé, mais il inclut typiquement des critères liés aux bugs, aux vulnérabilités, aux odeurs de code, et à la couverture des tests. Si un projet passe le Quality Gate, cela indique qu'il répond aux normes de qualité minimales définies. Si le projet échoue, il doit être amélioré avant de progresser. L'indicateur Quality Gate permet donc d'assurer une certaine qualité du code et de minimiser les risques avant les déploiements ou les intégrations de changements.