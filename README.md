Multimodal Construction Intelligence Platform
An AI-powered construction intelligence platform that combines multimodal image analysis, project planning, real estate valuation, construction guidance, and weather-aware recommendations in a single web application.

Live Demo
Live Application: https://multimodal-construction-intelligence.onrender.com/

GitHub Repository: https://github.com/Mayankpawar28/MultiModal-Construction-intelligence

Overview
The Multimodal Construction Intelligence Platform uses AI to assist construction professionals, site engineers, and property stakeholders with preliminary construction-related assessments and decision support.

Users can upload construction site images, ask construction-related questions, explore project planning suggestions, and receive weather-aware recommendations through a web-based interface.

Key Features
Site Safety Review: Analyze construction site images for potential safety concerns.
Crack and Surface Review: Examine visible cracks and surface conditions for preliminary assessment.
Real Estate Valuation: Generate indicative property valuation estimates based on provided information.
Project Planning: Obtain AI-generated construction planning suggestions.
Construction Assistant: Ask construction-related questions and receive AI-generated guidance.
Weather-Aware Advisory: Access weather information and recommendations using external weather data.
Technology Stack
Backend: Python, FastAPI, Uvicorn

AI Integration: Google Gemini API

Frontend: HTML, React, JavaScript, Babel

Image Processing: Pillow (PIL)

Weather Data: Open-Meteo API

Deployment: Docker, Render

Architecture
The application uses a FastAPI backend to handle requests, process uploaded images, and communicate with the Gemini API. The frontend provides an interactive interface for users to select workflows, submit information, and view generated results.

Weather-related recommendations use external weather data where applicable.

Getting Started
Prerequisites
Python 3.11 or compatible version
Git
A Google Gemini API key
1. Clone the Repository
git clone https://github.com/Mayankpawar28/MultiModal-Construction-intelligence.git
cd MultiModal-Construction-intelligence
2. Create a Virtual Environment
Windows PowerShell:

python -m venv .venv
.\.venv\Scripts\Activate.ps1
Linux/macOS:

python -m venv .venv
source .venv/bin/activate
3. Install Dependencies
pip install -r requirements.txt
4. Configure Environment Variables
Create a .env file in the project root and add your Gemini API key:

GEMINI_API_KEY=your_gemini_api_key
GEMINI_MODEL=gemini-2.5-flash
Obtain an API key from Google AI Studio.

Never commit .env files, API keys, or other sensitive credentials to GitHub.

5. Run the Application
uvicorn app.main:app --reload
Open the application at:

http://127.0.0.1:8000/

Interactive API documentation is available at:

http://127.0.0.1:8000/docs

6. Health Check
The application provides a health endpoint at:

/api/health
For the deployed application, visit:

https://multimodal-construction-intelligence.onrender.com/api/health

Deployment
The project is deployed on Render and uses environment variables to configure external AI services.

To deploy your own instance:

Fork or import the GitHub repository into Render.
Configure the service using the repository's Dockerfile.
Add GEMINI_API_KEY in the environment variables.
Deploy the service and verify the health endpoint.
Limitations and Responsible Use
AI-generated assessments may be incomplete or inaccurate.
Image-based observations are preliminary and cannot replace professional site inspections.
Property valuations are indicative estimates, not certified appraisals.
Safety-related outputs must be verified by qualified construction and safety professionals.
Application functionality depends on external API availability, network connectivity, and deployment resources.
This platform is intended for informational and decision-support purposes, not as a substitute for professional engineering judgment or regulatory compliance checks.

Future Enhancements
Advanced multimodal analysis of construction images and documents.
Integration with construction project management systems.
Improved cost estimation and material planning.
Historical project data and progress tracking.
Enhanced reporting and visualization.
