# Face Recognition System 👨‍💼

This repository implements a face recognition system capable of identifying known faces in real time. It utilizes cutting-edge techniques for image processing and vector encoding, enabling fast and accurate facial identification.

 It consists of two files:
 
1. face_rec.py: Defines a class for encoding and detecting faces.

2. main.py: Implements the real-time face recognition system using a webcam.


# What is Face Recognition? 🤔

Face recognition is a biometric technology that identifies or verifies a person by analyzing facial features.

## 🔍 Core Processes

1. Face Detection: Locate faces in an image or video frame.

2. Feature Encoding: Convert the face into a numerical vector representation.

3. Face Matching: Compare encoded features with stored data to identify the person.

# 🔍 Difference Between Face Recognition and Face Verification

![Image](https://github.com/user-attachments/assets/073bace7-e0ab-4794-a003-eb1c1fc1cbcf)

# How Face Recognition Works 🚀

The face recognition system in this repository follows these steps:

## 1. Face Encoding

Each face is encoded into a numerical vector using a pre-trained model from face_recognition. This vector represents the unique features of the face, such as the distance between eyes, nose shape, and jawline.

Key Concept:

The encoding process is like creating a unique fingerprint for every face but in the form of a vector.

## 2. Comparison Using Distance Metrics
   
When a new face is detected, the system computes the distance between the new face's vector and the vectors of known faces in the database.

The system calculates the distance between this new embedding and the embeddings of known faces stored in the database.

Euclidean Distance (or sometimes Cosine Similarity) is a standard metric for comparing embeddings.

  • Euclidean Distance measures the straight-line distance between two points in the vector space.
  
  • Cosine Similarity measures the angle between two vectors, which can also be used depending on the application.

If the distance is below a certain threshold, the system determines that the face matches one in the database.

## 3. Thresholding

The threshold value is crucial:

Low threshold: Reduces false positives but might miss valid matches.
High threshold: Increases sensitivity but may lead to false matches.
For example:

Threshold = 0.3

If the distance = 0.2, the faces match.

If the distance = 0.7, the faces don’t match.


# Code Breakdown 🔧 

## File 1: face_rec.py


1. load_encoding_images()

  • Loads images from a folder.

  • Converts them to RGB format.

  • Encodes each image into a numerical vector and stores it.

📂 Input: Image folder path.

📊 Output: Encoded vectors and corresponding names.



2. detect_known_faces()

• Detects faces in real-time video.

• Resizes the frame for faster processing.

• Encodes the detected face and compares it with known encodings.

• Returns the names of recognized faces.


## File 2: main.py

1. Encodes Faces

• Uses the Face_Recognition class to encode images in the images/ folder.

2. Real-Time Detection

•  Captures video using the webcam.

• Identifies and displays names of recognized faces.


🖼️ Detected faces are displayed with a rectangle and a name label.

3. Exit Condition

• Press the ESC key to exit the application.



# Technical Insights 📊 
## 🔧 Libraries Used

### • face_recognition:

Generates face encodings and performs matching.

Utilizes a pre-trained model for feature extraction.

### • OpenCV:

Handles video frame capture and visualization.




# Highlights of the System 🌟 

### • High Accuracy:

Uses advanced encoding and matching techniques for reliable recognition.

### • Modular and Scalable:

The system design allows easy addition or removal of known faces from the database.

### • Optimized Performance:

Video frames are resized for faster processing without compromising accuracy.


# Applications 💡

• Security and Surveillance:
Monitor and identify individuals in restricted areas.

• Attendance Systems:
Automate attendance tracking in schools, offices, and events.

• Authentication Systems:
Enable face-based login for devices or platforms.

# Challenges and Limitations 🎯
1. Lighting Conditions: Recognition accuracy may decrease in poor lighting.

2. Angles and Occlusions: Faces turned away or partially covered might not be recognized.

3. Threshold Tuning: Finding the optimal threshold for specific use cases can be tricky.
