# AI Guard Agent: EE782 Assignment 2

This repository contains all code files and videos of Assignment-2 for EE782-Introduction to Advanced Topics in Machine Learning course. This repo is created by Sachi Deshmukh (22B1213) and Yashomati Sarnaik (22B1259).

## Project Overview

This repository implements the **AI Guard Agent**, a real-time multimodal AI system for room security developed for EE782: Advanced Topics in Machine Learning Programming Assignment 2. The agent activates via voice command ("Guard my room"), monitors the room with a webcam for face recognition, welcomes trusted users, and escalates interactions with untrusted individuals through an intelligent dialogue system powered by an LLM and TTS. It integrates computer vision, speech processing, and natural language generation for a robust, privacy-focused security solution.

Core features:
- **Voice Activation**: Offline-capable listening for activation using SpeechRecognition with Google Web Speech API.
- **Face Recognition**: Enrollment and verification of 1-2 trusted users via `face_recognition` library (embedding-based, no training required).
- **Escalation Dialogue**: 3-level conversation using Google Gemini (free tier) for natural, polite responses, with ASR for replies.
- **TTS Responses**: Audio output via gTTS and pygame for spoken interactions.
- **Enhancements**: Multi-face tracking with visual bounding boxes (green for trusted, red for untrusted) and persistence alerts (>10s linger triggers warning). Customizable email notifications for level-3 escalations (SMTP with Gmail App Passwords).

The system runs locally on a laptop with webcam/microphone, prioritizing free tools, ethical data use (consented photos/voice only), and robustness (e.g., fallbacks for API failures).

## System Architecture

The agent uses a state-based pipeline:

1. **Activation**: Microphone input → SpeechRecognition → Command match → Set `guard_mode=True`.
2. **Monitoring**: Webcam frames → OpenCV capture → `face_recognition` encodings → Match against `trusted_embeddings.npy`.
3. **Response Logic**:
   - Trusted: TTS welcome.
   - Untrusted: LLM prompt → Gemini response → TTS play → ASR reply check → Escalate levels.
4. **Enhancements**:
   - Tracking: Dictionary-based ID assignment with timestamps for multi-face.
   - Alerts: JSON config → SMTP email with snapshot at level 3.


Link for video with code explanation and model demonstration: https://drive.google.com/file/d/1-VCyDVmfYQjQGqbmHPCgi07A8X6je-PA/view?usp=sharing
