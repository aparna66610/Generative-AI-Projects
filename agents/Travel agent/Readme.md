## 🛫 AI Travel Planner Plus

An advanced AI-powered travel planning application that generates comprehensive, personalized travel itineraries using OpenAI GPT-4o. This multi-agent system automates research, planning, weather analysis, activity booking, and logistics optimization to create the perfect travel experience.

---

## ✨ Key Features

### 🌍 **Comprehensive Travel Planning**
- **Personalized Research**: AI-powered destination research with targeted searches
- **Smart Itinerary Generation**: Day-by-day itineraries with time slots (Morning, Afternoon, Evening)
- **Travel Preferences**: Customize by travel style, budget range, interests, and dates
- **Cost Estimates**: Approximate costs for activities, meals, and accommodations

### 🌤️ **Weather Intelligence**
- **Free Weather Forecasts**: Real-time weather data using Open-Meteo API (no API key required!)
- **Packing Recommendations**: Smart packing suggestions based on weather conditions
- **Activity Adjustments**: Indoor alternatives suggested for unfavorable weather
- **Daily Weather Summaries**: Temperature, conditions, and precipitation probability

### 🎫 **Activity Booking Integration**
- **Automatic Booking Links**: Finds direct booking URLs for activities and attractions
- **Multiple Platforms**: Searches Viator, GetYourGuide, TripAdvisor, Klook, and official websites
- **Activity Extraction**: Automatically identifies activities from your itinerary
- **Easy Access**: Clickable links organized by day

### 🗺️ **Logistics & Transportation**
- **Route Optimization**: Plans optimal routes between attractions
- **Transportation Modes**: Suggests walking, public transit, taxi, or rental car options
- **Travel Time Estimates**: Realistic time estimates between locations
- **Efficiency Planning**: Minimizes travel time for better day planning

### 💾 **Multiple Export Formats**
- **Calendar Export (.ics)**: Import into Google Calendar, Apple Calendar, Outlook
- **Text Export (.txt)**: Plain text format for easy reading
- **Complete Guide**: Combined export with itinerary, weather, and booking links

### 🎯 **User Experience**
- **Intuitive Sidebar**: Easy API key management and preference settings
- **Progress Tracking**: Real-time progress indicators during generation
- **Toggle Features**: Enable/disable weather and activity booking features
- **Responsive Design**: Clean, modern Streamlit interface

---

## 🤖 Multi-Agent Architecture

The application uses **5 specialized AI agents** working together:

### 1. **Researcher Agent** 🔍
- **Role**: Searches for travel destinations, activities, and accommodations
- **Capabilities**:
  - Generates focused queries based on destination, duration, style, and budget
  - Uses DuckDuckGo (no API key) to gather top results
  - Organizes results by categories (Attractions, Restaurants, Accommodations, Activities, Tips)
  - Prioritizes recent and highly-rated options
  - Provides cost estimates when available

### 2. **Planner Agent** 📋
- **Role**: Generates detailed day-by-day itineraries
- **Capabilities**:
  - Creates time-structured itineraries (Morning: 9-12, Afternoon: 12-5, Evening: 5-9)
  - Includes activity descriptions and estimated costs
  - Suggests realistic travel times between locations
  - Provides meal recommendations with cuisine types and price ranges
  - Adds practical tips (best times to visit, booking requirements)
  - Formats with clear "Day X:" headers

### 3. **Weather Agent** 🌤️
- **Role**: Provides weather forecasts and packing suggestions
- **Capabilities**:
  - Analyzes weather data for destination and travel dates
  - Provides daily weather summaries with temperature and conditions
  - Suggests appropriate clothing and packing items
  - Recommends indoor alternatives for bad weather
  - Gives practical tips based on weather patterns
- **API**: Open-Meteo (completely free, no API key required)

### 4. **Activities Agent** 🎫
- **Role**: Identifies activities and suggests booking options
- **Capabilities**:
  - Extracts specific activities and attractions from itineraries
  - Suggests likely booking platforms (Viator, GetYourGuide, TripAdvisor, Klook, official sites)
  - Includes activity names, descriptions, and estimated prices when possible
  - Organizes links by day when possible
- **Tools**: LLM-only (no API key required)

### 5. **Logistics Agent** 🗺️
- **Role**: Plans transportation and routes between locations
- **Capabilities**:
  - Analyzes itinerary to identify locations
  - Suggests optimal routes and transportation modes
  - Estimates travel times between activities
  - Recommends efficient day plans to minimize travel time
  - Provides practical transportation tips
- **Tools**: LLM-only (no API key required)

---

## 🚀 Getting Started

### Prerequisites
- Python 3.8 or higher
- OpenAI API account (for GPT-4o)
  - Web search uses DuckDuckGo; no key needed

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/aparna66610/travel-agent.git
cd travel-agent
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

Required packages:
- `streamlit` - Web application framework
- `agno` - AI agent framework
- `openai` - OpenAI API client
- `duckduckgo-search` - Web search without API keys
- `beautifulsoup4` - Lightweight HTML parsing for snippets
- `icalendar` - Calendar file generation
- `requests` - HTTP requests (for weather API)

3. **Get API Keys**

#### Required APIs:
- **OpenAI API Key**: 
  - Sign up at [platform.openai.com](https://platform.openai.com/)
  - Get your API key from the dashboard
  - Required for all AI agents

#### Optional APIs:
- **Weather**: ✅ No API key needed! 
  - Uses free [Open-Meteo API](https://open-meteo.com)
  - Completely free with no usage limits
  - Automatically enabled when you check "Enable Weather Forecast"

4. **Run the application**
```bash
streamlit run travel_agent.py
```

The app will open in your browser at `http://localhost:8501`

---

## 📖 How to Use

### Step 1: Configure API Keys
1. Open the sidebar (click the arrow icon)
2. Enter your **OpenAI API Key** (required)
3. (Optional) Enable **Weather Forecast** checkbox (no API key needed!)

### Step 2: Set Travel Preferences
In the sidebar, configure your preferences:
- **Travel Style**: Adventure, Relaxation, Culture, Family-Friendly, Business, or Luxury
- **Budget Range**: Budget-Friendly, Mid-Range, or Luxury
- **Travel Start Date**: Select your departure date
- **Interests**: Select multiple interests:
  - Food & Dining
  - History & Culture
  - Nature & Outdoors
  - Nightlife
  - Shopping
  - Art & Museums
  - Sports

### Step 3: Enter Destination
1. In the main area, enter your destination (e.g., "Paris, France")
2. Select the number of days for your trip (1-30 days)
3. Click **"🚀 Generate Complete Itinerary"**

### Step 4: View Results
The app will generate:
1. **Main Itinerary**: Day-by-day schedule with time slots
2. **Weather Forecast** (if enabled): Daily weather and packing tips
3. **Activity Booking Links** (if enabled): Direct booking URLs for activities
4. **Export Options**: Download as calendar, text, or complete guide

### Step 5: Export Your Itinerary
- **📅 Calendar (.ics)**: Import into your calendar app
- **📄 Text (.txt)**: Plain text format
- **📦 Complete Guide**: Includes itinerary, weather, and booking links

---

## 💡 How It Works

### The Planning Process

1. **Research Phase** (15%)
   - Researcher Agent generates targeted search terms
   - Searches the web for activities, restaurants, accommodations
   - Organizes results by category with costs and ratings

2. **Weather Analysis** (30%) - Optional
   - Fetches weather forecast from Open-Meteo API
   - Weather Agent analyzes conditions and provides packing tips
   - Suggests weather-appropriate activities

3. **Logistics Planning** (45%)
   - Logistics Agent identifies all locations in the itinerary
   - Researches transportation options between locations
   - Plans optimal routes and estimates travel times

4. **Itinerary Creation** (60-75%)
   - Planner Agent combines all information
   - Creates day-by-day schedule with time slots
   - Includes meals, costs, and practical tips
   - Formats for easy reading

5. **Activity Booking** (75-90%) - Optional
   - Activities Agent extracts activity names from itinerary
   - Searches for booking links on popular platforms
   - Provides direct URLs for easy booking

6. **Completion** (100%)
   - All results displayed in organized sections
   - Ready for export or further customization

### Token Optimization
The app includes intelligent content truncation to:
- Stay within OpenAI API token limits (30,000 TPM)
- Reduce API costs
- Speed up processing
- Ensure reliable generation

---

## 📅 Using the Calendar Export Feature

After generating your travel itinerary:

1. Click the **"📅 Calendar (.ics)"** button
2. Save the `.ics` file to your computer
3. Import the file into your preferred calendar application:
   - **Google Calendar**: Settings → Import & Export
   - **Apple Calendar**: File → Import
   - **Outlook**: File → Open & Export → Import/Export
   - **Other calendar apps**: Use the import feature

4. Each day of your itinerary will appear as an all-day event
5. Complete details for each day's activities are included in the event description
6. Your itinerary is now synced across all your devices!

---

## 🎯 Best Practices

### For Best Results:
- **Be Specific**: Include country/city for destinations (e.g., "Paris, France" not just "Paris")
- **Set Realistic Dates**: Use actual travel dates for accurate weather forecasts
- **Select Relevant Interests**: Choose interests matching your travel style
- **Review Booking Links**: Verify booking links before purchasing
- **Save Exports**: Download your itinerary for offline access

### Performance Tips:
- **Shorter Trips**: Faster generation for 1-7 day trips
- **Disable Features**: Turn off weather/activities if not needed for faster processing
- **Clear Browser Cache**: If the app becomes slow, refresh your browser

---

## 🔧 Technical Details

### Architecture
- **Framework**: Streamlit for web interface
- **AI Framework**: Agno for multi-agent orchestration
- **Language Model**: OpenAI GPT-4o
- **Search Engine**: DuckDuckGo (no key required)
- **Weather API**: Open-Meteo (free, no key required)

### Token Management
- **Content Truncation**: Automatic truncation to stay within limits
- **Research Results**: Limited to 3,000 characters
- **Weather/Logistics**: Limited to 800 characters each
- **Activity Search**: Limited to 2,000 characters

### Error Handling
- Graceful degradation if APIs fail
- User-friendly error messages
- Optional features can be disabled
- Fallback mechanisms for missing data

---

## 📝 Features Comparison

| Feature | Status | API Required |
|---------|--------|--------------|
| AI-Powered Research | ✅ Included | OpenAI + DuckDuckGo (no key) |
| Personalized Itineraries | ✅ Included | OpenAI |
| Weather Forecasts | ✅ Included | Open-Meteo (Free) |
| Activity Booking Links | ✅ Included | OpenAI |
| Transportation Planning | ✅ Included | OpenAI |
| Calendar Export | ✅ Included | None |
| Multiple Export Formats | ✅ Included | None |
| Travel Preferences | ✅ Included | None |

---

## 🐛 Troubleshooting

### Common Issues:

**"API Key Error"**
- Ensure OpenAI key is entered correctly
- Check that the OpenAI key is active and has available credits

**"Token Limit Exceeded"**
- Try generating for shorter trips (fewer days)
- Disable weather or activity booking features
- The app automatically truncates content, but very long itineraries may still hit limits

**"Weather Not Loading"**
- Check your internet connection
- Verify destination name is spelled correctly
- Weather API is free and should work automatically

**"No Booking Links Found"**
- Some activities may not have online booking available
- Try searching manually using the activity names provided
- Ensure Activities Agent is enabled in sidebar

---

## 📚 Dependencies

See `requirements.txt` for complete list:
- `streamlit` - Web framework
- `agno` - AI agent framework  
- `openai` - OpenAI API client
- `duckduckgo-search` - Web search without API keys
- `beautifulsoup4` - HTML parsing for snippets
- `icalendar` - Calendar generation
- `requests` - HTTP requests

---

## 🎉 Future Enhancements

Potential features for future versions:
- **GitHub MCP Integration**: Faster processing and improved agent coordination using GitHub Model Context Protocol
- Multi-destination trip planning
- Hotel booking integration
- Flight price checking
- Real-time currency conversion
- Interactive map visualization
- Collaborative planning (multiple users)
- Custom activity recommendations
- Photo galleries integration

---

## 📄 License

This project is part of the Generative AI Projects repository.

---

## 🙏 Acknowledgments

- Built with [Agno](https://github.com/agno-ai/agno) agent framework
- Uses [OpenAI GPT-4o](https://openai.com/) for AI capabilities
- Weather data from [Open-Meteo](https://open-meteo.com/) (free API)
- Search powered by DuckDuckGo (no API key required)

## 👤 Author

**Aparna** - [@aparna66610](https://github.com/aparna66610)

AI Product Manager passionate about Generative AI, building Gen AI products.

- 🌐 GitHub: [github.com/aparna66610](https://github.com/aparna66610)
- 💼 LinkedIn: [in/sri-laxmi](https://www.linkedin.com/in/sri-laxmi)
- 📺 YouTube: [@sri_laxmi](https://youtube.com/@sri_laxmi)

---

## 💬 Support

For issues, questions, or contributions, please refer to the main repository.

---

**Happy Travel Planning! ✈️🌍**
