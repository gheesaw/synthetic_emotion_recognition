# synthetic_emotion_recognition

Synthetic Facial Expression Dataset

Questo progetto utilizza Blender per generare un dataset sintetico di espressioni facciali per il riconoscimento automatico delle emozioni. La generazione di immagini 3D consente di creare molteplici variazioni con annotazioni automatiche precise, superando i limiti dei dataset reali.

L’uso di un approccio sintetico permette di:

definire con esattezza le intensità delle Action Units (AU) del Facial Action Coding System (Ekman),

controllare la posizione della camera su più punti di vista,

ottenere landmark facciali perfettamente annotati e coerenti con i modelli standard (es. MediaPipe Face Mesh).

Lo script Python controlla la scena in Blender per produrre combinazioni di emozioni e posizioni camera, registrando tutte le configurazioni in file CSV organizzati secondo i landmark facciali.

Caratteristiche del dataset

Emozioni: include 7 emozioni di base (Joy, Sadness, Anger, Fear, Disgust, Surprise, Neutral) + Disprezzo.

Action Units (AU): per ogni emozione vengono attivate specifiche AU con intervalli di intensità definiti secondo Ekman.

Posizioni camera: la camera viene spostata su più vertici di una sfera attorno al volto, per simulare diversi punti di vista.

Combinazioni totali: ogni emozione × combinazioni di AU × posizioni camera = migliaia di configurazioni uniche.

Salvataggio dati: ogni configurazione viene salvata in un file CSV, con valori di:

posizione e rotazione della camera,

yaw, pitch e roll della testa,

intensità normalizzate delle AU,

coordinate 2D dei landmark facciali proiettati sull’immagine.

Landmark MediaPipe: gli indici dei punti facciali in Blender vengono mappati agli indici del MediaPipe Face Mesh (468 punti) per compatibilità con framework standard.

Strumenti

Blender: ambiente di modellazione 3D e rendering, con scripting Python integrato. Usato per gestire rigging, slider delle AU e generazione immagini/landmark.

Python (bpy): linguaggio di scripting usato all’interno di Blender per automatizzare la generazione delle espressioni e salvare i dati.

MB-Lab: add-on di Blender (derivato da Manuel Bastioni Lab) che permette di creare modelli umani 3D realistici da animare.

Installazione ed esecuzione

Per eseguire lo script:

Aprire il file .blend incluso nel progetto con Blender.

Nella sezione Scripting, caricare il codice Python fornito.

Aprire la Console di sistema di Blender (menu Window > Toggle System Console) per monitorare l’esecuzione.

Avviare lo script (premere Run Script).

A seconda del numero di combinazioni, il processo può richiedere diverse ore.

Al termine, i file CSV saranno salvati nella cartella di output configurata nello script (es. Downloads).

Output

Lo script genera come output un file CSV per ciascun modello di testa/emozione.

Ogni file contiene:

una riga di intestazione con i nomi delle colonne (AU, landmark, camera, ecc.),

migliaia di righe corrispondenti a combinazioni uniche di AU + emozione + posizione camera.

Questi file CSV possono essere usati per addestrare e valutare algoritmi di riconoscimento delle emozioni a partire dalle espressioni facciali.