# Quick Cloud Deployment Guide

## Option 1: Deploy to Vercel + Railway (Recommended)

### Deploy Frontend to Vercel (Free, 5 minutes)

1. **Install Vercel CLI:**
   ```bash
   npm install -g vercel
   ```

2. **Deploy Frontend:**
   ```bash
   cd frontend
   vercel
   ```
   - Login with GitHub/Email
   - Accept defaults
   - You'll get a URL like: `https://lumora-xyz.vercel.app`

3. **Update Environment Variable:**
   After deploying backend, update the frontend:
   - Go to Vercel dashboard
   - Settings → Environment Variables
   - Add: `VITE_API_URL` = `https://your-backend-url.up.railway.app`
   - Redeploy

### Deploy Backend to Railway (Free tier available)

1. **Go to:** https://railway.app
2. **Sign up** with GitHub
3. **New Project** → **Deploy from GitHub repo**
4. **Or use Railway CLI:**
   ```bash
   npm install -g @railway/cli
   railway login
   cd backend
   railway init
   railway up
   ```

5. **Add Environment Variables in Railway:**
   - OPENAI_API_KEY
   - NANOBANANA_API_KEY
   - FAL_API_KEY
   - PORT=5000

6. **Generate Domain:**
   - Settings → Generate Domain
   - You'll get: `https://lumora-backend.up.railway.app`

## Option 2: Deploy to Render (Alternative)

### Backend (Render)
1. Go to https://render.com
2. New → Web Service
3. Connect GitHub repo
4. Build: `cd backend && npm install`
5. Start: `node src/server.js`
6. Add environment variables

### Frontend (Render Static Site)
1. New → Static Site
2. Build: `cd frontend && npm run build`
3. Publish: `frontend/dist`

## Option 3: Use ngrok (Temporary, for Demos)

### Quick Share Your Local Server:

1. **Download ngrok:** https://ngrok.com/download

2. **Start your servers** (already running)

3. **Expose Backend:**
   ```bash
   ngrok http 5000
   ```
   You'll get: `https://xyz123.ngrok.io`

4. **Update Frontend .env:**
   ```
   VITE_API_URL=https://xyz123.ngrok.io
   ```

5. **Expose Frontend:**
   ```bash
   ngrok http 5173
   ```
   You'll get: `https://abc456.ngrok.io`

6. **Share:** `https://abc456.ngrok.io` with your team!

**Note:** Free ngrok URLs expire after 8 hours and change each time.

## Recommended for Hackathon:

**Use ngrok for immediate demo** (5 minutes setup)
OR
**Deploy to Vercel + Railway** (15 minutes, permanent URLs)

Both options will work around AP Isolation and give your team access!
