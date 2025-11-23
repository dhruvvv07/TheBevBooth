# TheBevBooth

AI-powered beverage companion that suggests drinks based on your mood.

**Author:** Dhruv Gupta  
**Version:** 1.0.0  
**License:** MIT

---

## Project Overview

**TheBevBooth** is an AI-powered web application that suggests personalized non-alcoholic beverages based on user mood. The application features an interactive AI chatbot named "BevBae" that engages users in a conversational interface to understand their emotional state and recommends appropriate drinks.

---

## Tech Stack

### Frontend
- **HTML5** - Semantic markup for structure
- **CSS3** - Custom styling with:
  - Flexbox for layout
  - CSS Grid (implicit)
  - CSS Animations (keyframes, transitions)
  - Gradient backgrounds
  - Glassmorphism effects (backdrop-filter)
  - Responsive design with media queries
- **Vanilla JavaScript (ES6+)** - No frameworks, pure JavaScript for:
  - DOM manipulation
  - Async/await for API calls
  - Event handling
  - State management (chat flow)

### Backend/API
- **Vercel Serverless Functions** - Node.js runtime
- **Google Gemini AI API** (Gemini 2.0 Flash model) - For AI-powered drink suggestions

### Deployment & Infrastructure
- **Vercel** - Hosting and serverless function deployment
- **Environment Variables** - Secure API key management
- **Static Site Generation** - No build process required

### Development Tools
- **Vercel CLI** - For local development (`vercel dev`)
- **Git** - Version control
- **npm** - Package management

---

## Architecture

### Application Structure
```
TheBevBooth/
├── Frontend (Static HTML/CSS/JS)
│   ├── home.html - Landing page with banner
│   ├── bevbae.html - AI chat interface
│   ├── coming-soon.html - Placeholder page
│   ├── style.css - Global styles
│   └── Assets (logo.png, banner1.jpg)
│
├── Backend (Serverless)
│   └── api/gemini.js - API proxy function
│
├── Configuration
│   ├── package.json - Project metadata
│   ├── vercel.json - Deployment config
│   ├── .gitignore - Git exclusions
│   └── README.md - Documentation
```

### Data Flow
1. User interacts with frontend (bevbae.html)
2. JavaScript captures user input (name, mood)
3. Frontend sends request to `/api/gemini` serverless function
4. Serverless function authenticates with Gemini API using environment variable
5. Gemini API processes prompt and returns drink suggestion
6. Serverless function returns response to frontend
7. Frontend displays AI response with "Buy Now" button

---

## Features

### Core Functionality
1. **Multi-step Chat Interface**
   - Step 1: Name collection with intelligent parsing
   - Step 2: Mood detection and drink suggestion
   - Step 3: Display recommendation with purchase option

2. **Mood-Based Drink Recommendations**
   - Predefined drink categories for 7 moods:
     - Sad: Hot Chocolate, Strawberry Banana Smoothie, Rose Milk
     - Stress: Green Tea, Lavender Lemonade, Coconut Water
     - Breakup: Dark Hot Chocolate, Mango Passion Smoothie, Vanilla Milkshake
     - Happy: Berry Blast Smoothie, Virgin Mojito, Tropical Punch
     - Tired: Cold Brew Coffee, Green Apple Juice, Pomegranate Juice
     - Angry: Cucumber Mint Cooler, Watermelon Juice, Peach Iced Tea
     - Bored: Rainbow Smoothie, Blue Lagoon Mocktail, Mixed Berry Slush

3. **AI Integration**
   - Google Gemini 2.0 Flash model
   - Personalized responses using user's name
   - Context-aware suggestions
   - Prevents duplicate recommendations

4. **User Experience**
   - Enter key support for message sending
   - Auto-scrolling chat messages
   - Loading states ("Thinking...")
   - Responsive design for mobile and desktop
   - Smooth animations and transitions

### UI/UX Features
- **Glassmorphism Design** - Frosted glass effect on chat container
- **Animated Background** - Floating bubble animations
- **Sticky Navigation** - Header remains visible on scroll
- **Gradient Backgrounds** - Dark theme with gradient overlays
- **Hover Effects** - Interactive button and link states
- **Parallax Effect** - Fixed background attachment on banner

---

## Setup

1. Clone the repository
   ```bash
   git clone <repository-url>
   cd DhruvDRINKS-main
   ```

2. Install dependencies (if needed):
   ```bash
   npm install
   ```

3. Set up environment variables:
   - For local development, create a `.env` file in the root directory
   - Add your Gemini API key:
     ```
     GEMINI_API_KEY=your_api_key_here
     ```
   - Get your Gemini API key from: https://makersuite.google.com/app/apikey

4. Run locally (optional):
   ```bash
   npm run dev
   ```

---

## Deployment on Vercel

1. Push your code to GitHub
2. Import the project in Vercel
3. Add the environment variable `GEMINI_API_KEY` in Vercel dashboard:
   - Go to your project settings
   - Navigate to "Environment Variables"
   - Add `GEMINI_API_KEY` with your API key value
4. Deploy!

The serverless function will automatically be deployed and available at `/api/gemini`.

---

## Security

- The API key is stored securely in Vercel environment variables
- API calls are proxied through a serverless function (`/api/gemini`)
- The API key is never exposed in the client-side code
- Security headers configured (XSS protection, frame options, content type options)

---

## File Structure

### Frontend Files
- `home.html` - Landing page with hero banner
- `bevbae.html` - AI chat interface with inline styles
- `coming-soon.html` - Placeholder page
- `style.css` - Global stylesheet

### Backend Files
- `api/gemini.js` - Serverless function that handles API calls securely

### Configuration Files
- `package.json` - Project metadata and scripts
- `vercel.json` - Deployment configuration and routes
- `.gitignore` - Git exclusions

### Assets
- `logo.png` - Brand logo
- `banner1.jpg` - Home page banner image

---

## API Integration

### Gemini API
- **Model:** gemini-2.0-flash
- **Endpoint:** https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent
- **Authentication:** X-goog-api-key header

### Serverless Function Endpoint
- **Path:** `/api/gemini`
- **Method:** POST
- **Request Body:** `{ prompt: string }`
- **Response:** `{ text: string }` or `{ error: string }`

---

## Design System

### Color Palette
- **Primary Gold:** #f0c040 (buttons, highlights)
- **Secondary Gold:** #e2b630 (hover states)
- **Accent Blue:** #40c0f0 (AI messages)
- **Background Dark:** #1a1a1a, #292929 (gradient)
- **Header Dark:** #111
- **Text:** #ffffff (white)

### Typography
- **Font Family:** 'Segoe UI', sans-serif
- **Heading Sizes:** 3.5rem (h1), 1.5rem (h2)
- **Body Text:** 1.2rem, 1rem

---

## Future Enhancements (Potential)

- User authentication
- Drink favorites/saved recommendations
- Social sharing
- Drink database integration
- Order tracking
- Payment integration
- Multi-language support
- Voice input
- Drink recipe display

---

## Key Technical Decisions

1. **No Framework** - Chose vanilla JS for simplicity and performance
2. **Serverless Architecture** - Vercel functions for scalability
3. **Environment Variables** - Secure API key management
4. **Static Site** - Fast loading, easy deployment
5. **Glassmorphism UI** - Modern, engaging design
6. **Mood-Based Logic** - Predefined categories with AI enhancement

---

## Browser Compatibility

- Modern browsers (Chrome, Firefox, Safari, Edge)
- ES6+ JavaScript features
- CSS Grid and Flexbox
- Backdrop-filter (glassmorphism) - may have fallbacks

---

## Development Workflow

1. Local development: `npm run dev` (Vercel dev server)
2. Code changes in HTML/CSS/JS files
3. Test locally with Vercel CLI
4. Push to GitHub
5. Automatic deployment via Vercel
6. Environment variables configured in Vercel dashboard

---

## Project Statistics

- **Total Files:** ~10 core files
- **Lines of Code:** ~800+ (HTML/CSS/JS)
- **Pages:** 3 (home, chat, coming-soon)
- **API Endpoints:** 1 serverless function
- **Dependencies:** 1 dev dependency (Vercel CLI)
- **Build Time:** 0 (static site)

---

This project demonstrates modern web development practices with a focus on user experience, security, and performance while maintaining simplicity and maintainability.
