# Modele X Forensic

Ce projet vise à la conception et l'entrainement d'un modele spécialisé en **Digital Forensic** à partir d'une base de connaissances documentaire (PDF technique, rapports, documentations).
L'approche repose sur une génération contrôlée de questions-réponses et une sélection (basée sur des métriques) du meilleur LLM, suivies d'un perfectionnement progressif par fine-tuning et RAG.

---

## Objectifs

- Construire une base de données (forensic_qa_dataset.json) de 300 questions.
- Réduire les hallucinations en s'appuyant sur des documents.
- Comparer plusieurs LLMs pour chaque réponse et sélectionner le meilleur.
- Entrainer un modele capable de répondre à des questions techniques, s'appuyer sur des preuves et des faits issus de documents forensiques et évoluer vers un assistant d'analyse numérique spécialisé.

---

## Prérequis

### Logiciels nécessaires

- **Python 3.8+**
- **FastAPI**
- **Uvicorn**
- **Scikit-learn**
- **Pickle**

### Installation des dépendances

Crée un environnement virtuel et installe les dépendances nécessaires avec la commande suivante :

```bash
pip install -r requirements.txt
```

Exemple de contenu du fichier `requirements.txt` :
```txt
fastapi
uvicorn
scikit-learn
numpy
```

---

## Pipeline d'entrainement

### Base de connaissances

### Génération des questions-réponses

### Génération multi LLM

### Sélection meilleur réponse

### Fine-tuning du modéle

### Intégration d'un Retrival Augmented Generation (RAG)

---

## Structure du projet

```plaintext
.
├── Pipeline.org           # Pipeline utilisé et interprétation des résultats
├── Data                   # Base de connaissance utilisée (peut être améliorée)
├── Sample_QR              # Échantillon de 300 questions/réponses
├── prediction.json        # Métriques de performance
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
