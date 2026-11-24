# My Project

## Introduction

This project uses AI to analyze shipment exceptions.

## Technologies Used

- Python
- FastAPI
- PostgreSQL
- SQLAlchemy

## Installation

1. Clone the repository.
2. Create a virtual environment.
3. Install dependencies.


# AI-Powered Logistics Shipment Exception Intelligence System

## 1. Project Overview

The AI-Powered Logistics Shipment Exception Intelligence System is a backend application designed to manage shipments, track shipment events, and intelligently analyze delivery exceptions using AI.

The system uses Natural Language Processing (NLP) to classify shipment exceptions, identify similar historical incidents, determine severity, and recommend the appropriate operational team.

It also provides APIs for shipment tracking, team workload, exception reporting, and delivery performance analysis.

## 2. Problem Statement

Logistics companies handle thousands of shipments and receive different types of delivery updates.

Manually identifying delivery problems, categorizing exceptions, and assigning them to the appropriate teams can be time-consuming.

This system aims to automate these tasks using AI and rule-based business logic.

## 3. Key Features

- Shipment registration and tracking.
- Shipment event management.
- AI-powered exception classification.
- Ranked exception predictions with confidence scores.
- Similar historical incident detection.
- Automatic severity assessment.
- Recommended operational team assignment.
- Manual team assignment override.
- Shipment status management.
- Exception and delivery performance reports.
- Team workload reporting.
- Assignment history tracking.

## 4. Technologies Used

- Python
- FastAPI
- PostgreSQL
- SQLAlchemy
- Pydantic
- Alembic
- Hugging Face Transformers
- Sentence Transformers
- PyTorch

## 5. Project Architecture

The application follows a layered architecture:

Route → Service → Repository → Database

- **Routes:** Handle HTTP requests and responses.
- **Services:** Implement business logic.
- **Repositories:** Handle database operations.
- **Models:** Define database tables.
- **Schemas:** Validate request data and response structures.
- **AI:** Contains machine learning and NLP functionality.

## 6. Installation and Setup

### Clone the repository

```bash
git clone <repository-url>
cd shipment_intelligence
```

### Create a virtual environment

```bash
python -m venv .venv
```

### Activate the virtual environment

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

### Install dependencies

```bash
pip install -r requirements.txt
```

## 7. Environment Variables

Create a `.env` file in the root directory.

```env
DATABASE_URL=postgresql+psycopg://username:password@localhost:5432/shipment_intelligence_db
```

Replace the database credentials with your local PostgreSQL configuration.

## 8. Database Migrations

Apply database migrations using Alembic:

```bash
alembic upgrade head
```

## 9. Run the Application

Start the FastAPI development server:

```bash
uvicorn app.main:app --reload
```

The application will run at:

http://127.0.0.1:8000

## 10. API Documentation

FastAPI provides interactive API documentation through Swagger UI.

http://127.0.0.1:8000/docs

### Main API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | /shipments | Register shipment |
| GET | /shipments | Get shipments |
| GET | /shipments/{tracking_number} | Get shipment details |
| POST | /shipments/{tracking_number}/events | Create shipment event |
| GET | /shipments/{tracking_number}/events | Get shipment events |
| POST | /events/{event_id}/analyze | Analyze shipment exception |
| GET | /events/{event_id}/similar | Find similar incidents |
| PATCH | /shipments/{tracking_number}/status | Update shipment status |
| POST | /events/{event_id}/override | Override assigned team |
| GET | /events/{event_id}/assignment-history | Get assignment history |
| GET | /reports/exceptions | Exception summary |
| GET | /reports/delivery-performance | Delivery performance |
| GET | /reports/team-workload | Team workload |

## 11. AI Components

### Exception Classification

Uses a zero-shot classification model to classify shipment events into categories such as:

- Address Issue
- Customer Unavailable
- Package Damage
- Vehicle/Route Delay
- Weather Disruption
- Other

### Similar Incident Detection

Uses sentence embeddings and cosine similarity to identify historical shipment events with similar descriptions.

### Severity Assessment

Uses rule-based logic to determine exception severity based on factors such as:

- Delivery deadline.
- Failed delivery attempts.
- Package damage.
- Time since the last progress update.

### Team Recommendation

Recommends an operational team based on the predicted exception category.

## 12. Future Improvements

- Improve classification accuracy.
- Add automated notifications.
- Optimize similarity search.
- Add analytics dashboards.
- Improve AI model performance.
