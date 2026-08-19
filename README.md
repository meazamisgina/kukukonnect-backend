# KukuKonnect

KukuKonnect is a real-time IoT platform designed to help poultry farmers monitor and manage environmental conditions inside chicken coops.

The system connects ESP32-based sensors with a Django backend to collect temperature and humidity data, while configurable thresholds can trigger automated climate-control responses such as activating heaters or fans.

The platform combines IoT hardware, MQTT communication, backend APIs, persistent data storage, real-time monitoring, and automated environmental control.

## Key Features

- **Real-Time Environmental Monitoring** - Collects temperature and humidity readings from poultry coops.
- **Automated Climate Control** - Triggers configured heater or fan responses when environmental conditions cross defined thresholds.
- **IoT Device Management** - Manages connected ESP32 devices and their configuration.
- **MQTT Communication** - Provides communication between the IoT hardware and application services.
- **Real-Time Updates** - Streams current environmental readings to the monitoring interface.
- **Configurable Thresholds** - Supports adjustable temperature and humidity thresholds.
- **User Management** - Supports authenticated farmer and agrovet workflows.
- **REST APIs** - Provides APIs for users, devices, sensor readings, thresholds, and automation settings.

## System Architecture

The system combines on-farm sensing and control hardware with a cloud-backed application layer and a real-time monitoring interface.
<img width="1902" height="1054" alt="image" src="https://github.com/user-attachments/assets/55735217-ac7a-4239-a6af-13fe304024c1" />

The architecture consists of three main layers:

- **On-Farm Hardware** - DHT22 environmental sensors and ESP32-based control hardware connected to the physical coop.
- **Application Layer** - Django REST APIs, PostgreSQL, and MQTT/HiveMQ communication services.
- **User Interface** - A web/PWA monitoring interface for farmers and agrovets.

The system uses MQTT for IoT communication and real-time application mechanisms to deliver current environmental readings to the monitoring interface.

## How It Works

1. ESP32 hardware collects temperature and humidity readings from the coop.
2. Sensor data is communicated through MQTT/HiveMQ.
3. Application services receive and process the environmental data.
4. Environmental readings and device configuration are stored in PostgreSQL.
5. Configured temperature and humidity thresholds are evaluated.
6. When environmental conditions cross configured thresholds, the system can trigger the appropriate climate-control response.
7. Current readings are delivered to the monitoring interface in real time.
8. Farmers can monitor coop conditions and manage configured environmental thresholds through the application.

## Technology Stack

### Backend

- Python
- Django
- Django REST Framework
- PostgreSQL
- JWT Authentication
- OpenAPI / drf-spectacular

### IoT & Real-Time Communication

- ESP32
- DHT22
- MQTT
- HiveMQ
- WebSockets

### Frontend

- Next.js
- React.js
- Progressive Web App (PWA)

### Development & Deployment

- Docker
- Gunicorn
- Heroku
- Git

## Data Model

The backend uses PostgreSQL to manage the core entities required by the platform, including:

- Users
- IoT devices
- Environmental readings
- Device configuration
- Temperature and humidity thresholds
- Automation settings

The API layer exposes these resources through Django REST Framework with authenticated access to application workflows.

## API Documentation

The backend uses `drf-spectacular` to generate OpenAPI documentation.

When running the application locally, API documentation can be accessed through the generated Swagger UI and ReDoc interfaces.

## MVP Demonstration

A recorded MVP demonstration shows the physical IoT setup and environmental monitoring workflow, including the coop hardware and automated climate-control system.

[Watch the MVP demonstration](https://drive.google.com/file/d/1Yp5naPuyF-sR_srePZohRImCHGOM9oEI/view?usp=sharing)

## Screenshots

### Physical Prototype

<img width="1280" height="896" alt="image" src="https://github.com/user-attachments/assets/ce6b2f03-0cfe-4663-96fa-f59df33b8506" />
<img width="1564" height="808" alt="image" src="https://github.com/user-attachments/assets/82c05b4f-3017-4898-b29f-c551a723559f" />
<img width="1583" height="774" alt="image" src="https://github.com/user-attachments/assets/ef0cd12c-d95a-4826-9cb9-09175bf62af4" />
<img width="1580" height="765" alt="image" src="https://github.com/user-attachments/assets/00dce115-993f-4a79-ac10-ca75bc567047" />
<img width="1257" height="784" alt="image" src="https://github.com/user-attachments/assets/dc5df5c9-79c2-4c61-937e-aebc2367557e" />
<img width="779" height="568" alt="image" src="https://github.com/user-attachments/assets/7bb74b9a-e145-497f-aa6a-731d8695b9f1" />

### Monitoring Interface

<img width="1840" height="1014" alt="image" src="https://github.com/user-attachments/assets/62eb6744-9131-470d-9ed6-d0ca460b0d4c" />
<img width="1920" height="942" alt="image" src="https://github.com/user-attachments/assets/11474edb-9ac2-435a-aef6-d50ef6a5f55d" />



## Getting Started

Follow these instructions to run the backend locally for development and testing.

### Prerequisites

- Python 3.10+
- pip
- virtualenv
- PostgreSQL
- MQTT broker
- Git

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/akirachix/kukukonnect-backend.git
cd kukukonnect-backend
```
   
2. **Create and activate a virtual environment**
```
python -m venv kukuenv
```

**macOS/Linux**
```
source kukuenv/bin/activate
```


**Windows**
```powershell
kukuenv\Scripts\activate

```


3. **Install dependencies**
```bash
pip install -r requirements.txt

```


4. **Configure environment variables**

Create a `.env` file containing the required application configuration.

6. **Apply database migrations**
```bash
python manage.py migrate

```


6. **Run the development server**
```bash
python manage.py runserver

```


The backend will then be available locally at:

```text
[http://127.0.0.1:8000/](http://127.0.0.1:8000/)
```

## Project Structure

```text
kukukonnect-backend/
├── api/
├── devices/
├── sensors/
├── users/
├── kukukonnect/
├── manage.py
├── requirements.txt
└── README.md
