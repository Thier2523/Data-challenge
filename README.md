# Data Challenge HRFLOW.AI – Prédiction des comportements utilisateurs sur un jobboard

## Contexte
Ce projet a été réalisé dans le cadre du **Data Challenge HRFLOW.AI**, organisé par la plateforme HRFLOW.AI, spécialisée dans l’innovation du recrutement et l’analyse des parcours utilisateurs sur les jobboards.  
L’objectif était de prédire les prochaines offres d’emploi qu’un candidat est susceptible de consulter ainsi que l’action qu’il effectuera : consultation (*view*) ou candidature (*apply*), à partir de son historique de navigation.

## Dataset
Le jeu de données comprenait trois fichiers principaux :  
- **x_train** : séquences de navigation des candidats (sessions, jobs consultés, actions)  
- **y_train** : pour chaque session, le job à prédire et l’action correspondante  
- **job_listings.json** : descriptions textuelles des offres (résumé, détails, compétences requises)  

Le dataset contient 15 882 sessions et 21 917 jobs distincts, avec environ 8 offres consultées par session. Les descriptions textuelles ont été encodées pour créer des embeddings exploitables par les modèles séquentiels.

## Outils et technologies
- **Python** : prétraitement, nettoyage, feature engineering, encodage des textes  
- **SQL** : exploration et requêtes sur les données structurées  
- **RNN / LSTM** : modélisation séquentielle pour prédire les prochaines consultations et l’action des candidats  
- **CSV / Excel** : préparation et documentation des données

## Méthodologie
1. **Prétraitement des données**
   - Conversion des IDs de jobs en listes d’entiers
   - Structuration du JSON en tableau (job_id, description)
   - Encodage des textes pour générer des embeddings

2. **Approches testées**
   - **Méthode naïve** : filtrage collaboratif basé sur les similarités entre sessions  
   - **Historique + contenu des offres** : enrichissement avec similarités cosinus des descriptions  
   - **RNN / LSTM** : modèles séquentiels capturant la dépendance temporelle des consultations


## Résultats et apprentissages
- Les modèles RNN/LSTM permettent de mieux prendre en compte la séquence des consultations et de prédire l’action (view/apply) des candidats  
- L’utilisation combinée de l’historique des sessions et du contenu des offres enrichit les recommandations  


