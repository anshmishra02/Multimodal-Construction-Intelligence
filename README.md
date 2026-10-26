# 🏗️ Multimodal Construction Intelligence Platform

An AI-powered construction intelligence platform that combines multimodal image analysis, construction project planning, real estate valuation, and weather-aware recommendations in a single web application.

## 🌐 Live Demo

- **Live Application:** https://multimodal-construction-intelligence.onrender.com/
- **GitHub Repository:** https://github.com/Mayankpawar28/MultiModal-Construction-intelligence
- **API Health Check:** https://multimodal-construction-intelligence.onrender.com/api/health

## 📌 Overview

The **Multimodal Construction Intelligence Platform** is an AI-powered decision-support system designed to assist construction professionals, site engineers, project managers, and property stakeholders.

The platform enables users to upload construction site images for preliminary analysis, review visible cracks and surface conditions, obtain indicative property valuations, explore project planning suggestions, and receive construction-related guidance.

By integrating AI-powered image analysis, a conversational construction assistant, and external weather data, the application brings multiple construction support workflows together in one accessible web interface.

## ✨ Key Features

### 🦺 1. Site Safety Review
- Analyze uploaded construction site images for potential safety concerns.
- Identify visually observable hazards where supported by the AI model.
- Generate preliminary safety observations and recommendations.

### 🔍 2. Crack and Surface Analysis
- Examine construction images for visible cracks and surface irregularities.
- Generate preliminary observations about potential structural concerns.
- Provide general recommendations for further inspection.

*Note: Image-based analysis is preliminary and does not replace an assessment by a qualified structural engineer.*

### 🏠 3. Real Estate Valuation
- Generate indicative property valuation estimates based on user-provided information.
- Support preliminary property-related decision-making.
- Present AI-generated insights to help users explore potential property values.

### 📋 4. Construction Project Planning
- Generate AI-assisted construction planning suggestions.
- Help users explore project activities and possible next steps.
- Provide general construction workflow guidance based on the information supplied.

### 🤖 5. AI Construction Assistant
- Answer construction-related questions.
- Provide general guidance on construction processes, materials, and project workflows.
- Support interactive question-and-answer experiences through the web interface.

### 🌦️ 6. Weather-Aware Recommendations
- Retrieve weather information using the Open-Meteo API.
- Provide weather-related construction recommendations where applicable.
- Help users consider environmental conditions when planning outdoor site activities.

## 🛠️ Technology Stack

| Component | Technology |
|---|---|
| Backend | Python, FastAPI |
| ASGI Server | Uvicorn |
| AI Integration | Google Gemini API |
| Frontend | HTML, React, JavaScript, Babel |
| Image Processing | Pillow (PIL) |
| Weather Integration | Open-Meteo API |
| Containerization | Docker |
| Deployment | Render |
| Configuration | Environment variables |

## 🏛️ System Architecture

The application follows a web-based client-server architecture.

1. **Frontend:** Provides the user interface for uploading images, entering property information, requesting planning suggestions, and interacting with the construction assistant.
2. **FastAPI Backend:** Handles HTTP requests, processes inputs and uploaded images, and coordinates application workflows.
3. **AI Integration:** Communicates with the Google Gemini API to generate image-based observations and construction-related responses.
4. **Image Processing:** Uses Pillow to support image handling and preprocessing.
5. **Weather Integration:** Retrieves relevant weather information from the Open-Meteo API.
6. **Deployment:** Runs as a containerized application on Render, with environment variables used to configure external services.

### Architecture Diagram

```text
                ┌─────────────────────────┐
                │       User / Client     │
                └────────────┬────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │    Web Frontend         │
                │ HTML, React, JavaScript │
                └────────────┬────────────┘
                             │ HTTP Requests
                             ▼
                ┌─────────────────────────┐
                │    FastAPI Backend      │
                │   Python + Uvicorn      │
                └────────────┬────────────┘
                             │
                ┌────────────┼────────────┐
                ▼            ▼            ▼
        ┌─────────────┐ ┌───────────┐ ┌─────────────┐
        │ Gemini API  │ │ Pillow    │ │ Open-Meteo  │
        │ AI Analysis │ │ Processing│ │ Weather API │
        └─────────────┘ └───────────┘ └─────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │   Results & Guidance    │
                └─────────────────────────┘
```

## 📂 Project Structure

The following is a conceptual overview of the main application components. Actual filenames may differ depending on the repository implementation.

```text
MultiModal-Construction-intelligence/
│
├── app/
│   └── main.py
│
├── requirements.txt
├── Dockerfile
├── .env
├── .gitignore
└── README.md
```

- `app/` — Backend application code.
- `main.py` — Application entry point, assuming the backend uses this module path.
- `requirements.txt` — Python dependency list.
- `Dockerfile` — Container build configuration.
- `.env` — Local environment configuration; should not be committed to GitHub.
- `.gitignore` — Files and directories excluded from version control.
- `README.md` — Project documentation.

## 🚀 Getting Started

Follow these steps to run the project locally.

### Prerequisites

Ensure you have the following installed:

- Python 3.11 or a compatible version supported by the project dependencies
- Git
- pip
- A Google Gemini API key

### 1. Clone the Repository

```bash
git clone https://github.com/Mayankpawar28/MultiModal-Construction-intelligence.git
cd MultiModal-Construction-intelligence
```

### 2. Create a Virtual Environment

**macOS / Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows PowerShell**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install Dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file in the project root and configure your Gemini API credentials:

```env
GEMINI_API_KEY=your_gemini_api_key
GEMINI_MODEL=gemini-2.5-flash
```

Get your API key from [Google AI Studio](https://aistudio.google.com/apikey).

Replace `your_gemini_api_key` with your actual API key. Confirm that the selected model is supported by your API key and project configuration.

**Security note:** Never commit API keys, passwords, or other secrets to GitHub. Ensure `.env` is included in `.gitignore`.

### 5. Start the Application

If the project entry point is `app/main.py`, run:

```bash
uvicorn app.main:app --reload
```

Open the application in your browser:

- **Web Application:** http://127.0.0.1:8000/
- **Interactive API Documentation:** http://127.0.0.1:8000/docs
- **Alternative API Documentation:** http://127.0.0.1:8000/redoc

If the application uses a different entry point, update the Uvicorn command to match the actual project structure.

### 6. Verify Application Health

Check the health endpoint locally:

```text
http://127.0.0.1:8000/api/health
```

For the deployed application, visit:

https://multimodal-construction-intelligence.onrender.com/api/health

A successful response should indicate that the application is running. The exact response format depends on the backend implementation.

## ☁️ Deployment

The application is deployed on **Render** and uses environment variables to configure external services.

To deploy your own instance:

1. Fork or import the repository into your GitHub account.
2. Create a new web service on [Render](https://render.com/).
3. Connect the repository.
4. Configure the service to use the project's Dockerfile or the appropriate build and start commands.
5. Add the required environment variables, including `GEMINI_API_KEY` and `GEMINI_MODEL`.
6. Deploy the application.
7. Verify the deployed application and health endpoint.

Deployment settings must match the actual repository configuration. Do not expose API credentials in source code, logs, or public documentation.

## 🔐 Security and Responsible AI

- Store API keys in environment variables.
- Validate uploaded files and restrict unsupported file types and sizes.
- Handle external API errors and network failures gracefully.
- Treat AI-generated outputs as preliminary information, not verified engineering conclusions.
- Avoid uploading confidential construction plans or sensitive property information unless appropriate safeguards are in place.
- Verify safety-related recommendations with qualified professionals.

## ⚠️ Limitations

- AI-generated image observations may be incomplete or inaccurate.
- Visible cracks cannot be reliably classified for structural safety from images alone.
- Property valuation estimates depend on the quality and completeness of the supplied information.
- Weather-related recommendations depend on external data availability and relevance.
- AI responses may vary and should be independently verified.
- Application availability and performance depend on network connectivity, external APIs, and deployment resources.

**Important:** This platform is intended for informational and decision-support purposes. It is not a substitute for professional engineering inspections, certified property appraisals, site-specific safety assessments, or regulatory compliance checks.

## 🔮 Future Enhancements

- Advanced multimodal analysis of construction images and documents.
- Improved crack classification and structural assessment workflows.
- Construction material estimation and cost breakdowns.
- Project progress tracking and historical records.
- Downloadable inspection reports.
- Integration with construction project management tools.
- Enhanced dashboards, charts, and project visualizations.
- More detailed weather-aware scheduling recommendations.

## 🤝 Contributing

Contributions, suggestions, and bug reports are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Implement and test your changes.
4. Submit a pull request describing the changes.

Please avoid committing credentials, generated secrets, or sensitive project information.

## 📄 License

A license has not been specified in this documentation. Add a `LICENSE` file and update this section when the project's licensing terms have been decided.

## 👨‍💻 Project Information

**Project:** Multimodal Construction Intelligence Platform  
**Category:** Generative AI | Construction Technology | Real Estate Decision Support  
**Backend:** Python and FastAPI  
**AI Model Integration:** Google Gemini API  
**Deployment Platform:** Render

---

*Built to explore how AI can support construction workflows, preliminary site observations, project planning, and property-related decision-making.*
