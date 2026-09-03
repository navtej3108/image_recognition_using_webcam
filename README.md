# Webcam Face Recognition

A Python-based real-time face recognition project that uses a webcam to detect faces and identify a known person from a reference image.

## Project Background

This project was developed during my internship from **June 2024 to August 2024** as part of my early practical experience with Python, computer vision, and face recognition.

The project helped me understand how computer vision applications are built in practice and gave me a foundation for working on several similar Python and computer-vision projects afterward.

> **Note:** This repository contains an early project from 2024. It is being published later to document my learning journey and earlier practical work.

## What the Project Does

The application:

1. Opens the computer's webcam.
2. Captures video frames in real time.
3. Resizes frames to make face processing faster.
4. Converts the frame from OpenCV's BGR format to RGB.
5. Detects faces in the video frame.
6. Generates a face encoding for each detected face.
7. Compares the detected face with the stored reference face encoding.
8. Displays a bounding box and the person's name when a match is found.
9. Displays `Unknown` when the detected face does not match the known face.

The current example uses an image of **Elon Musk** as the known reference face.

## Technologies Used

- **Python 3.12**
- **OpenCV** — webcam access, video processing, resizing, drawing, and displaying frames
- **face-recognition** — face detection, face encoding, and face comparison
- **dlib** — underlying machine-learning/computer-vision functionality used by `face-recognition`
- **NumPy** — numerical operations and face-distance comparison

## Project Structure

```text
webcam/
│
├── Elon Musk.png
├── facerec_from_webcam_faster.py
├── requirements.txt
└── README.md
```

### Files

**`facerec_from_webcam_faster.py`**  
The main Python program that performs real-time face recognition using the webcam.

**`Elon Musk.png`**  
The reference image used to create the known face encoding.

**`requirements.txt`**  
Contains the Python package versions required to recreate the project environment.

**`README.md`**  
Project documentation and setup instructions.

## How Face Recognition Works

The project does not compare the webcam image directly with the reference image pixel-by-pixel.

Instead, the reference image is converted into a numerical **face encoding**. When a face is detected through the webcam, that face is also converted into an encoding.

The two encodings are then compared to determine whether the detected face is sufficiently similar to the known face.

Conceptually:

```text
Reference Image
      ↓
Face Detection
      ↓
Face Encoding
      ↓
Known Face Encoding
                           → Compare → Match / Unknown
             /
Webcam Frame
      ↓
Face Detection
      ↓
Face Encoding
```

## Setup

### 1. Install Python

The project was restored and tested using:

```text
Python 3.12.10
```

Python 3.12 is recommended for reproducing the tested environment.

### 2. Create a virtual environment

From the project directory:

```bash
py -3.12 -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

Install the packages listed in `requirements.txt`:

```bash
python -m pip install -r requirements.txt
```

### 4. Run the program

Make sure the reference image is available in the project directory, then run:

```bash
python facerec_from_webcam_faster.py
```

A webcam window should open.

The program will attempt to identify the face using the reference image.

Press **`q`** to exit the application.

## Important Notes

- The application requires access to a working webcam.
- The reference image must contain a detectable face.
- The example program currently uses one known face.
- Recognition accuracy can depend on lighting, camera quality, face angle, image quality, and other environmental conditions.
- The original 2024 project used a Windows-specific absolute path for the reference image. The project can be made more portable by using a path relative to the project directory.

## Learning Outcomes

Through this project, I gained practical experience with:

- Python project setup and virtual environments
- Webcam access using OpenCV
- Image and video-frame processing
- Face detection
- Face encodings
- Comparing facial features
- Real-time computer vision
- Working with third-party Python libraries
- Debugging dependency and environment issues

This project became part of my early practical experience and helped me approach and build other Python and computer-vision projects.

## Future Improvements

Possible improvements include:

- Supporting multiple known people
- Loading known faces from a dedicated folder
- Using relative paths instead of hard-coded Windows paths
- Adding a user interface
- Improving recognition speed
- Adding configurable recognition thresholds
- Storing recognition events
- Improving error handling and camera selection

## Author

**Navtej Pawan**

BTech Computer Science and Information Technology

This repository documents an early computer-vision project developed during my internship in **June 2024 – August 2024**.
al-time face recognition using the webcam.
