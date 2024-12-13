# HIRA-Hear-Assistant-
HIRA (HearAssist for Real-time Accessibility) is a mobile app that helps Deaf and Hard of Hearing (D/HH) employees in cafes by transcribing spoken orders into text instantly. Using speech-to-text technology, HIRA enables D/HH individuals to understand customer requests, promoting inclusivity and independence in customer service roles.
This IS our Cloud Architectrue
![image](https://github.com/user-attachments/assets/f8108738-99d0-45cb-81e0-ad9fffbac271)


1. User Layer (Interface System)
User 1 (Desktop): The end user interacts with the system using a desktop interface.
Frontend (App Engine): A web-based frontend hosted on Google App Engine. This component allows users to record or upload audio files.
Record Audio: A feature enabling users to record audio directly via the interface.
Attribute Name: An input field where users can assign attributes or names to their uploaded data.
2. Backend Layer
Backend (Cloud Run): The backend service runs on Google Cloud Run. It handles user requests, such as processing uploaded or recorded audio files.
Model (Cloud Run): A separate containerized service running on Cloud Run, which performs audio processing or analysis using a machine learning model. The model is implemented using TensorFlow.
3. Infrastructure System
TensorFlow: A machine learning framework used to develop and run the AI/ML model for tasks like audio transcription or other audio processing.
Cloud IAM (Identity and Access Management): IAM is used to manage and control access to cloud services and resources. It ensures that only authorized users or components can access sensitive resources, such as storage buckets and AI models.
Bucket-Hira (Cloud Storage): An object storage service used to store audio files and processing results. The bucket is organized into the following folders:
Uploads: Stores files uploaded by the user.
Audio-uploads: Stores audio files recorded or uploaded through the frontend.
Transcribed-audio: Contains transcription results of the audio files processed by the ML model.
Model-Hira: Likely stores the AI model or related files.
Data Flow
The user accesses the frontend (App Engine) via their desktop.
The user records or uploads audio, which is sent to the Backend (Cloud Run).
The backend validates the input and stores the audio file in Bucket-Hira (Cloud Storage), specifically in the "Audio-uploads" folder.
The stored audio file is processed by the ML Model (Cloud Run) using TensorFlow.
The processing result (e.g., transcription) is saved back to Bucket-Hira, particularly in the "Transcribed-audio" folder.
Cloud IAM ensures secure access to all resources, including the storage bucket and the ML model.
This architecture is designed using a serverless approach (Cloud Run and App Engine) for scalability, cost efficiency, and ease of management
Our Buckte:
![image](https://github.com/user-attachments/assets/7743780d-0129-49c2-acf4-7c264ff6312b)

Our Cloud Run:
![image](https://github.com/user-attachments/assets/a035011a-007a-4a4f-9d1e-8bb54029b4e6)

Our App engine
![image](https://github.com/user-attachments/assets/b58be78c-96a4-411f-8dbf-37eb703b701f)

END POINT BACKEND: https://backend-877036409345.asia-southeast2.run.app
END POINT MODEL:https://model-api-877036409345.asia-southeast2.run.app
