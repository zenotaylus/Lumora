# ✨ Lumora - AI-Powered Fashion Assistant

An intelligent AI-powered fashion application that provides outfit rating and generation capabilities using artificial intelligence.

## 🎯 Features

- **Outfit Rater Mode**: Upload outfit photos for AI-powered analysis and rating
- **Outfit Generator Mode**: Generate personalized outfit recommendations with AI-created visualizations
- **Fashion Arena Mode**: Social sharing and community voting platform
- **AI-Powered Analysis**: Uses GPT-4 Vision for intelligent outfit feedback
- **Face Preservation**: Maintains your facial features in generated images using NanobananaAPI
- **Mobile-Responsive Design**: Works beautifully on all devices

## 🛠️ Technology Stack

### Backend
- Node.js 18+
- Express.js 4.18+
- OpenAI GPT-4 Vision
- NanobananaAPI (Image Generation)
- Sharp (Image Processing)
- UUID for ID generation

### Frontend
- React 18+
- Vite
- Axios
- Modern CSS with responsive design

## 📋 Prerequisites

- Node.js 18 or higher
- NPM or Yarn
- API Keys:
  - OpenAI API Key
  - NanobananaAPI Key (optional, for image generation)
  - Fal API Key (optional, for CDN)

## 🚀 Quick Start

### 1. Clone the Repository

```bash
cd outfit-assistant
```

### 2. Backend Setup

```bash
cd backend

# Install dependencies
npm install

# The .env file already exists with your API keys
# Verify it contains:
# OPENAI_API_KEY=...
# NANOBANANA_API_KEY=...
# FAL_API_KEY=...

# Start the backend server
npm start
```

The backend will start on **http://localhost:5000**

### 3. Frontend Setup

Open a new terminal:

```bash
cd frontend

# Install dependencies (already done)
# npm install

# Start the development server
npm run dev
```

The frontend will start on **http://localhost:5173**

### 4. Access the Application

Open your browser and navigate to **http://localhost:5173**

## 📖 Usage Guide

### Outfit Rater Mode

1. Click on **"⭐ Outfit Rater"** in the header
2. Upload an outfit photo (JPG, PNG, HEIC, or WEBP, max 10MB)
3. Select the occasion (Job Interview, Date Night, etc.)
4. Optionally add your budget (e.g., USD 500)
5. Click **"Rate My Outfit"**
6. View your results:
   - Wow Factor (1-10)
   - Occasion Fitness (1-10)
   - Overall Rating (1-10)
   - Strengths, Improvements, and Styling Suggestions
   - Shopping Recommendations
7. Submit to Fashion Arena to share with the community!

### Outfit Generator Mode

1. Click on **"🎨 Outfit Generator"** in the header
2. Optionally upload your photo for personalized generation
3. Adjust the Wow Factor slider (1-10):
   - 1-3: Classic & Safe
   - 4-6: Balanced & Stylish
   - 7-10: Bold & Creative
4. Add favorite brands (optional, max 5)
5. Set your budget (required)
6. Select the occasion
7. Add special conditions (optional, e.g., "must include red")
8. Click **"Generate Outfit"**
9. Wait 30-60 seconds for AI to create your perfect outfit
10. View your generated outfit with:
    - AI-generated outfit visualization
    - Complete outfit description
    - Color palette and styling notes
    - Shopping recommendations
11. Click **"Generate Another"** for more options!

### Fashion Arena Mode

1. Click on **"🏆 Fashion Arena"** in the header
2. Browse outfits submitted by the community
3. **Double-click/Double-tap** on outfits to like them
4. View the Top 10 Leaderboard
5. Sort submissions by:
   - Recent
   - Top Voted
   - Top Rated

## 📂 Project Structure

```
outfit-assistant/
├── backend/
│   ├── src/
│   │   ├── services/
│   │   │   ├── openaiService.js        # GPT-4 Vision integration
│   │   │   └── nanobananaService.js    # Image generation
│   │   ├── db/
│   │   │   └── fashionArena.js         # JSON database
│   │   ├── utils/
│   │   │   ├── imageProcessor.js       # Image processing
│   │   │   └── logger.js               # Logging system
│   │   ├── middleware/
│   │   │   └── errorHandler.js         # Error handling
│   │   └── server.js                   # Main Express server
│   ├── package.json
│   └── .env                            # API keys
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Header.jsx              # App header
│   │   │   ├── OutfitRater.jsx         # Rating interface
│   │   │   ├── OutfitGenerator.jsx     # Generation interface
│   │   │   ├── FashionArena.jsx        # Arena interface
│   │   │   ├── ImageUpload.jsx         # Reusable upload component
│   │   │   ├── LoadingSpinner.jsx      # Loading indicator
│   │   │   └── Modal.jsx               # Modal dialog
│   │   ├── services/
│   │   │   └── api.js                  # API service layer
│   │   ├── utils/
│   │   │   ├── imageUtils.js           # Image utilities
│   │   │   └── validation.js           # Form validation
│   │   ├── App.jsx                     # Main app component
│   │   └── App.css                     # Application styles
│   └── package.json
├── logs/                               # Application logs
└── README.md                           # This file
```

## 🔑 API Endpoints

### Backend API (http://localhost:5000)

- `GET /api/health` - Health check
- `POST /api/rate-outfit` - Rate an outfit
- `POST /api/generate-outfit` - Generate outfit
- `POST /api/regenerate-outfit` - Regenerate last outfit
- `POST /api/arena/submit` - Submit to Fashion Arena
- `GET /api/arena/submissions` - Get all submissions
- `GET /api/arena/leaderboard` - Get top 10 leaderboard
- `POST /api/arena/like` - Like a submission
- `GET /api/arena/submission/:id` - Get submission by ID
- `GET /api/arena/stats` - Get arena statistics

## 🎨 Design System

### Colors
- Primary: #667eea (Purple)
- Secondary: #764ba2 (Purple gradient)
- Accent: #f093fb (Pink gradient)
- Success: #48bb78
- Error: #f56565

### Typography
- Font Family: System fonts (Segoe UI, Roboto, sans-serif)
- Headings: Bold, 24-32px
- Body: Regular, 14-16px

## 🐛 Troubleshooting

### Backend won't start
- Ensure Node.js 18+ is installed: `node --version`
- Check that all dependencies are installed: `npm install`
- Verify .env file contains valid API keys
- Check port 5000 is not in use

### Frontend won't start
- Ensure dependencies are installed: `npm install`
- Check that backend is running on port 5000
- Clear browser cache and try again

### Image generation fails
- Check NANOBANANA_API_KEY is valid
- Check FAL_API_KEY is valid
- Image generation takes 30-60 seconds, be patient
- If it fails, a placeholder image will be shown

### Outfit rating fails
- Check OPENAI_API_KEY is valid
- Ensure image is under 10MB
- Verify image format is JPG, PNG, HEIC, or WEBP

## 📝 Logs

Application logs are stored in the `logs/` directory with daily rotation:
- Format: `outfit_assistant_YYYYMMDD.log`
- Contains request/response logs, errors, and performance metrics

## 🔒 Security Notes

- API keys are stored in `.env` file (not committed to version control)
- Images are processed in memory only
- No persistent storage of user data (except Fashion Arena submissions)
- CORS configured for localhost development

## 💡 Tips

1. **Best Results**: Use clear, well-lit photos for outfit rating
2. **Budget Matters**: Providing a budget helps with more accurate recommendations
3. **Wow Factor**: Start with 5 and adjust based on how adventurous you want to be
4. **Special Conditions**: Be specific (e.g., "must be comfortable for walking")
5. **Fashion Arena**: Double-click/tap to like - it's Instagram-style!

## 🚀 Deployment (Future)

### Backend (Railway)
1. Push code to GitHub
2. Connect Railway to repository
3. Add environment variables
4. Deploy

### Frontend (Vercel)
1. Push code to GitHub
2. Connect Vercel to repository
3. Update API_BASE_URL to production backend
4. Deploy

## 📄 License

MIT License - Developed by Lumora Team

## 👥 Team Credits

**Lumora Development Team**
- Simon Armstrong - Sensei
- Craig Acquaye - Team Member
- Iris Keum - Team Member
- Saurabh Mehta - Team Member
- Taj-Mahal Y Aquino - Team Member
- Sailesh Sharma - Team Member
- Kyn Sze - Team Member

*Developed during AI Hackathon 2025*

## 🤝 Contributing

This is a hackathon project. For improvements or suggestions, please reach out to the team.

## 📞 Support

For issues or questions:
1. Check the Troubleshooting section above
2. Review logs in the `logs/` directory
3. Verify API keys are valid
4. Check network connectivity

---

**Built with ❤️ using AI and modern web technologies**
