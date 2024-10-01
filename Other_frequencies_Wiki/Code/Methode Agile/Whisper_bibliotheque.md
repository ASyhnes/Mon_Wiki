
# Bibliothèque Whisper

**Whisper** est un modèle de reconnaissance vocale développé par OpenAI, conçu pour convertir la parole en texte. Il est extrêmement performant et peut être utilisé dans des projets d'assistant vocal pour capturer des commandes vocales et les traduire en texte compréhensible pour un LLM.

## Fonctionnement de Whisper
Whisper fonctionne via un modèle de deep learning capable d'écouter l'entrée audio d'un microphone et de la transcrire automatiquement. Il est robuste aux différents accents et bruits de fond, ce qui le rend idéal pour des environnements variés.

## Utilisation dans un projet vocal
1. Capturer la voix via un microphone.
2. Convertir la parole en texte avec Whisper.
3. Envoyer ce texte à un LLM (local ou via API) pour obtenir une réponse.
4. Convertir la réponse en voix à l'aide d'un outil comme `gTTS` (Google Text-to-Speech).

Whisper peut être installé via pip :
```
pip install openai-whisper
```
