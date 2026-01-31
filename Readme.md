# Modele X Forensic

Ce projet vise à la conception et l'entrainement d'un modele spécialisé en **Digital Forensic** à partir d'une base de connaissances documentaire (PDF technique, rapports, documentations).
L'approche repose sur une génération contrôlée de questions-réponses et une sélection (basée sur des métriques) du meilleur LLM, suivies d'un perfectionnement progressif par fine-tuning et RAG.

---

> **Notebook**  
> Les étapes de l'entrainement peuvent être directement visualisé depuis PipelineQuizz.org.  
> Le notebook (format Raw) sera également disponible.
> Noté que ce dernier fait lieu de brouillon

---

## Objectifs

- Construire une base de données (forensic_qa_dataset.json) de 300 questions.
- Réduire les hallucinations en s'appuyant sur des documents.
- Comparer plusieurs LLMs pour chaque réponse et sélectionner le meilleur.
- Entrainer un modele capable de répondre à des questions techniques, s'appuyer sur des preuves et des faits issus de documents forensiques et évoluer vers un assistant d'analyse numérique spécialisé.

---

## Prérequis

### Environnement de travail

- **Python 3.8+ (local)**
- **Kaggle / Colab (cloud)**

### Installation des dépendances (optionnel)

Crée un environnement virtuel et installe les dépendances nécessaires avec la commande suivante :

```bash
pip install -r requirements.txt
```

---

## Pipeline d'entrainement

### Base de connaissances
- Documents PDF lié au Digital Forensic
- Découpage en chunks
- Aucune génération hors contenu des documents

### Génération des questions-réponses
- Génération de 6 à 8 questions réponses techniques
- Réponses courtes

### Génération multi LLM
Chaque question recoit une réponse générée par trois LLMs choisis

### Sélection meilleur réponse
Sélection en fonction des métriques de:
- précision technique
- d'absence d'hallucinations
- de fidélité par rapport au ground_truths

### Fine-tuning du modéle
Le dataset est utilisé pour:
- améliorer la cohérence et la précision des réponses
- renforcer la spécialisation en digital forensic

### Intégration d'un Retrival Augmented Generation (RAG)
- Actualisation des connaissances sans rééntrainement
- Plus de limite concernant les hallucinations
- Adapter le modele à de nouvelles données

---

## Structure du projet

```plaintext
.
├── PipelineQuizz.org      # Pipeline utilisé et interprétation des résultats
├── Data                   # Base de connaissance utilisée (peut être améliorée)
├── forensic_qa_dataset    # Échantillon de 300 questions/réponses
├── Metriques/             # Métriques de performance
├── requirements.txt       # Fichier listant les dépendances Python
└── README.md              # Documentation du projet
```

---

## Cas d'usage

- Formation en investigation numérique
- Aide à l'analyse post-mortem
- Recherche académique en forensiques et IA

---

## Prochaines améliorations

- **Données de base du dataset** : Inclure une base de connaissance plus large.
- **Choix du LLM** : Tester d'autres LLMs et évaluer leur métrique.
- **Application** : Implémenter une application et y déployer le model dans un cadre d'étude réel.

---

## Contributeurs

- Erico
