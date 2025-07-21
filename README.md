# AT-T-project

## Project Overview
AT&T est une société multinationale américaine de télécommunications, dont le siège se trouve à la Whitacre Tower au centre-ville de Dallas, Texas. C’est la plus grande entreprise de télécommunications au monde en termes de chiffre d’affaires.

L’un des principaux problèmes des utilisateurs AT&T est l’exposition constante aux messages indésirables (SPAM). Après une phase de signalement manuel, AT&T cherche désormais à automatiser la détection de ces spams pour mieux protéger ses clients.

## Dataset
Le jeu de données contient 5 572 SMS étiquetés comme spam ou ham (légitime). Chaque enregistrement initial comportait quatre colonnes de texte que j'ai concaténées en un unique champ message.

## Preprocessing Pipelines
Quatre versions du dataset ont été créées pour comparer l’impact du prétraitement :
- Raw Tokenization
  - Tokenisation simple sans aucune modification du texte.
- Basic Preprocessed
  - Suppression des stopwords
  - Remplacement des URLs par “URL”
  - Remplacement des adresses e-mail par “EMAIL”
  - Remplacement des mentions @username par “USER”
  - Suppression des caractères non alphabétiques
  - Réduction des répétitions de lettres (ex. “heeeello” → “heello”)
- Lemmatization
  - Application de la lemmatisation sur le dataset prétraité
- Stemming
  - Application du stemming sur le dataset prétraité


## Models
- Transformer pré-entraîné (BERT)
- Fully Connected Neural Network (MLP)
- LSTM (Long Short-Term Memory)
- GRU (Gated Recurrent Unit)

## Results & Recommendations
- Tous les modèles performent bien, la version raw (hors BERT) affiche un léger retard.
- Les écarts entre les architectures séquentielles (LSTM/GRU) et l’approche fully connected ne sont pas significatifs.
- Le modèle fully connected étant le plus rapide tout en conservant une excellente performance, il est recommandé pour un déploiement en production.
