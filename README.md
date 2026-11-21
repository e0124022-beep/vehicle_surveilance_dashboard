# 🚗 Deep Learning-Based Intelligent Vehicle Surveillance System

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-green.svg)
![React](https://img.shields.io/badge/React-18-61DAFB.svg)
![TypeScript](https://img.shields.io/badge/TypeScript-5-blue.svg)
![YOLO](https://img.shields.io/badge/YOLO11-Object%20Detection-purple.svg)
![EasyOCR](https://img.shields.io/badge/EasyOCR-ANPR-orange.svg)

## 📌 Project Overview

The Deep Learning-Based Intelligent Vehicle Surveillance System is an intelligent vehicle monitoring platform designed to detect vehicles, recognize Indian vehicle registration numbers, track vehicle identities, and identify unauthorized or suspicious vehicles.

The system combines deep learning, computer vision, Optical Character Recognition (OCR), and multi-frame validation techniques to provide an integrated vehicle surveillance dashboard.

It includes an interactive web interface for exploring vehicle datasets, performing number plate recognition, managing watchlists, monitoring alerts, and evaluating OCR performance.

The project uses YOLO11n for vehicle detection, ByteTrack as part of the proposed tracking pipeline, and EasyOCR for automatic number plate recognition.

## ✨ Key Features

### 1. Vehicle Surveillance Dashboard
- Interactive overview dashboard.
- Vehicle monitoring statistics.
- Processing pipeline visualization.
- Dataset statistics and OCR performance indicators.
- Recent alert information.

### 2. Automatic Number Plate Recognition (ANPR)
- Upload vehicle or number plate images.
- Extract Indian vehicle registration numbers using EasyOCR.
- Apply multiple image preprocessing techniques.
- Perform character correction based on Indian number plate formats.
- Display OCR confidence scores.
- Identify valid and invalid registration number formats.

### 3. Multi-Frame Validation
- Simulates repeated OCR observations across video frames.
- Uses confidence-based filtering.
- Implements majority-voting validation.
- Compares recognition performance across different frame windows.
- Visualizes false-decision rates.

### 4. Dataset Explorer
- Explore annotated Indian vehicle number plate images.
- View dataset statistics.
- Search registration numbers.
- Filter images by dataset source.
- Display original images and plate crops.
- Analyze state-code distributions.

### 5. Watchlist Management
- Display authorized, unknown, and watchlist vehicle categories.
- Identify vehicles with predefined watchlist status.
- Explore vehicle registration information.

### 6. Alert Monitoring
- Display vehicle alert records.
- Identify unknown and watchlisted vehicles.
- Present alert status and associated information.
- Simulate notification messages.

### 7. OCR Evaluation
- Evaluate OCR performance using annotated number plate images.
- Calculate exact-match accuracy.
- Calculate character-level accuracy.
- Measure average OCR processing time.
- Display sample recognition errors.

## 🧠 Technologies and Algorithms

| Component | Technology |
|---|---|
| Vehicle Detection | YOLO11n |
| Object Tracking Pipeline | ByteTrack |
| Number Plate Recognition | EasyOCR |
| Image Processing | OpenCV |
| Image Enhancement | CLAHE, Bilateral Filtering, Sharpening |
| Thresholding | Otsu and Adaptive Thresholding |
| Character Correction | Position-based character correction |
| Multi-Frame Validation | Majority Voting |
| Backend | Python, FastAPI |
| Frontend | React, TypeScript, Vite |
| Database | SQLite, SQLModel |
| Data Processing | NumPy, Pandas |
| Visualization | Recharts |
| Testing | Pytest, Vitest |

## ⚙️ System Architecture

The proposed surveillance pipeline consists of the following stages:

1. Camera or vehicle image input.
2. Vehicle detection using YOLO11n.
3. Vehicle tracking using ByteTrack.
4. Number plate localization.
5. Image preprocessing and enhancement.
6. Text recognition using EasyOCR.
7. Indian number plate format validation.
8. Multi-frame majority-voting validation.
9. Watchlist database comparison.
10. Alert generation and dashboard visualization.

**Note:** The current ZIP includes a working image-based ANPR API and dashboard components. Full live camera processing and integrated YOLO11n + ByteTrack inference are not yet connected to the frontend.

## 📂 Project Structure

```text
vehicle_surveillance_project/
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   │
│   │   ├── api/
│   │   │   └── v1/
│   │   │       ├── router.py
│   │   │       ├── health.py
│   │   │       ├── anpr.py
│   │   │       └── datasets.py
│   │   │
│   │   ├── core/
│   │   │   ├── config.py
│   │   │   └── logging.py
│   │   │
│   │   ├── models/
│   │   │   ├── common.py
│   │   │   └── health.py
│   │   │
│   │   └── services/
│   │       ├── ocr.py
│   │       └── plates.py
│   │
│   ├── scripts/
│   │   └── evaluate_ocr.py
│   │
│   ├── tests/
│   │
│   ├── requirements.txt
│   └── pyproject.toml
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── layout/
│   │   │   ├── shared/
│   │   │   └── ui/
│   │   │
│   │   ├── hooks/
│   │   ├── lib/
│   │   ├── pages/
│   │   │   ├── Overview.tsx
│   │   │   ├── AnprLab.tsx
│   │   │   ├── ValidationSimulator.tsx
│   │   │   ├── DatasetExplorer.tsx
│   │   │   ├── Watchlist.tsx
│   │   │   ├── Alerts.tsx
│   │   │   ├── Detection.tsx
│   │   │   ├── Evaluation.tsx
│   │   │   └── ComingSoon.tsx
│   │   │
│   │   ├── App.tsx
│   │   ├── main.tsx
│   │   └── router.tsx
│   │
│   ├── package.json
│   └── vite.config.ts
│
├── .env
├── Makefile
├── package.json
└── README.md
```

## 💻 Prerequisites

Install the following software before running the application:

- Python 3.10–3.12
- Node.js 18 or above
- npm 9 or above
- Git (optional)
- NVIDIA GPU with CUDA support (optional)

The application supports CPU execution when CUDA is unavailable.

## 🚀 Installation and Setup

### Step 1: Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd p
```

Alternatively, extract the downloaded project ZIP and open a terminal in its root directory.

### Step 2: Create a Python Virtual Environment

**Windows PowerShell:**

```powershell
python -m venv backend/.venv
backend/.venv/Scripts/Activate.ps1
```

**Windows Command Prompt:**

```bat
python -m venv backend/.venv
backend\.venv\Scripts\activate.bat
```

**Linux/macOS:**

```bash
python3 -m venv backend/.venv
source backend/.venv/bin/activate
```

### Step 3: Install Backend Dependencies

From the project root:

```bash
pip install -r backend/requirements.txt
```

For real ANPR functionality, ensure EasyOCR and OpenCV are installed.

The first EasyOCR execution may download pretrained model weights.

### Step 4: Install Frontend Dependencies

```bash
cd frontend
npm install
cd ..
```

### Step 5: Install Root Dependencies

```bash
npm install
```

### Step 6: Configure Environment Variables

The project includes a `.env` configuration file.

Important settings:

| Variable | Default | Description |
|---|---|---|
| APP_ENV | development | Application environment |
| DEBUG | true | Enables development API documentation |
| DEMO_MODE | true | Skips ML model loading during startup |
| BACKEND_PORT | 8000 | Backend port |
| FRONTEND_PORT | 5173 | Frontend port |
| YOLO_MODEL_PATH | yolo11n.pt | YOLO model path |
| YOLO_CONFIDENCE | 0.5 | Detection confidence |
| DEVICE | auto | CPU/GPU selection |
| MAX_UPLOAD_SIZE_MB | 10 | Maximum image upload size |

Keep secrets and machine-specific configuration out of public GitHub commits.

## ▶️ Running the Application

### Option 1: Start Both Servers

From the project root:

```bash
npm run dev
```

This starts the backend and frontend together.

**Backend:**
http://localhost:8000

**Frontend:**
http://localhost:5173

### Option 2: Run Backend Separately

Open a terminal:

```bash
cd backend
python -m uvicorn app.main:app --reload --port 8000
```

Backend API:

http://localhost:8000

Swagger API documentation:

http://localhost:8000/docs

### Option 3: Run Frontend Separately

Open another terminal:

```bash
cd frontend
npm run dev
```

Open the application:

http://localhost:5173

## 🔍 Automatic Number Plate Recognition

The ANPR module uses EasyOCR with multiple preprocessing techniques to improve text recognition.

### Image Preprocessing Techniques

1. Grayscale conversion.
2. Image resizing using cubic interpolation.
3. Bilateral filtering.
4. Contrast enhancement using CLAHE.
5. Image sharpening.
6. Otsu thresholding.
7. Adaptive Gaussian thresholding.

### Indian Number Plate Format

The recognition module validates the extracted text using the following general pattern:

```text
AA 00 AA 0000
```

Example:

```text
TN01AB1234
```

The extracted number is divided into:

- State code: TN
- RTO code: 01
- Series: AB
- Registration number: 1234

Position-based character correction is applied to reduce common OCR errors, such as confusing O with 0 and I with 1.

## 🔌 API Endpoints

The backend provides REST API endpoints.

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/v1/health` | Check backend and model health |
| GET | `/api/v1/config` | Retrieve runtime configuration |
| POST | `/api/v1/anpr` | Recognize an uploaded number plate |
| GET | `/api/v1/datasets/plates/stats` | Retrieve plate dataset statistics |
| GET | `/api/v1/datasets/plates/items` | Retrieve paginated plate records |
| GET | `/api/v1/datasets/plates/image` | Retrieve dataset image or crop |
| GET | `/api/v1/eval/ocr` | Retrieve OCR evaluation results |

Interactive API documentation:

http://localhost:8000/docs

### Example ANPR Request

```bash
curl -X POST "http://localhost:8000/api/v1/anpr" \
  -H "accept: application/json" \
  -F "file=@vehicle.jpg"
```

The API returns:

- OCR candidates for each preprocessing variant.
- Original recognized text.
- Corrected text.
- Recognition confidence.
- Indian number plate format validity.
- Best recognized registration number.
- Extracted registration components.

## 📊 OCR Evaluation

The project includes an OCR evaluation script for testing recognition performance on annotated Indian number plate images.

Run the evaluation from the backend directory:

```bash
python -m scripts.evaluate_ocr --n 50
```

For a smaller initial test:

```bash
python -m scripts.evaluate_ocr --n 5
```

Evaluation metrics include:

- Exact-match accuracy.
- Character accuracy.
- Average processing latency.
- Recognition failure examples.

The results are saved to:

```text
vehicle_surveillance_project/
└── outputs/
    └── ocr_eval.json
```

The frontend Evaluation page retrieves these results from the backend.

## 🧪 Testing

### Backend Tests

```bash
cd backend
python -m pytest tests/ -v
```

### Frontend Tests

```bash
cd frontend
npx vitest --run
```

### Run All Tests

From the project root:

```bash
npm run test
```

## 📈 Dashboard Modules

| Module | Purpose |
|---|---|
| Overview | Displays system statistics and processing pipeline |
| ANPR Lab | Performs image-based number plate recognition |
| Validation Simulator | Demonstrates multi-frame majority-voting validation |
| Dataset Explorer | Explores annotated Indian number plate datasets |
| Watchlist | Displays vehicle authorization categories |
| Alerts | Displays vehicle alert information |
| Detection & Tracking | Demonstrates vehicle detection and tracking analytics |
| Evaluation | Displays OCR evaluation results |

## 🔐 Privacy and Ethical Considerations

This project is developed for academic and research purposes.

- Vehicle images and registration information should be handled responsibly.
- Use datasets only when their licensing and usage terms permit it.
- Surveillance deployment must comply with applicable privacy and data protection laws.
- Access to vehicle information should be restricted to authorized users.
- Data retention should follow appropriate institutional policies.
- Simulated alerts must not be mistaken for actual notifications.

**SMS notifications in the current project are simulated only. No real SMS messages are sent.**

## ⚠️ Current Implementation Status

| Component | Status |
|---|---|
| React dashboard | Implemented |
| FastAPI backend | Implemented |
| Image-based ANPR using EasyOCR | Implemented |
| Multi-variant image preprocessing | Implemented |
| Indian plate format correction | Implemented |
| OCR evaluation script | Implemented |
| Dataset exploration API | Implemented |
| Multi-frame validation | Simulation |
| Watchlist and alerts | Demonstration data |
| YOLO11n live detection integration | Not yet connected |
| ByteTrack live tracking integration | Not yet connected |
| Live camera surveillance | Not yet connected |
| Real SMS notifications | Not implemented |

## 🎯 Future Enhancements

- Real-time CCTV video processing.
- Complete YOLO11n and ByteTrack integration.
- Automatic number plate localization.
- Persistent vehicle tracking across video frames.
- Database-backed vehicle watchlist management.
- Real-time alert notifications.
- Multi-camera surveillance.
- Improved OCR accuracy under low-light and motion-blur conditions.
- Role-based access control and audit logging.

## 📄 License

This project is developed for academic and educational purposes. Add an appropriate license before distributing the source code publicly.
