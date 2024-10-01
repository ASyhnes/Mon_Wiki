


## Motion Capture
L'objectif ici est de réaliser à partir d'une vidéo une motion capture de visage

![[Insta_motion_capture.mp4|100*200]]

**Instal**

  

` codepip install mediapipe opencv-python `

MediaPipe : pour la détection des points du visage.
OpenCV : pour lire et afficher la vidéo.


```
import cv2

import mediapipe as mp

import os

import numpy as np

  

mp_face_mesh = mp.solutions.face_mesh

mp_drawing = mp.solutions.drawing_utils

  

input_video_path = 'test_visage.mp4'

cap = cv2.VideoCapture(input_video_path)

if not cap.isOpened():

    print("Erreur : Impossible d'ouvrir la vidéo.")

    exit()

  

width = int(cap.get(cv2.CAP_PROP_FRAME_WIDTH))

height = int(cap.get(cv2.CAP_PROP_FRAME_HEIGHT))

fps = int(cap.get(cv2.CAP_PROP_FPS))

  

base_name = os.path.splitext(os.path.basename(input_video_path))[0]

output_video_path = f"{base_name}_points.avi"

  

fourcc = cv2.VideoWriter_fourcc(*'XVID')

out = cv2.VideoWriter(output_video_path, fourcc, fps, (width, height))

  

with mp_face_mesh.FaceMesh(static_image_mode=False,

                            max_num_faces=1,

                            refine_landmarks=True) as face_mesh:

    while True:

        success, frame = cap.read()

        if not success:

            print("Fin de la vidéo ou problème de lecture.")

            break

  

        frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

  

        results = face_mesh.process(frame_rgb)

  

        output_frame = np.zeros((height, width, 3), dtype=np.uint8)

  

        if results.multi_face_landmarks:

            for face_landmarks in results.multi_face_landmarks:

                for landmark in face_landmarks.landmark:

                    x = int(landmark.x * width)

                    y = int(landmark.y * height)

                    cv2.circle(output_frame, (x, y), 3, (0, 255, 0), -1)  

  

        out.write(output_frame)

  

        cv2.imshow('Points de repère', output_frame)

  
  

        if cv2.waitKey(int(1000 / fps)) & 0xFF == ord('q'):

            break

  

cap.release()

out.release()  

cv2.destroyAllWindows()

  

print(f"Vidéo des points enregistrée sous : {output_video_path}")
```

## le même code avec la doc: 

```
import cv2 
 # Importation de la bibliothèque OpenCV pour la manipulation des images et des vidéos
import mediapipe as mp 
 # Importation de la bibliothèque MediaPipe pour le suivi et la détection des visages
import os 
 # Importation de la bibliothèque os pour interagir avec le système de fichiers (gestion des chemins)
import numpy as np 
 # Importation de NumPy pour la manipulation de matrices et de tableaux

# Initialisation des outils Face Mesh et Drawing de MediaPipe
mp_face_mesh = mp.solutions.face_mesh 
 # Module de MediaPipe pour détecter les points du visage (face mesh)
mp_drawing = mp.solutions.drawing_utils 
 # Module utilitaire pour dessiner sur les images (facultatif ici)

# Définition du chemin d'accès à la vidéo à traiter
input_video_path = 'test_visage.mp4'

# Ouverture de la vidéo avec OpenCV
cap = cv2.VideoCapture(input_video_path)
# Vérification si la vidéo a pu être ouverte correctement
if not cap.isOpened():
    print("Erreur : Impossible d'ouvrir la vidéo.") 
     # Message d'erreur si la vidéo ne peut pas être ouverte
    exit() 
     # Quitte le programme

# Récupération des dimensions et des informations de la vidéo
width = int(cap.get(cv2.CAP_PROP_FRAME_WIDTH)) 
 # Largeur de la vidéo
height = int(cap.get(cv2.CAP_PROP_FRAME_HEIGHT)) 
 # Hauteur de la vidéo
fps = int(cap.get(cv2.CAP_PROP_FPS)) 
 # Nombre d'images par seconde (frames per second)

# Extraction du nom de fichier de la vidéo sans l'extension
base_name = os.path.splitext(os.path.basename(input_video_path))[0]
# Création du nom pour le fichier de sortie (la vidéo avec les points faciaux tracés)
output_video_path = f"{base_name}_points.avi"

# Configuration du codec vidéo pour l'enregistrement de la nouvelle vidéo
fourcc = cv2.VideoWriter_fourcc(*'XVID') # Codec XVID utilisé pour compresser la vidéo
# Création d'un objet VideoWriter pour enregistrer la nouvelle vidéo
out = cv2.VideoWriter(output_video_path, fourcc, fps, (width, height))

# Initialisation du modèle Face Mesh de MediaPipe pour détecter les visages et leurs points
with mp_face_mesh.FaceMesh(static_image_mode=False,  # Mode vidéo (False) pour un flux en temps réel
                            max_num_faces=1,  # Limite à un seul visage à détecter
                            refine_landmarks=True) as face_mesh:  # Raffinement des points faciaux (yeux, lèvres)

    # Boucle pour traiter chaque image de la vidéo
    while True:
        success, frame = cap.read()  # Lecture d'une image (frame) depuis la vidéo
        if not success:  # Si l'image n'est pas lue correctement (fin de vidéo ou erreur)
            print("Fin de la vidéo ou problème de lecture.")  # Affiche un message
            break  # Quitte la boucle de traitement des images

        # Conversion de l'image de BGR (format par défaut d'OpenCV) en RGB (format attendu par MediaPipe)
        frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

        # Utilisation du modèle MediaPipe pour détecter les points du visage sur l'image
        results = face_mesh.process(frame_rgb)

        # Création d'une nouvelle image noire (toute noire) de même taille que l'image d'origine
        output_frame = np.zeros((height, width, 3), dtype=np.uint8)

        # Si des points faciaux ont été détectés
        if results.multi_face_landmarks:
            # Pour chaque visage détecté (ici limité à 1 visage)
            for face_landmarks in results.multi_face_landmarks:
                # Pour chaque point du visage détecté
                for landmark in face_landmarks.landmark:
                    # Conversion des coordonnées normalisées du point (entre 0 et 1) en coordonnées d'image (en pixels)
                    x = int(landmark.x * width)  # Coordonnée x du point sur l'image
                    y = int(landmark.y * height)  # Coordonnée y du point sur l'image
                    # Dessin d'un cercle vert pour chaque point sur l'image noire
                    cv2.circle(output_frame, (x, y), 3, (0, 255, 0), -1)  # Cercle vert de rayon 3 pixels

        # Enregistrement de l'image avec les points dans la vidéo de sortie
        out.write(output_frame)

        # Affichage de l'image avec les points faciaux sur une fenêtre
        cv2.imshow('Points de repère', output_frame)

        # Attente entre chaque image (selon la fréquence d'images), permet de quitter avec la touche 'q'
        if cv2.waitKey(int(1000 / fps)) & 0xFF == ord('q'):
            break  # Quitte la boucle si l'utilisateur appuie sur la touche 'q'

# Libération des ressources (fermeture des fichiers vidéo et des fenêtres)
cap.release()  # Ferme la vidéo d'entrée
out.release()  # Ferme la vidéo de sortie
cv2.destroyAllWindows()  # Ferme toutes les fenêtres ouvertes par OpenCV

# Message final indiquant où la vidéo avec les points faciaux a été sauvegardée
print(f"Vidéo des points enregistrée sous : {output_video_path}")

```

