# Review Hub

🌐 **Live Demo:** [https://review-ochre.vercel.app/](https://review-ochre.vercel.app/)

---

## 📌 Section 1: Project Idea

**Review Hub** is an intelligent review management and analysis platform that helps businesses and users collect, analyze, and understand customer feedback. The platform leverages AI-powered sentiment analysis to provide actionable insights from customer reviews, enabling businesses to make data-driven decisions and improve customer satisfaction.

### Key Features:
- **Review Collection & Management**: Centralized platform to aggregate reviews from multiple sources
- **AI-Powered Sentiment Analysis**: Automated analysis of customer sentiment (positive, negative, neutral)
- **Smart Insights Dashboard**: Visual representation of review trends and customer feedback patterns
- **Real-time Processing**: Instant analysis and categorization of incoming reviews
- **Root Cause Analysis**: Identify common pain points and areas of improvement
- **User-friendly Interface**: Clean and intuitive design for easy navigation and usage

---

## 💻 Section 2: Technologies Used

### Frontend
- **React.js** - JavaScript library for building user interfaces
- **CSS3** - Styling and responsive design
- **HTML5** - Markup structure
- **JavaScript (ES6+)** - Core programming language

### Backend
- **Node.js** - JavaScript runtime environment
- **Express.js** (assumed) - Web application framework
- **RESTful API** - API architecture

### AI/ML Service
- **Python** - Programming language for AI/ML operations
- **Flask/FastAPI** (assumed) - Python web framework
- **Natural Language Processing (NLP)** - Text analysis and sentiment detection
- **Machine Learning Models** - Sentiment classification algorithms

### Deployment & Tools
- **Vercel** - Frontend hosting and deployment
- **Git & GitHub** - Version control
- **npm** - Package manager

### Project Structure Technologies
```
Review-Hub/
├── Frontend (React)    → 56.6% JavaScript
├── Styling             → 32.9% CSS
├── AI Service          → 10.0% Python
└── HTML                → 0.5% HTML
```

---

## 📁 Section 3: Project Structure

```
Review-Hub/
│
├── ai-service/              # AI/ML backend for sentiment analysis
│   ├── models/              # Machine learning models
│   ├── utils/               # Utility functions for NLP
│   └── app.py               # AI service main application
│
├── backend/                 # Node.js backend server
│   ├── routes/              # API routes
│   ├── controllers/         # Business logic controllers
│   ├── models/              # Data models
│   └── server.js            # Backend entry point
│
├── public/                  # Static assets
│   ├── index.html           # HTML template
│   ├── favicon.ico          # Website icon
│   └── assets/              # Images, icons, etc.
│
├── src/                     # React frontend source code
│   ├── components/          # React components
│   │   ├── Dashboard/       # Dashboard components
│   │   ├── ReviewList/      # Review display components
│   │   ├── Analytics/       # Analytics visualizations
│   │   └── common/          # Reusable components
│   │
│   ├── pages/               # Page components
│   ├── services/            # API service calls
│   ├── utils/               # Helper functions
│   ├── styles/              # CSS files
│   ├── App.js               # Main App component
│   └── index.js             # React entry point
│
├── root-cause               # Root cause analysis scripts
│
├── .gitignore               # Git ignore file
├── package.json             # Node dependencies and scripts
├── package-lock.json        # Locked dependency versions
└── README.md                # Project documentation
```

---

## 🚀 Section 4: Steps to Use the Project

### Prerequisites
Before you begin, ensure you have the following installed:
- **Node.js** (v14.0 or higher)
- **npm** (v6.0 or higher)
- **Python** (v3.8 or higher) - for AI service
- **Git** - for cloning the repository

### Installation Steps

#### 1. Clone the Repository
```bash
git clone https://github.com/anush-2705/Review-Hub.git
cd Review-Hub
```

#### 2. Install Frontend Dependencies
```bash
npm install
```

#### 3. Install Backend Dependencies
```bash
cd backend
npm install
cd ..
```

#### 4. Set Up AI Service
```bash
cd ai-service
pip install -r requirements.txt
cd ..
```

#### 5. Configure Environment Variables
Create a `.env` file in the root directory and add necessary configurations:
```env
REACT_APP_API_URL=http://localhost:5000
REACT_APP_AI_SERVICE_URL=http://localhost:8000
```

#### 6. Start the Development Servers

**Terminal 1 - Frontend:**
```bash
npm start
```
The app will run on [http://localhost:3000](http://localhost:3000)

**Terminal 2 - Backend:**
```bash
cd backend
npm start
```
Backend will run on [http://localhost:5000](http://localhost:5000)

**Terminal 3 - AI Service:**
```bash
cd ai-service
python app.py
```
AI service will run on [http://localhost:8000](http://localhost:8000)

#### 7. Access the Application
Open your browser and navigate to:
```
http://localhost:3000
```

### Production Build
To create a production build:
```bash
npm run build
```

The optimized build will be created in the `build` folder.

---

## 🔄 Section 5: Project Flow

### 1. **User Interaction Flow**
```
User → Review Hub Dashboard → Submit/View Reviews → AI Analysis → Results Display
```

### 2. **Detailed Application Flow**

#### A. **Review Submission Process**
1. User accesses the Review Hub web interface
2. User submits a new review or imports existing reviews
3. Frontend validates the input and sends data to the backend API
4. Backend stores the review in the database
5. Review is queued for AI analysis

#### B. **AI-Powered Sentiment Analysis**
1. Backend sends review text to AI Service (Python microservice)
2. AI Service performs:
   - Text preprocessing (cleaning, tokenization)
   - Sentiment classification (Positive/Negative/Neutral)
   - Keyword extraction
   - Emotion detection
3. AI Service returns analysis results to backend
4. Backend updates review record with sentiment data

#### C. **Data Visualization & Insights**
1. User navigates to Analytics Dashboard
2. Frontend requests aggregated data from backend
3. Backend processes and returns:
   - Sentiment distribution charts
   - Trending topics
   - Rating statistics
   - Time-series analysis
4. Frontend renders interactive visualizations

#### D. **Root Cause Analysis**
1. System identifies patterns in negative reviews
2. Clustering algorithms group similar complaints
3. Root cause analysis module generates insights
4. Actionable recommendations are presented to users

### 3. **Technical Data Flow Diagram**

```
┌─────────────────┐
│   React UI      │
│   (Frontend)    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│   Express.js    │
│   (Backend API) │
└────────┬────────┘
         │
         ├────────────────────┐
         │                    │
         ▼                    ▼
┌─────────────────┐  ┌─────────────────┐
│   Database      │  │  Python AI      │
│   (Reviews)     │  │  Service (NLP)  │
└─────────────────┘  └─────────────────┘
```

### 4. **Key Workflows**

#### Review Analysis Pipeline:
```
Input Review → Preprocessing → Sentiment Analysis → 
Feature Extraction → Classification → Results Storage → 
Dashboard Update → User Notification
```

#### Dashboard Refresh Cycle:
```
User Request → API Call → Data Aggregation → 
Chart Generation → UI Update → Cache Results
```

### 5. **API Endpoints Flow** (Example)

```javascript
// Create Review
POST /api/reviews
→ Validate data
→ Save to database
→ Trigger AI analysis
→ Return review ID

// Get Sentiment Analysis
GET /api/reviews/:id/sentiment
→ Fetch from cache/database
→ If not analyzed, trigger AI
→ Return sentiment data

// Get Dashboard Stats
GET /api/analytics/dashboard
→ Aggregate reviews
→ Calculate metrics
→ Return statistics
```

---

## 📊 Key Benefits

- ✅ **Automated Insights**: AI-powered analysis eliminates manual review processing
- ✅ **Real-time Analytics**: Instant feedback on customer sentiment trends
- ✅ **Scalable Architecture**: Microservices design for easy scaling
- ✅ **User-Friendly**: Intuitive interface for both technical and non-technical users
- ✅ **Data-Driven Decisions**: Actionable insights for business improvement

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 License

This project is open source and available under the MIT License.

---

## 👤 Author

**Anush**
- GitHub: [@anush-2705](https://github.com/anush-2705)
- Project Link: [https://github.com/anush-2705/Review-Hub](https://github.com/anush-2705/Review-Hub)

---

## 🌟 Show Your Support

Give a ⭐️ if this project helped you!

---

**Made with ❤️ by Anush**
