# Pipeline d'analyse OpenFace et DTW

Ce dépôt contient un pipeline complet pour extraire, traiter et analyser des données faciales à l'aide d'OpenFace, NumPy et la distance de Dynamic Time Warping (DTW). Le pipeline couvre :

- Extraction des features depuis des vidéos à l'aide d'OpenFace.

- Conversion des fichiers CSV générés en tableaux NumPy (.npy).

- Normalisation des tableaux NumPy (z-score).

-Analyse DTW causale pour mesurer l'imitation faciale entre un robot et plusieurs participants.

- Visualisations : courbes temporelles, heatmaps DTWD/DTWI et alignements.

## Prérequis

Système d'exploitation : Windows (pour l’exécutable FeatureExtraction.exe) ou adaptation sous Linux/Mac.

Python 3.8+

### Bibliothèques Python :

- numpy

- pandas

- matplotlib

- seaborn

- dtaidistance

pip install numpy pandas matplotlib seaborn dtaidistance

OpenFace : 
Instalation: https://github.com/TadasBaltrusaitis/OpenFace/wiki


## Configuration

Avant de lancer les scripts, modifier les chemins dans data_preparation.py :

# Chemin vers le dossier OpenFace
OPENFACE_DIR = Path("/chemin/vers/OpenFace")
# Dossier contenant vos vidéos
VIDEOS_DIR   = Path("/chemin/vers/videos")
# Fichiers de sortie
CSV_DIR      = VIDEOS_DIR / "openface_csv"
NUMPY_DIR    = VIDEOS_DIR / "openface_numpy"

Dans dtw_analysis.py, adapter si nécessaire la fréquence d'images (fps) et le délai maximal (delay_sec).



# Résultats

results_df : DataFrame contenant pour chaque participant :

DTWD_causal : distance DTW multidimensionnelle.

DTWI_causal : distance DTW unidimensionnelle (moyenne).

score_causal : ratio DTWD / (DTWI + ε).

Graphiques sauvegardés ou affichés à l'écran.

Personnalisation

Colonnes AU : modifier la liste AU_COLS pour ajouter/supprimer des Action Units.

Format vidéo : adapter les extensions supportées dans extract_openface_features().

# Licence

Ce projet est distribué sous licence MIT. Voir le fichier LICENSE pour plus de détails.
- Licence du projet : Ce projet est distribué sous licence MIT. 
- Licence d'OpenFace :
    OpenFace est distribué sous Apache License, Version 2.0. Pour citer et respecter cette licence, ajoutez dans vos documents la mention suivante :

    OpenFace est licencié sous Apache License 2.0 ; voir http://www.apache.org/licenses/LICENSE-2.0[^2]

    Vous pouvez également inclure ce bloc dans vos rapports :
        Copyright (c) 2015 – Carnegie Mellon University
        Licensed under the Apache License, Version 2.0 (the "License");
        you may not use this file except in compliance with the License.
        You may obtain a copy of the License at

            http://www.apache.org/licenses/LICENSE-2.0