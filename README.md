# 🛍️ Visual Product Matcher

A web application that lets users **upload a product image** and find **visually similar products** from a dataset using deep learning embeddings and FastAPI backend.  
Deployed with **Netlify (Frontend)** and **Render (Backend)**.  


[Live Deployement](https://visualproductmatcher.netlify.app/)
---

## 📊 System Flow

```
Summary Flow
Frontend (upload image) 
   ↓
Backend (FastAPI /upload)
   ↓
[Save + Embed + Classify (Gemini)]
   ↓
Store in uploads DB
   ↓
Ensure dataset (Unsplash → dataset DB)
   ↓
Similarity search (cosine)
   ↓
Return top matches
   ↓
Frontend displays results
```
```
flowchart TD
    A[User Uploads Image] --> B[Frontend (React + Netlify)]
    B --> C[API Call /api/upload]
    C --> D[Backend (FastAPI + Uvicorn on Render)]
    D --> E[Image Preprocessing (TensorFlow MobileNetV2)]
    E --> F[Feature Embedding Extraction]
    F --> G[Similarity Search (Cosine Distance)]
    G --> H[Top-N Similar Products]
    H --> I[Send Results as JSON]
    I --> J[Frontend Renders Product Grid]
```
# Folder Structure
```
visual-product-matcher/
│── backend/
│   ├── main.py              # FastAPI entry
│   ├── routes/
│   │   ├── upload.py        # Upload route
│   │   └── similar.py       # Similarity route
│   ├── data/images/         # Dataset images
│   ├── uploads/             # User uploaded images
│   └── requirements.txt
│
│── frontend/
│   ├── src/
│   │   ├── components/      # React components
│   │   ├── App.jsx
│   │   └── index.css
│   ├── public/
│   └── package.json
│
└── README.md
```

[Screenshot 2025-08-31 222657.png]
[Screenshot 2025-08-31 222741.png]
[Screenshot 2025-08-31 222632.png]
[Screenshot 2025-08-31 222614.png]

# ⚡ Tech Stack
## 🌐 Frontend

React.js (Vite)
TailwindCSS (UI styling)
Glassmorphism + Responsive UI

Netlify Deployment
# Frontend - 
[Frontend Deployement](https://visualproductmatcher.netlify.app/)

# ⚙️ Backend

FastAPI (Python)
TensorFlow (MobileNetV2 embeddings)
NumPy + PIL for image processing
CORS middleware
Uvicorn server

Render Deployment
# Backend - 
[Backend Deployment](https://visual-product-matcher-nopo.onrender.com)

🗄️ Data Handling

Product Dataset (stored in data/images)
Uploaded images stored in /uploads
Similarity calculation (cosine distance)


# 🚀 Features

✅ Upload an image to find similar products <br>
✅ Real-time similarity search using embeddings <br>
✅ Interactive preview of uploaded image <br>
✅ Adjustable threshold slider for similarity results <br>
✅ Responsive design (Desktop, Tablet, Mobile) <br>
✅ Deployed and accessible via public URLs <br>


# 🛠️ Setup Instructions (Local Development)
# 1. Clone Repo
```
git clone https://github.com/your-username/visual-product-matcher.git
cd visual-product-matcher

```

# 2. Backend Setup (FastAPI)

```
cd backend
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
pip install -r requirements.txt

```
# Run backend:
```
uvicorn main:app --reload
```

```
API runs at → http://localhost:8000
```

# 3. Frontend Setup (React)
```
cd frontend
npm install
npm run dev
```
```
Frontend runs at → http://localhost:5173
```




# 🔮 Future Improvements
Add database (Postgres / MongoDB) for product metadata
Support multi-modal search (text + image)
Add authentication (JWT) for user-specific uploads
Implement infinite scroll + pagination for results
Optimize embeddings with FAISS / Milvus for scalable similarity search

# 🌍 Deployment

Frontend: [Netlify → ](https://visualproductmatcher.netlify.app)
Backend: Render (FastAPI server)


