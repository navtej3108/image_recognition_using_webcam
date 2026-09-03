# Webcam Face Extraction

A Python computer vision project that captures faces from a webcam, identifies newly detected faces using face embeddings, and saves each unique face as a cropped image.

This project was originally developed during an internship in June–August 2024 as an early practical computer vision project.

## What the Project Does

The program:

1. Opens the computer's webcam.
2. Detects faces in the webcam frames.
3. Generates a face encoding (embedding) for each detected face.
4. Compares each face with previously captured face embeddings.
5. Assigns a new ID when a face is considered unique.
6. Crops and resizes the new face to `180 × 227` pixels.
7. Saves the cropped face as a JPG file.
8. Displays:
   - **Green box** — newly captured/unique face
   - **Red box** — face already detected
9. Prints the total number of faces saved when the program is stopped.

The original implementation uses a face-distance threshold of `0.6` to determine whether a detected face is unique.

## Technologies Used

- Python
- OpenCV
- dlib
- face_recognition
- NumPy

## Project Structure

```text
webcam/
│
├── extract_images_from_webcam.py
├── requirements.txt
├── README.md
└── extracted_images/
    └── face_*.jpg
```

The `extracted_images` folder is created automatically when the program runs.

## Requirements

- Python 3.12.x
- Working webcam
- Windows/macOS/Linux
- The Python packages listed in `requirements.txt`

## Installation

Create and activate a virtual environment:

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.venv\Scripts\activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

## Configuration

Before running the program, check the `new_path` variable in `extract_images_from_webcam.py`.

For Windows, for example:

```python
new_path = r'C:\Users\YourName\Desktop\webcam\extracted_images'
```

Change the path to the folder where you want the captured images to be stored.

## Running the Project

Run:

```bash
python extract_images_from_webcam.py
```

A webcam window will open.

Press **`q`** to stop the program.

## Output

Captured images are saved as JPG files using a naming pattern similar to:

```text
face_12_1.jpg
face_25_2.jpg
face_41_3.jpg
```

The numbers represent the frame counter and assigned face ID.

## How Face Uniqueness Works

The program stores the face embeddings of previously captured faces in memory.

For a newly detected face, it calculates the face distance against the stored embeddings. If all distances are greater than or equal to `0.6`, the face is treated as unique and saved.

This means the project is designed to avoid repeatedly saving the same detected face while the program is running.

## Important Limitations

- Face recognition depends on the quality and position of the face in the webcam frame.
- Lighting, camera angle, distance, and facial appearance can affect recognition.
- The face embeddings are stored only while the program is running; they are not saved to a database.
- The project does not provide persistent identity management.
- The original implementation uses a hard-coded image output path, which should be changed for the user's computer.
- The project was an early practical implementation and is not intended to represent a production-grade face-recognition system.

## Learning Outcomes

This project provided practical experience with:

- Webcam video capture using OpenCV
- Face detection
- Face embeddings and face-distance comparison
- Image cropping and resizing
- Saving images programmatically
- Working with Python computer vision libraries
- Basic handling of real-time video processing

## Future Improvements

Possible improvements include:

- Store face embeddings persistently.
- Add a proper person/identity database.
- Improve face detection and recognition accuracy.
- Add configuration instead of hard-coded paths.
- Add a user interface for managing captured faces.
- Improve performance by processing selected frames instead of every frame.
- Add logging and better error handling.

## License

This project is provided for educational and portfolio purposes.
