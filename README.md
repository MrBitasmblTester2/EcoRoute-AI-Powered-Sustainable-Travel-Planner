# EcoRoute-AI-Powered-Sustainable-Travel-Planner

Description: A platform that helps users plan eco-friendly trips by suggesting routes, accommodations, and activities with the lowest carbon footprint while optimizing travel costs and convenience.

## Tech Stack
- Python
- FastAPI
- ASP.NET Core

## Requirements
- Carbon footprint calculation engine (use public emissions datasets for accuracy)
- Eco-friendly accommodation and activity recommendations (aggregate data from public APIs or curated lists)
- AI itinerary optimization (start with rules-based matching before AI)

## Installation

### Python & FastAPI
1. Clone the repo:
   bash
   git clone https://github.com/your-org/EcoRoute-AI-Powered-Sustainable-Travel-Planner.git
   cd EcoRoute-AI-Powered-Sustainable-Travel-Planner/python-api
   
2. Create and activate a virtual environment:
   bash
   python3 -m venv env
   source env/bin/activate
   
3. Install dependencies:
   bash
   pip install -r requirements.txt
   
4. Create a `.env` file with the following variables:
   - `EMISSIONS_API_KEY`
   - `ACCOMMODATIONS_API_URL`
   - `ACTIVITIES_API_URL`

### ASP.NET Core
1. Navigate to the .NET project:
   bash
   cd EcoRoute.Api
   
2. Restore and build packages:
   bash
   dotnet restore
   dotnet build
   
3. Add an `appsettings.json` in the project root with:
   
   {
     "EmissionsApiKey": "<your_key>",
     "AccommodationsApiUrl": "<api_url>",
     "ActivitiesApiUrl": "<api_url>"
   }
   

## Usage
1. Start the FastAPI service:
   bash
   uvicorn main:app --reload --host 0.0.0.0 --port 8000
   
2. Start the ASP.NET Core service:
   bash
   dotnet run --project EcoRoute.Api
   

## Implementation Steps
1. Collect and preprocess public emissions datasets in Python.
2. Build a FastAPI service for carbon footprint calculations.
3. Integrate public accommodation and activity sources with aggregation endpoints.
4. Implement a rules-based engine for initial itinerary matching.
5. Add AI components for iterative itinerary optimization.
6. Expose RESTful endpoints in ASP.NET Core for unified access.
7. Secure environment variables and test services locally.
8. (Optional) Containerize services using Docker.

## API Endpoints
- GET /carbon-footprint?origin={origin}&destination={destination}
- GET /recommendations/accommodations?location={location}&preferences={preferences}
- GET /recommendations/activities?location={location}&preferences={preferences}
- POST /itinerary/optimize