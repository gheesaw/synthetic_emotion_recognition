# synthetic_emotion_recognition

Facial Expression Dataset Generator

Overview
This project uses Blender and Python to generate a synthetic facial expression dataset for emotion recognition.
The system programmatically controls facial Action Units (FACS) and camera positions to generate thousands of labeled samples with perfectly annotated facial landmarks.
This approach overcomes limitations of real datasets such as annotation errors, limited variation, and lack of ground truth.

Features

Emotions
Includes 8 emotions: Joy, Sadness, Anger, Fear, Disgust, Surprise, Neutral, and Contempt.

Action Units
Each emotion is generated using specific FACS Action Units with controlled intensity ranges based on Ekman’s model.

Camera variation
The camera moves across multiple predefined positions on a hemisphere around the face to simulate real-world viewpoints.

Landmark generation
Exports 468 facial landmarks mapped to MediaPipe Face Mesh standard.

Automatic annotation

Each sample includes:
camera position and rotation
head pose (yaw, pitch, roll)
Action Unit intensities (normalized 0–1)
2D facial landmark coordinates
High scalability
The system can generate thousands of unique labeled samples automatically.

Tech stack
Blender
Python (bpy)
MB-Lab
MediaPipe landmark mapping

Dataset size
Full dataset size: ~80GB
Due to size limitations, only sample outputs are included in this repository.

Use case

This dataset can be used for:
training emotion recognition models
facial landmark detection
computer vision research
synthetic data generation pipelines

How it works

The Python script:
controls facial rig sliders (Action Units)
moves the camera across predefined positions
renders the scene
extracts landmark coordinates
exports structured CSV files
Example output

Each CSV contains:
Action Unit intensities
head pose
camera parameters
468 facial landmark coordinates

Execution
Open the .blend file in Blender
Go to the Scripting tab
Load the Python script
Run Script
Output CSV files will be generated automatically.

Author
Marco Ghiselli

BSc Information Engineering for Video Games and Virtual Reality
Questi file CSV possono essere usati per addestrare e valutare algoritmi di riconoscimento delle emozioni a partire dalle espressioni facciali.
