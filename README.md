# Migo – Virtueller Assistent der Mirgos Bank

## Deployment auf Vercel

### 1. Repository auf GitHub erstellen

```bash
git init
git add .
git commit -m "Initial commit – Migo v5"
git remote add origin https://github.com/DEIN-USERNAME/migo-assistant.git
git push -u origin main
```

### 2. Vercel verbinden

1. [vercel.com](https://vercel.com) → Log in
2. **"Add New Project"** → GitHub Repo auswählen
3. **Framework Preset:** Other
4. **Root Directory:** `.` (Standard)
5. **"Deploy"** klicken

### 3. API Key hinterlegen

Nach dem ersten Deploy:
1. Vercel Dashboard → Projekt → **Settings → Environment Variables**
2. Name: `ANTHROPIC_API_KEY`
3. Value: `sk-ant-...` (deinen Anthropic API Key)
4. Environment: **Production** + **Preview**
5. **Save** → dann **Redeploy** auslösen

### 4. Stakeholder-Link

Nach dem Deployment erhältst du eine URL wie:
```
https://migo-assistant.vercel.app
```

Jeder `git push` auf `main` löst automatisch ein neues Deployment aus.

---

## Lokale Entwicklung

Für lokales Testen mit echtem API-Zugriff:

```bash
npm install -g vercel
vercel dev
```

Dann `.env.local` erstellen:
```
ANTHROPIC_API_KEY=sk-ant-...
```

## Projekt-Struktur

```
/
├── api/
│   └── chat.js          # Serverless proxy → Anthropic API
├── public/
│   └── index.html       # Migo Frontend (alle Versionen hier ablegen)
├── package.json
├── vercel.json
└── README.md
```
