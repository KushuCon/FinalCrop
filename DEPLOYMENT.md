# Deployment Instructions

## Prerequisites

- GitHub repositories ready
- Gemini API key

## Render Deployment (Backend)

1. **Connect to Render:**

   - Go to [render.com](https://render.com)
   - Connect your GitHub account
   - Click "New +" → "Web Service"
   - Select your backend-only repository

2. **Configure Service:**

   - **Name:** agricare-ai-backend (or your choice)
   - **Environment:** Python 3
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `gunicorn app:app`
   - **Instance Type:** Free tier is fine for testing

3. **Set Environment Variables:**

   - In Render dashboard, go to Environment tab
   - Add: `GEMINI_API_KEY` = your_actual_api_key
   - Add: `PYTHON_VERSION` = 3.11.0 (optional, for consistency)

4. **Deploy:**
   - Click "Create Web Service"
   - Render will automatically build and deploy
   - Wait for deployment to complete (5-10 minutes)

## Vercel Deployment (Frontend)

1. **Connect to Vercel:**

   - Go to [vercel.com](https://vercel.com)
   - Connect your GitHub account
   - Select your main project repository

2. **Configure Build Settings:**

   - **Framework Preset:** Vite
   - **Root Directory:** `react-frontend`
   - **Build Command:** `npm run build`
   - **Output Directory:** `dist`

3. **Set Environment Variables:**

   - In Vercel dashboard, go to Settings > Environment Variables
   - Add: `VITE_API_URL` = your_render_backend_url (e.g., https://agricare-ai-backend.onrender.com)

4. **Deploy:**
   - Click "Deploy"
   - Vercel will build and deploy your frontend

## Important Notes

- **Never commit .env files** - they're now in .gitignore
- **Set API keys in platform dashboards** - not in code
- **Update VITE_API_URL** after Render deployment completes
- **Render free tier** may have cold starts (first request takes longer)

## Step-by-Step Process

1. **Deploy Backend First:**

   - Deploy to Render
   - Copy the generated URL (e.g., https://your-app.onrender.com)

2. **Then Deploy Frontend:**
   - Set VITE_API_URL to your Render backend URL
   - Deploy to Vercel

## Testing Deployment

1. Visit your Vercel URL
2. Upload an image
3. Verify it connects to Render backend
4. Test PDF download functionality

## Troubleshooting

- **Frontend can't connect to backend:** Check VITE_API_URL is correct
- **Render deployment fails:** Check requirements.txt has all dependencies
- **Model loading fails:** Ensure models/ folder is in backend repo
- **Cold start issues:** First request to Render may be slow (free tier limitation)
- **CORS errors:** Backend already has CORS enabled, should work fine

## Free Tier Limitations

- **Render:** Service sleeps after 15 minutes of inactivity
- **Vercel:** 100GB bandwidth per month
- Both are sufficient for testing and small-scale usage
