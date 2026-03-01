# Before Ben Leaves — Rencher Family Questionnaire

## Setup Guide (15 minutes total)

### Step 1: Create Firebase Project (Free — 5 min)

1. Go to https://console.firebase.google.com
2. Click **Add Project** → name it `rencher-family` → click through defaults
3. Once created, click the **</>** (Web) icon to add a web app
4. Name it anything (e.g. "questionnaire") → **Register app**
5. Copy the `firebaseConfig` object it shows you — you'll need it in Step 3
6. In the left sidebar, click **Build → Realtime Database**
7. Click **Create Database** → choose any location → Start in **test mode**
8. Done with Firebase

### Step 2: Add Your Firebase Config

Open `public/index.html` and find this block (around line 230):

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  ...
};
```

Replace it with the config you copied from Firebase.

### Step 3: Deploy to Vercel (Free — 5 min)

**Option A: Via GitHub (recommended)**
1. Push this folder to a GitHub repo
2. Go to https://vercel.com → Sign in with GitHub
3. Click **Add New → Project** → Import your repo
4. Click **Deploy** — done!

**Option B: Via Vercel CLI**
```bash
npm i -g vercel
cd rencher-family-app
vercel --prod
```

### Step 4: Share the URL
Vercel gives you a URL like `rencher-family.vercel.app`. Text it to the family.

---

## How It Works
- Each family member taps their name and answers 11 questions
- 4 shared questions (goals, favorite memory, favorite trip, what to do as a family)
- 7 personalized "I want [person] to know…" questions (one for each other family member)
- The Summary view compiles everything with 3 tabs:
  - **All Answers** — every response organized by question
  - **Family Goals** — compiled goals and family activity wishes
  - **Messages To Each** — everything the family wants each person to know, grouped by recipient
