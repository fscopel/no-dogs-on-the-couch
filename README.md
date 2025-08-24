# Project Goals

The main goal of this project is to **train the dogs not to be on the couch when humans are not present**.

Dogs are allowed on the couch only when humans are also on it. If the dogs are on the couch by themselves, the system should detect it and trigger a response.

---

## Project Phases

### Phase 1: Data Collection & Training

- Use a **Raspberry Pi Zero 2** with a camera to gather images of:
  - Couch with dogs
  - Couch without dogs
  - Couch with humans
  - Couch with both humans and dogs
- These images will be used to build a dataset for training.
- Training will take place in **Azure**, leveraging cloud resources to build the initial detection model.

### Phase 2: Model Deployment

- Once trained, the model will be downloaded and deployed.
- Deployment will happen in two stages:

#### Stage 1: Local Desktop Deployment

- A **web service** will run on the local desktop PC (NVIDIA RTX 3090).
- The Raspberry Pi Zero 2 will:
  - Capture live images of the couch.
  - Send them to the desktop web service for analysis.
  - Receive detection results back.
  - If the dogs are detected on the couch without humans, trigger the **speaker** to emit a **beep**.

#### Stage 2: Raspberry Pi 5 Deployment

- The **same web service** will later run on the **Raspberry Pi 5 with an AI Hat**.
- The Raspberry Pi Zero 2 will continue to handle:
  - Image capture
  - Sending images to the Pi 5 web service
  - Receiving results and triggering the speaker

---

## Technical Stack

- **Data Collection:** Raspberry Pi Zero 2 + camera
- **Model Training:** Azure AI/ML
- **Inference / Web Service:**
  - Stage 1: Local desktop with NVIDIA RTX 3090
  - Stage 2: Raspberry Pi 5 with AI Hat
- **Signal / Feedback:** Raspberry Pi Zero 2 with attached speaker
