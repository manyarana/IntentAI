# System Design Document: IntentAI Decision Engine

---

## 1. System Overview

IntentAI is a modular AI-powered decision engine built using Amazon Bedrock for NLP and a Python-based multi-factor ranking system. The system transforms user queries into structured insights and generates ranked, explainable recommendations.

---

## 2. High-Level Architecture

User → Backend API → Amazon Bedrock → Ranking Engine → Explanation Layer → UI Output  
                                              ↑  
                                   Logging & Feedback Loop  

---

## 3. Architecture Components

### 3.1 User Layer
- Chat-based interface (Web)
- Accepts natural language input

---

### 3.2 Backend Layer
- Built using Flask or FastAPI
- Handles input validation
- Routes requests to AI layer

---

### 3.3 AI Processing Layer

**Amazon Bedrock (Claude 3.5 Sonnet or equivalent)**

Responsible for:
- Intent detection
- Mood analysis
- Structured JSON generation
- Confidence score output

Example structured output:

```json
{
  "intent": "healthy_food",
  "budget": 300,
  "mood": "post_workout",
  "confidence": 0.91
}
