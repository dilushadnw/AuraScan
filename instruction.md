# Project: AI Facial Analysis & Style Advisor

## 1. Overview
Create a real-time web application using Vanilla JS and face-api.js that detects a user's face shape and current emotion to provide personalized grooming and mood-based styling tips.

## 2. Technical Requirements
- **Core Library:** face-api.js (via CDN).
- **Styling:** Tailwind CSS (via CDN).
- **Detection Models:** - `tinyFaceDetector` (for speed)
  - `faceLandmark68Net` (for face shape calculation)
  - `faceExpressionNet` (for mood detection)
- **Environment:** Must run on VS Code Live Server (Localhost).

## 3. Core Features & Logic
### A. Face Shape Detection
- Track 68 landmarks in real-time.
- Use Euclidean distance to calculate:
  - Forehead Width (Landmarks 17-26 distance)
  - Cheekbone Width (Landmarks 1-15 distance)
  - Jawline Width (Landmarks 5-11 distance)
  - Face Length (Landmark 8 to the top point)
- Classify into: **Oval, Round, Square, Heart, or Diamond**.

### B. Emotion & Mood Detection (New)
- Detect emotions: **Happy, Sad, Neutral, Angry, Surprised, Disgusted**.
- Display the current mood prominently with an emoji.

### C. Recommendation Engine
- Provide a curated list of:
  - **Hairstyles** (based on face shape)
  - **Beard Styles** (based on jawline and face shape)
  - **Mood Tips** (e.g., if 'Sad', suggest a fresh cut to cheer up; if 'Angry', suggest a calming style).

## 4. UI/UX Requirements
- **Split Screen:** - **Left Side:** Webcam feed with a Canvas overlay showing landmarks.
  - **Right Side:** A dashboard showing:
    - Detected Shape (e.g., "Shape: Oval")
    - Detected Emotion (e.g., "Mood: Happy 😊")
    - Recommended Styles (using clean cards/lists).
- **Screenshot Feature:** A 'Capture' button to save the recommendation as an image.
- **Visual Guides:** Draw a geometric shape (SVG/Canvas) around the face that matches the detected face shape.

## 5. Deliverables
- A single `index.html` with integrated CSS/JS.
- Clear code comments explaining the geometric ratios used for shape detection.
- A loading overlay that disappears only after all 3 models are loaded.