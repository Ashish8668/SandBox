# NLP Based Resume Analysis Dashboard (React + Firebase)

This project is a starter dashboard for **NLP-based resume analysis** using:
- React (Vite)
- Firebase Firestore
- Recharts for analytics visuals

You can upload a resume file, run a lightweight keyword-based NLP score, and store analysis results in Firestore.

## Features

- Resume upload (`.txt`, `.md`, `.pdf`, `.doc`, `.docx`)
- Candidate fit scoring against target skills
- Dashboard KPI cards
- Score bar chart
- Recent analysis table
- Firebase Firestore save for each analysis

## Project Setup

## 1) Install dependencies

```bash
npm install
```

## 2) Configure Firebase

1. Create a Firebase project: https://console.firebase.google.com
2. Enable Firestore Database.
3. Copy `.env.example` to `.env`
4. Fill values from your Firebase web app config.

Example:

```env
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=000000000000
VITE_FIREBASE_APP_ID=1:000000000000:web:abcdef123456
```

## 3) Run locally

```bash
npm run dev
```

Then open the local URL shown in terminal (usually `http://localhost:5173`).

## Build for production

```bash
npm run build
npm run preview
```

## Firestore Data Model

Collection: `resumeAnalyses`

Document fields:
- `name`
- `score`
- `matchPercent`
- `experienceYears`
- `matched` (array)
- `missing` (array)
- `sourceFile`
- `createdAt`
- `serverCreatedAt`

## NLP Note

Current logic is keyword-based for fast prototyping.
For production NLP, replace scoring logic in `src/App.jsx` with:
- spaCy / transformers API
- semantic skill extraction
- job description vs resume embeddings
- section-wise scoring (skills, projects, experience)

## Scripts

- `npm run dev` - start development server
- `npm run build` - production build
- `npm run preview` - preview production build

## Folder Structure

```txt
.
├── src
│   ├── App.jsx
│   ├── firebase.js
│   ├── main.jsx
│   └── styles.css
├── .env.example
├── index.html
├── package.json
└── vite.config.js
```
