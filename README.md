# Driver Drowsiness Detection

This project uses computer vision and deep learning to detect driver drowsiness in real time via webcam. When drowsiness is detected, an audible alarm sounds to alert the driver.

## Features

- Detects closed and open eyes using a CNN model.
- Real-time face and eye detection with OpenCV and Haar Cascades.
- Plays an alarm if drowsiness is detected.
- Saves a snapshot when drowsiness is detected.

## Folder Structure

| File/Folder                  | Description                                         |
|------------------------------|-----------------------------------------------------|
| `drowsiness-detection.py`    | Main script for real-time detection and alert.      |
| `model.py`                   | Script to train the CNN model for eye state.        |
| `models/cnncat2.h5`          | Pre-trained CNN model for eye state classification. |
| `alarm.wav`                  | Alarm sound played when drowsiness is detected.     |
| `haar cascade files/`        | Haar Cascade XMLs for face and eye detection.       |
| `data/`                      | Training and validation image data.                 |

## Requirements

- Python 3.x
- OpenCV
- Keras
- TensorFlow
- NumPy
- pygame

Install dependencies using:
```
pip install opencv-python keras tensorflow numpy pygame
```

## Usage

1. **Clone the repository** and ensure all required files are present.
2. **Run the main detection script:**

    ```
    python drowsiness-detection.py
    ```

3. The webcam will activate. If both eyes are detected as closed for a sustained period, an alarm will sound and a snapshot will be saved.

## Training the Model

- To retrain the model, organize your dataset under `data/train` and `data/valid` with subfolders for each class (`Open`, `Closed`).
- Run:

    ```
    python model.py
    ```

- The trained model will be saved as `models/cnncat2.h5`.

## Notes

- Ensure your webcam is connected.
- Place the Haar Cascade XML files in the correct folder (`haar cascade files/`).
- The alarm will only sound if drowsiness is detected continuously (score > 15).
