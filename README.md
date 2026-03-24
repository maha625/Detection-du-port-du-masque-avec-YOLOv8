Détection de Masques Faciaux avec YOLOv8

Ce projet implémente un système de détection d'objets en temps réel pour identifier le port du masque chirurgical. Il a été développé dans le cadre du module Deep Learning à l'ENSAM-Meknès (Filière GILSI).

**📊 Présentation du Dataset**

Le modèle est entraîné sur le Face Mask Detection Dataset disponible sur Kaggle.

Lien du Dataset : [Kaggle - Face Mask Detection](https://www.kaggle.com/datasets/andrewmvd/face-mask-detection)

Contenu : 853 images et trois classes d'annotations :

0 : with_mask (Port correct)

1 : without_mask (Pas de masque)

2 : mask_weared_incorrect (Masque mal porté)

**📁 Structure du Projet**


├── dataset/               # Données brutes (Images PNG + Annotations XML) 

├── data/                  # Données converties au format YOLO (Généré par le script)

├── converter.py           # Script de conversion XML -> TXT et Split Train/Val

├── data.yaml              # Configuration des chemins pour YOLOv8

├── train.py               # Script de lancement de l'entraînement

├── test_inference.py      # Script de test sur des images isolées

├── .gitignore             # Exclusion des fichiers lourds pour Git

└── README.md              # Documentation du projet


**🛠️ Installation et Prérequis**

Cloner le projet (uniquement les scripts) :git clone <url-du-repo>
cd mini_projet


Installer les dépendances :pip install ultralytics pandas matplotlib scikit-learn


Télécharger les données :Rendez-vous sur le lien Kaggle, téléchargez le ZIP, extrayez-le et placez les dossiers images et annotations dans le répertoire dataset/ à la racine du projet.

**🚀 Utilisation**

1. Préparation des données

Lancez la conversion des annotations XML au format YOLO et la répartition (80% train, 20% val) :python converter.py


2. Entraînement

Pour lancer l'apprentissage du modèle :python train.py


3. Évaluation et Test

Pour tester le modèle final (best.pt) sur une image :python test_inference.py


**📈 Résultats**

Le modèle génère des courbes de précision (mAP) et une matrice de confusion disponibles dans le dossier runs/ après l'entraînement.

Note importante : Les dossiers dataset/, data/ et runs/ sont listés dans le fichier .gitignore car ils sont trop volumineux pour être hébergés sur GitHub.
