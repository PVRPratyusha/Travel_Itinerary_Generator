# Generative AI–Powered Travel Itinerary Generator   

This project uses generative AI models and real-time APIs to automatically create a personalized travel itinerary. It generates hotel suggestions, sightseeing recommendations, weather insights, restaurant picks, transportation comparisons, interactive maps, and a professionally formatted itinerary PDF.

---

## Overview  

The Travel Itinerary Generator builds an end-to-end multimodal AI system that combines:

- **LLM-based reasoning** (Gemini + GPT-2)  
- **Real-time geospatial API calls** (Geoapify)  
- **Live weather integration** (WeatherAPI)  
- **Dynamic routing & mapping** (Folium)  
- **PDF itinerary generation** (ReportLab)  
- **AI agents** for sightseeing, food, and transport

The output is a complete, actionable travel plan tailored to the user’s route, dates, budget level, and interests.

---

## Key Features  

### 1. Hotel Recommendations  
Generated based on user-selected budget tier (low, medium, high).

### 2. Sightseeing Suggestions  
AI-driven selection of attractions aligned to interests  
(beaches, museums, food, history, culture, nature, etc.).

### 3. Restaurant Recommendations  
Catered to cuisine preferences and proximity to attractions.

### 4. Weather Forecasting  
- Real-time weather  
- 10-day forecasts  
- Seasonal fallback logic for long-range trips

### 5. Transport Planning  
Compares walking, public transit, taxi, and rideshare options  
with estimated cost and travel time.

### 6. Interactive Maps  
Generates an HTML map showing:  
- Travel route  
- City markers  
- Daily attractions  
- Restaurants

### 7. PDF Itinerary Generation  
Creates a clean, structured PDF with:  
- Trip overview  
- Day-by-day breakdown  
- Weather  
- Transport  
- Restaurants  
- Travel tips

---

## Technologies Used  

### **APIs**
- **Geoapify API** – geocoding, routing, place search  
- **WeatherAPI** – weather data (current, forecast, historical)  
- **Google Gemini 1.5 Flash** – narrative itinerary generation  
- **OpenRouter LLM API** – GPT-style text refinement  

### **AI Models**
- **Gemini-1.5-Flash** for narrative creation  
- **GPT-2 (HuggingFace)** for descriptions and travel tips  

### **Python Libraries**
- `transformers`, `accelerate`, `torch`  
- `folium`  
- `requests`  
- `reportlab`  
- `typing`, `datetime`, `logging`

---

## Project Structure  
```
Travel_Itinerary_Generator/
│
├── Travel_Itinerary_Generator.ipynb # Main notebook
├── README.md # Project documentation
├── generated_pdfs/ # (Optional) Output PDFs
├── generated_maps/ # (Optional) Output HTML maps
```

---

## How the System Works  

### **1. User Input**
- Start and destination cities  
- Dates and number of days  
- Waypoints  
- Budget level  
- Interests  

### **2. API Data Retrieval**
- Coordinates (Geoapify)  
- Weather (WeatherAPI)  
- Places & restaurants (Geoapify)  

### **3. AI Agent Pipeline**
- **Sightseeing Agent:** selects relevant attractions  
- **Transport Agent:** generates realistic transportation modes  
- **Food Agent:** finds restaurants based on cuisine & distance  
- **LLM Layer:**  
  - GPT-2 → content refinement and travel tips  
  - Gemini → day-by-day narrative itinerary  

### **4. Output Generation**
- Daily plan dictionaries  
- AI-generated descriptions  
- Full narrative itinerary  
- Interactive Folium map  
- PDF report  

---

## Outputs  

### ✔ Interactive Map  
HTML file with markers, daily routes, legends, and popups.

### ✔ PDF Itinerary  
Includes:  
- Overview  
- Daily schedule  
- Weather  
- Attractions  
- Transportation  
- Restaurant recommendations  
- Tips from AI models  

### ✔ AI-Generated Content  
- Personalized narrative  
- Destination description  
- Budget-aligned tips  

---

## Running the Project  

Open the notebook in Google Colab and run:

```python
final_result = main()
```
##Notes
API keys must be generated and configured before running the notebook.
The system currently supports U.S. multi-city travel.
All outputs (PDF + map) are saved in the notebook’s working directory.

##Acknowledgements
This project was developed as part of CSYE 7380 – Theory & Practical Applications of AI Generative Modeling using a combination of LLMs, geospatial APIs, and multi-agent design.
