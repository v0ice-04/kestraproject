# Disaster Response Automation Platform  

### Overview  
The **Disaster Response Automation Platform** is an open-source system designed to enhance disaster management efforts by automating the collection, processing, and dissemination of critical disaster-related information. Built on **Kestra**, this platform provides a scalable and declarative approach to workflow orchestration, ensuring seamless integration and processing of data from various APIs.  

---

## Features  
- **Kestra Workflow Automation**: Centralized orchestration for all disaster-related tasks, from data fetching to notification.  
- **Weather Monitoring**: Fetches current weather data using the OpenWeatherMap API.  
- **Earthquake Tracking**: Retrieves earthquake data from the USGS Earthquake API for seismic event analysis.  
- **Disaster Alerts**: Collects real-time disaster alerts via the ReliefWeb API.  
- **Data Processing**: Aggregates and processes the collected data using a Python script within a Kestra task.  
- **Email Notifications**: Sends automated disaster alerts to specified recipients for timely response.  

---

## Architecture  

1. **Workflow Orchestration**  
   Kestra orchestrates tasks defined declaratively in YAML, managing the dependencies between data collection, processing, and notification steps.  

2. **Data Collection**  
   APIs for weather, earthquakes, and disaster alerts provide raw data through individual Kestra tasks.  

3. **Data Processing**  
   A Python script, executed within a Kestra task, processes the collected data to generate actionable insights.  

4. **Notification System**  
   Kestra triggers an email task to send disaster alerts with critical event details.  

---

## Requirements  

- Kestra installation (self-hosted or Docker setup)  
- Python 3.x for data processing  
- An OpenWeatherMap API key  
- Access to the USGS Earthquake and ReliefWeb APIs (publicly accessible)  
- SMTP setup for email notifications  

---

## Installation  

1. **Install Kestra**  
   Follow the official [Kestra installation guide](https://kestra.io/docs/installation/).  

2. **Clone this repository**  
   ```bash
   git clone https://github.com/your-username/disaster-response-platform.git
   cd disaster-response-platform
Deploy workflows
Upload the Kestra workflow YAML file:

kestra upload disaster-platform.yaml
Configure Secrets
Replace the placeholder in secrets.openweather_api_key with your OpenWeatherMap API key.

Set Variables
Update parameters.city in the workflow to specify the target city for weather monitoring.

Usage
Start the Kestra server:
kestra start

Trigger the workflow:

bash
kestra execute disaster.platform

Monitor execution:

View real-time execution logs in the Kestra UI.
Check email notifications for disaster alerts.

Project Structure
disaster-response-platform/
├── workflows/
│   ├── disaster-platform.yaml     # Kestra workflow definition /n
├── tasks/
│   ├── fetch-weather/             # Kestra task for weather data /n
│   ├── fetch-earthquake/          # Kestra task for earthquake data  /n
│   ├── fetch-alerts/              # Kestra task for disaster alerts  /n
│   ├── process-data/              # Kestra task for data processing  /n
│   ├── notify-email/              # Kestra task for email notification  /n
├── variables.yaml                 # Workflow parameters and variables  /n
├── secrets.yaml                   # Secure API keys and secrets  /n
├── README.md                      # Project documentation  /n
└── requirements.txt               # Python dependencies for processing script  /n

Acknowledgments
Kestra
OpenWeatherMap API
USGS Earthquake API
ReliefWeb API
Feel free to reach out if you have any questions or suggestions!
