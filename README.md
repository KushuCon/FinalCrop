# 🌾 AgriCare AI - Intelligent Crop Disease Detection System

AI-powered crop disease detection system with 99.48% accuracy using deep learning.

---

## 🚀 Quick Start

## LATEST MODEL DRIVE LINK(GITHUB NOT PUSHING MODEL DUE TO RESTRICTIONS)
- https://drive.google.com/file/d/1KszZIaQGutVbaCMVvGd-oQrVkmANfUi-/view?usp=sharing
### Prerequisites
- Python 3.11+
- Node.js 18+
- Git

### Installation

**1. Clone Repository**
```bash
git clone https://github.com/KushuCon/FinalCrop.git
cd FinalCrop
```

**2. Backend Setup**
```bash
cd backend
python -m venv venv
venv\Scripts\activate          # Windows
source venv/bin/activate       # Mac/Linux
pip install -r requirements.txt
```

**3. Frontend Setup**
```bash
cd react-frontend
npm install
```

**4. Add Model File**
- Place `best_bet_plant_model.keras` in `backend/models/`

**5. Configure API Key**
- Get API key from wherever you like and config it
- Edit `backend/app.py`: Replace `GROQ_API_KEY = "your_key_here"`

---

## ▶️ Running the App

**Terminal 1 - Backend:**
```bash
cd backend
venv\Scripts\activate
python app.py
```
Backend runs at: http://127.0.0.1:5000

**Terminal 2 - Frontend:**
```bash
cd react-frontend
npm run dev
```
Frontend runs at: http://localhost:5173

**Open browser:** http://localhost:5173

---

## 📁 Project Structure
```
agricare-ai/
├── backend/
│   ├── models/
│   │   └── best_bet_plant_model.keras
│   ├── app.py
│   ├── requirements.txt
│   └── venv/
├── react-frontend/
│   ├── src/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── package.json
│   └── node_modules/
└── README.md
```

---

## 🛠️ Tech Stack

**Frontend:** React 18.3, Vite 6.0, Tailwind CSS 3.4  
**Backend:** Flask 3.1, TensorFlow 2.18, Groq API  
**Model:** EfficientNetB0 + DenseNet121 (99.48% accuracy)  
**Dataset:** PlantVillage (15 classes)

---

## 📦 Dependencies

### Backend (requirements.txt)
```
Flask==3.1.0
tensorflow==2.18.0
keras==3.7.0
Pillow==11.0.0
numpy==2.2.1
fpdf2==2.8.1
groq==0.14.0
flask-cors==5.0.0
```

### Frontend (package.json)
```json
{
  "dependencies": {
    "react": "^18.3.1",
    "react-dom": "^18.3.1",
    "react-dropzone": "^14.3.5",
    "lucide-react": "^0.469.0",
    "framer-motion": "^11.15.0"
  },
  "devDependencies": {
    "vite": "^6.0.3",
    "tailwindcss": "^3.4.17",
    "@vitejs/plugin-react": "^4.3.4"
  }
}
```

---

## 🧠 Model Details

| Model | Accuracy | Status |
|-------|----------|--------|
| MobileNetV2 | 87% | Baseline |
| EfficientNetB3 + DenseNet201 | 81% | Failed |
| InceptionV3 | 93% | Single |
| EfficientNetB0 | 97.96% | Single |
| Triple Hybrid | 97.66% | Complex |
| **EfficientNetB0 + DenseNet121** | **99.48%** | ✅ **Production** |

**Architecture:**
- Dual backbone (EfficientNetB0 + DenseNet121)
- Pretrained on ImageNet
- Fine-tuned last 40% layers
- Global Avg + Max Pooling
- Label smoothing (0.1)
- Input: 224×224×3

---

## 📊 Dataset

**Source:** PlantVillage (Kaggle)  
**Classes:** 15 diseases  
**Crops:** Pepper, Potato, Tomato

**Diseases:**
- Pepper: Bacterial Spot, Healthy
- Potato: Early Blight, Late Blight, Healthy
- Tomato: Bacterial Spot, Early Blight, Late Blight, Leaf Mold, Septoria Leaf Spot, Spider Mites, Target Spot, Yellow Leaf Curl Virus, Mosaic Virus, Healthy

---

## 🔧 Troubleshooting

**Backend issues:**
```bash
# Reinstall dependencies
pip install -r requirements.txt
```

**Frontend issues:**
```bash
# Clear cache
npm cache clean --force
npm install

# Check port availability
# Vite auto-increments if 5173 is busy
```

**API errors:**
- Verify API key in `backend/app.py`
- Check internet connection

---

## 📝 Usage

1. Upload leaf image (drag & drop or click)
2. AI detects disease (99.48% accuracy)
3. View results (disease name + confidence)
4. Generate advisory report (LLaMA 3.3 70B)
5. Download PDF report

---

## 🚢 Deployment

**Frontend (Vercel):**
- Build: `npm run build`
- Output: `dist`

**Backend (Render):**
- Build: `pip install -r requirements.txt`
- Start: `gunicorn app:app`
- Add env var: `GROQ_API_KEY`

---

## 📜 License

MIT License - see LICENSE file

---

## 👥 Team

**Developer:** Kaustubh  
**Institution:** Jaipur, Rajasthan  
**Year:** 2025-26

---

## 🙏 Acknowledgments

- PlantVillage Dataset
- TensorFlow/Keras
- API Key (LLaMA API)

---

**Made with ❤️ for farmers** 🌾
