# ScoutAI - AI-Powered Talent Sourcing Platform

🤖 **AI-Driven Recruitment Automation**

ScoutAI is an advanced talent sourcing platform that leverages artificial intelligence to help recruiters and hiring managers quickly find, evaluate, and engage top talent. By automating the search and screening process, ScoutAI dramatically reduces time-to-hire and improves candidate quality.

![ScoutAI Logo](./Client/public/logo.png)

## 🚀 Key Features

- **🔍 AI-Powered Natural Language Search** - Transform natural language queries into precise candidate searches
- **⚡ Automated Candidate Screening** - Filter and score candidates against your specific requirements
- **📊 LinkedIn Profile Integration** - Scrape detailed candidate information directly from LinkedIn profiles
- **🎯 Smart Match Analysis** - Understand fit metrics and why candidates align with your role
- **✉️ Personalized Outreach** - AI-generated tailored messages for each candidate
- **📝 Search History** - Track and revisit previous talent searches
- **👥 Comprehensive Profiles** - View full candidate profiles with experience, skills, education, and more
- **🚩 Background Check Integration** - Automated flagging of potential issues
- **❓ Prescreening Questions** - AI-generated questions specific to each candidate

## 🏗️ Architecture Overview

ScoutAI follows a sophisticated **client-server architecture** with multiple AI-powered processing layers:

```
┌─────────────────────────────────────────────────────────────┐
│                        React Frontend                       │
│                      (User Interface)                       │
└────────────────────┬────────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────────┐
│                   Express.js Backend                        │
│              (Orchestration & Processing)                  │
└────────────────────┬────────────────────────────────────────┘
                     │
        ┌────────────┼────────────┐
        │            │            │
   ┌────▼──┐  ┌─────▼─────┐  ┌──▼────┐
   │ Gemini│  │  SerpAPI  │  │ Apify │
   │  LLM  │  │ (Search)  │  │(LinkedIn)│
   └────────┘  └───────────┘  └────────┘
        │            │            │
        └────────────┼────────────┘
                     │
        ┌────────────▼────────────┐
        │  Firestore + Vector DB  │
        │   (Data Persistence)    │
        └─────────────────────────┘
```

## 🔄 Core Process Flow

### 1. **Query Processing** 🔎
- User submits a natural language query (e.g., "Senior React developers in Bangalore with 5+ years experience")
- Gemini AI parses and transforms the query into structured search parameters
- Context extraction for location, skills, experience level, and specializations

### 2. **Candidate Discovery** 🌐
- System executes multiple search queries via SerpAPI
- Crawls search results to identify candidate profiles
- Initial candidate list compiled from various sources

### 3. **Data Enrichment** 📈
- LinkedIn profiles are automatically scraped using Apify
- Profile data is structured and standardized
- Extract experience, education, skills, endorsements, and recommendations

### 4. **Vector Database Storage** 🗄️
- Candidate profiles are converted to vector embeddings
- Embeddings stored in Firestore with full profile data
- Enables semantic similarity search and intelligent retrieval

### 5. **Candidate Analysis & Scoring** 🎯
- Candidates ranked against original job requirements
- AI generates prescreening questions specific to each candidate
- Background check flags created if issues detected
- Personalized outreach messages generated for engagement

### 6. **Results Delivery** 📋
- Ranked candidate list presented with confidence scores
- Detailed profiles with all analysis available
- Ready-to-send personalized outreach messages

## 🛠️ Tech Stack

### Frontend
- **React** - UI framework for building interactive components
- **Modern JavaScript** - ES6+ with dynamic features
- **Responsive Design** - Mobile-friendly interface

### Backend
- **Express.js** - Node.js web framework for API development
- **REST APIs** - RESTful endpoints for frontend communication
- **WebSockets** - Real-time updates during processing

### AI & Data
- **Google Gemini API** - LLM for intelligent query processing and analysis
- **SerpAPI** - Web search integration
- **Apify** - LinkedIn profile scraping
- **Vector Embeddings** - Semantic search capability

### Database & Storage
- **Firebase Firestore** - Real-time NoSQL database
- **Vector Search** - Semantic similarity matching
- **Authentication** - Firebase Auth integration

### Languages & Tools
- **JavaScript/Node.js** - Backend runtime
- **SQL/NoSQL** - Data querying

## 📦 Project Structure

```
ScoutAI/
├── Client/                      # React frontend
│   ├── public/
│   │   └── logo.png
│   ├── src/
│   │   ├── components/          # React components
│   │   ├── pages/               # Page components
│   │   └── App.jsx
│   └── package.json
├── Backend/                     # Express.js server
│   ├── routes/                  # API endpoints
│   ├── controllers/             # Business logic
│   ├── services/                # AI & external services
│   ├── config/                  # Configuration files
│   └── server.js
├── docs/                        # Documentation
│   └── architecture-diagram.png
├── .env.example                 # Environment variables template
└── README.md
```

## 🚀 Getting Started

### Prerequisites
- Node.js v14 or higher
- npm or yarn
- Firebase account with Firestore setup
- Google Gemini API key
- SerpAPI key
- Apify account

### Installation

1. **Clone the Repository**
```bash
git clone https://github.com/mugilan-sakthivel/ScoutAI.git
cd ScoutAI
```

2. **Setup Backend**
```bash
cd Backend
npm install
cp .env.example .env
# Update .env with your API keys
```

3. **Setup Frontend**
```bash
cd ../Client
npm install
```

### Configuration

Create a `.env` file in the backend directory:
```env
# Firebase
FIREBASE_API_KEY=your_firebase_key
FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
FIREBASE_PROJECT_ID=your_project_id
FIREBASE_STORAGE_BUCKET=your_storage_bucket

# AI Services
GEMINI_API_KEY=your_gemini_key
SERPAPI_KEY=your_serpapi_key
APIFY_TOKEN=your_apify_token

# Server
PORT=5000
NODE_ENV=development
```

## 🎯 How It Works

1. User enters a job description or search query
2. AI analyzes and extracts key requirements
3. System performs comprehensive talent search
4. LinkedIn profiles are enriched with detailed data
5. Candidates are scored and ranked
6. Personalized outreach messages are generated
7. Results presented with actionable insights

## 📊 Key Metrics

- **⭐ GitHub Stars**: 1
- **👥 Contributors**: 3 (mugilankani, AlwinSunil, Anam-Ashraf7)
- **📜 License**: MIT License
- **🔧 Primary Language**: JavaScript (99.7%)

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/YourFeature`)
3. Commit changes (`git commit -m 'Add YourFeature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

## 🔐 License

This project is licensed under the **MIT License** - see the LICENSE file for details.

## 👥 Team

- **Mugilan Sakthivel** ([@mugilankani](https://github.com/mugilankani)) - Lead Developer
- **Alwin Sunil** ([@AlwinSunil](https://github.com/AlwinSunil)) - Contributor
- **Anam Ashraf** ([@Anam-Ashraf7](https://github.com/Anam-Ashraf7)) - Contributor

## 📞 Support & Contact

- 🐛 Found a bug? [Open an issue](https://github.com/mugilan-sakthivel/ScoutAI/issues)
- 💬 Questions? Reach out via GitHub Discussions
- 💼 LinkedIn: [mugilansakthivel](https://linkedin.com/in/mugilansakthivel)

## 🚀 Future Roadmap

- [ ] Multi-language support for global candidate search
- [ ] Advanced salary prediction models
- [ ] Interview scheduling automation
- [ ] Candidate pipeline management dashboard
- [ ] Integration with popular ATS platforms
- [ ] Custom scoring algorithms per organization
- [ ] Advanced analytics and reporting

---

**Built with ❤️ by Mugilan Sakthivel**

*Last Updated: November 14, 2025*
