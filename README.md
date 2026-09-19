[README.md](https://github.com/user-attachments/files/32415230/README.md)
# emotion_detection# Watson NLP Emotion Detector

A Flask application that sends text to the Watson NLP Emotion Predict service and
returns anger, disgust, fear, joy, sadness, and the dominant emotion.

## Setup and run

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python server.py
```

Open `http://127.0.0.1:5000`. The API endpoint is
`/emotionDetector?textToAnalyze=...`; blank or invalid text returns HTTP 400.

## Quality checks

```powershell
python -m unittest -v
pylint EmotionDetection server.py test_emotion_detection.py
```

The Watson course endpoint must be reachable for live non-empty analysis. The
unit tests mock it, so they run without that external service.
