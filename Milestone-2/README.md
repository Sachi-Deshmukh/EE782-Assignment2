As a part of Milestone-2 we have done the following things:

- Implemented **face detection and recognition** using the `face_recognition` and `OpenCV` libraries.  
- Created a **trusted_faces** folder to enroll 2 trusted users by storing their images.  
- Generated and saved **face embeddings** to compare with live webcam detections.  
- When a face is detected, the system **greets trusted users** and **flags unrecognized faces**.  
- Comparison is based on **Euclidean distance** between embeddings with a fixed tolerance value.  
- Tested across different **lighting conditions and angles** to ensure accuracy and robustness.
