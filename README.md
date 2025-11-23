# TheBevBooth

AI-powered beverage companion that suggests drinks based on your mood.

## Setup

1. Clone the repository
2. Install dependencies (if needed):
   ```bash
   npm install
   ```

3. Set up environment variables:
   - Copy `.env.example` to `.env` (or set in Vercel dashboard)
   - Add your Gemini API key:
     ```
     GEMINI_API_KEY=your_api_key_here
     ```

4. Get your Gemini API key from: https://makersuite.google.com/app/apikey

## Deployment on Vercel

1. Push your code to GitHub
2. Import the project in Vercel
3. Add the environment variable `GEMINI_API_KEY` in Vercel dashboard:
   - Go to your project settings
   - Navigate to "Environment Variables"
   - Add `GEMINI_API_KEY` with your API key value
4. Deploy!

## Security

- The API key is stored securely in Vercel environment variables
- API calls are proxied through a serverless function (`/api/gemini`)
- The API key is never exposed in the client-side code

## Files

- `home.html` - Home page
- `bevbae.html` - AI chat interface
- `api/gemini.js` - Serverless function that handles API calls securely
- `style.css` - Main stylesheet

