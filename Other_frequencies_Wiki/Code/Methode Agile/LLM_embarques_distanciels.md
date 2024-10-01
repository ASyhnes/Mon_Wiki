
# Modèles de Langage (LLM) embarqués ou distanciels

## LLM embarqués
Pour un projet d'assistant vocal sur un Raspberry Pi 4, il existe plusieurs petits modèles de langage (LLM) qu'on peut envisager :

- **GPT-J** : Un modèle plus léger, qui peut être utilisé localement sur un Raspberry Pi, mais nécessitera probablement une optimisation via ONNX ou TensorFlow Lite pour s'adapter aux contraintes matérielles.
- **LLaMA** : Un autre modèle léger qui peut être configuré pour fonctionner localement avec une consommation réduite de ressources.
- **DistilGPT-2** : Une version allégée de GPT-2 qui pourrait également être envisagée pour une utilisation locale.

### Avantages des LLM embarqués :
- Pas besoin de connexion Internet constante.
- Traitement local des données (meilleure confidentialité).

### Inconvénients :
- Limité par les performances du Raspberry Pi.
- Modèles moins puissants et moins précis que ceux exécutés sur des serveurs.

## LLM distanciels
Utiliser un LLM distanciel via une API comme **ChatGPT** (OpenAI) est une solution simple et efficace. Cette approche permet de bénéficier de la puissance des modèles de langage les plus avancés tout en déchargeant le Raspberry Pi de la complexité du traitement.

### Avantages :
- Modèles très performants.
- Pas de souci de limitation matérielle.

### Inconvénients :
- Nécessite une connexion Internet.
- Peut générer des coûts d'usage selon le nombre de requêtes.

### Idée: 
Implémenté la possibilité d'une configuration vocale permettant de passer d'un modèle à l'autre en fonction des besoins, possibilité.
