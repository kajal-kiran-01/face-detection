# Real-Time Emotion Detection with Face Recognition

This Python script uses OpenCV and DeepFace to perform real-time emotion detection from a video stream. The script captures video from a webcam, detects faces in each frame, and then analyzes the facial expressions to predict the dominant emotion. The detected emotion is displayed on the screen along with the face bounding box.

## Requirements

- Python 3.x
- OpenCV
- DeepFace
- Other dependencies:

You can install the required libraries using the following commands:

```bash
pip install opencv-python
pip install deepface
```

## How It Works

1. **Face Detection**: The script uses OpenCV's Haar Cascade Classifier to detect faces in the video frames. The `haarcascade_frontalface_default.xml` model is used to identify faces within the video.
   
2. **Emotion Recognition**: Once a face is detected, the script crops the face region (ROI) and sends it to the DeepFace library for emotion analysis. DeepFace uses deep learning models to predict the dominant emotion on the detected face.

3. **Live Display**: The webcam video is shown with bounding boxes around detected faces, and the dominant emotion is overlayed on the screen in real-time.

4. **Exit the Program**: Press the 'q' key to exit the video stream and close the window.

## Usage

1. Run the script:
   ```bash
   python emotion_detection.py
   ```

2. The script will open a video capture window where faces will be detected and emotions will be displayed in real-time.

3. To stop the program, simply press the 'q' key while the video capture window is active.

## Example

The script will identify emotions such as:
- Happy
- Sad
- Angry
- Surprised
- Disgust
- Fear
- Neutral

These emotions will appear as text labels on the screen above the faces as they are detected.

## Code Walkthrough

1. **Import Dependencies**: 
   - `cv2` is used for video capture, face detection, and image manipulation.
   - `DeepFace` is used for analyzing facial emotions.
   
2. **Video Capture**: 
   - The `cv2.VideoCapture(0)` function opens the webcam for capturing video.

3. **Face Detection**:
   - Faces are detected using `CascadeClassifier`, and bounding boxes are drawn on the detected faces.

4. **Emotion Analysis**:
   - DeepFace is used to analyze the detected face and predict the dominant emotion.

5. **Display**:
   - The emotion is drawn on the screen, and the updated frame is shown in a window using `cv2.imshow`.

6. **Exit Condition**:
   - The program continuously captures frames until the user presses the 'q' key.

## Troubleshooting

- If the script fails to capture video, ensure your webcam is connected and accessible.
- If DeepFace fails to analyze the face, check if the face is properly detected (adequate lighting and facing the camera are essential).
- For other errors, consult the error messages printed in the console for insights.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
