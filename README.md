# Mario AI by Shahriar

An Android-ready starter project for a ChatGPT-style assistant using the OpenAI API.

## Important
- This is a **starter project**, not a finished APK.
- You must deploy the backend and replace `API_BASE` in `www/app.js` with your backend HTTPS URL.
- Never put an OpenAI API key in the Android app, frontend JavaScript, or a public repository.
- OpenAI API usage may cost money. Ask a parent/guardian to help review billing and account setup. Never share secret keys in chat.

## 1. Install prerequisites
Install Node.js (LTS), Android Studio, and the Android SDK on a computer.

## 2. Configure the backend
```bash
cd server
npm install
cp .env.example .env
```
Put your secret key in `server/.env` on the server only. Do not upload `.env` to GitHub or share it.

Run locally:
```bash
npm start
```

Deploy the `server` folder to a trusted HTTPS Node hosting provider. Add `OPENAI_API_KEY` as a private environment variable in the hosting dashboard.

## 3. Connect the app
Edit `www/app.js` and replace:
```js
const API_BASE = "https://YOUR-BACKEND-DOMAIN.example";
```
with the HTTPS address of your deployed backend.

## 4. Create the Android project
From the project root:
```bash
npm install
npx cap add android
npx cap sync android
npx cap open android
```
Android Studio opens the project. Use **Build > Build Bundle(s) / APK(s) > Build APK(s)** to create a test APK.

## 5. Share safely
Test the app first. For public distribution, publish through a trusted app store or host the signed APK on a trusted HTTPS website. Do not share an unsigned/debug APK as a public release.

## Current starter features
- Mario AI branding
- Chat-style interface
- Bengali/English-ready conversation
- Suggested prompts for science and maths
- Dark/light toggle
- Backend endpoint using OpenAI Responses API

## Before public launch
Add authentication, rate limiting, abuse prevention, privacy policy, data-retention rules, and spending limits. The simple starter backend is not hardened for public traffic.


## Build from an Android phone using GitHub Actions
This project includes `.github/workflows/android.yml` for a cloud debug build.

1. Sign in to GitHub in your phone browser and create a new repository.
2. Upload the **contents** of this ZIP to the repository (including the hidden `.github` folder; if the mobile upload UI hides it, use GitHub's web editor to create `.github/workflows/android.yml` and paste the workflow from this file).
3. Open the repository's **Actions** tab.
4. Select **Build Mario AI Android APK**, then choose **Run workflow**.
5. When the run finishes, open it and download the `Mario-AI-debug-APK` artifact.
6. Extract the downloaded artifact ZIP to find `app-debug.apk`.

The debug APK is for testing, not a signed public release. The AI chat will not work until the backend is deployed and `API_BASE` in `www/app.js` is changed to that HTTPS backend address. Do not put your OpenAI API key in the app or repository.
