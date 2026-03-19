# 🚀 AI-Powered Parametric Insurance Platform for Gig Workers

---

## 📌 Problem Statement

Gig workers (Zomato/Swiggy delivery partners) face unpredictable income loss due to external disruptions such as heavy rain, extreme heat, pollution, traffic congestion, and sudden zone shutdowns.

### ❗ Constraints
- Cover **LOSS OF INCOME ONLY**
- ❌ No health, life, accidents, or vehicle repair coverage
- Weekly pricing model (mandatory)

---

## 👤 Persona: Food Delivery Worker

### Scenario

A delivery partner starts a peak-hour shift expecting high earnings.

Suddenly, heavy rain and traffic congestion disrupt operations.  
Order flow drops, delivery time increases, and the worker logs out early.

👉 Result: Significant income loss due to external factors

---

## ⚙️ Core Features

- Automated income protection (no manual claims)
- AI-powered real-time risk scoring
- Dynamic weekly premium pricing
- Parametric trigger-based payouts
- Advanced fraud detection system
- Real-time dashboard for users and admin

---

## 🌧️ External Disruptions

| Disruption        | Parameter      | Trigger Condition |
|------------------|--------------|------------------|
| Heavy Rain       | Rainfall     | > 50 mm/hr       |
| Extreme Heat     | Temperature  | > 45°C           |
| Air Pollution    | AQI          | > 300            |
| Traffic          | Delay Factor | > 3x             |
| Zone Shutdown    | Binary       | Active           |

---

# 🧠 Risk Score Calculation

## Step 1: Normalize Inputs
RainScore = min(rainfall / 50, 1)
HeatScore = min((temp - 35) / 10, 1)
AQIScore = min((AQI - 100) / 200, 1)
TrafficScore = min((delay - 1) / 2, 1)
ShutdownScore = 0 or 1

## Step 2: Weighted Risk Score
Risk Score =
(RainScore × 0.30) +
(HeatScore × 0.15) +
(AQIScore × 0.15) +
(TrafficScore × 0.20) +
(ShutdownScore × 0.20)

## Risk Interpretation

| Score | Meaning |
|------|--------|
| 0–30 | Safe |
| 30–60 | Medium |
| 60–80 | High |
| 80–100 | Extreme |

---

# 💰 Weekly Premium Calculation

## Base Premium
- Base Premium = ₹100/week

---

## Multipliers

### Risk Multiplier

| Risk Score | Value |
|------------|------|
| 0–30       | 0.8  |
| 30–60      | 1.0  |
| 60–80      | 1.3  |
| 80–100     | 1.7  |

---

### Behavior Factor
- No claims → 0.9
- Normal → 1.0
- Frequent claims → 1.2
---

### Coverage Multiplier (Plan Based)

| Plan     | Coverage | Multiplier |
|----------|----------|------------|
| Basic    | 60%      | 0.8        |
| Standard | 75%      | 1.0        |
| Premium  | 90%      | 1.3        |

---

## Final Premium Formula
- Premium = Base × Risk Multiplier × Behavior Factor × Coverage Multiplier
---

# 💸 Payout Calculation

## Step 1: Average Hourly Income
- AvgHourlyIncome = Last 7 days earnings / total hours worked
---

## Step 2: Disruption Factor (Derived from Risk Score)

| Risk Score | Factor |
|-----------|--------|
| 60–70     | 0.3    |
| 70–80     | 0.5    |
| 80–90     | 0.8    |
| 90–100    | 1.0    |

---

## Step 3: Lost Hours
- Lost Hours = Shift Duration × Disruption Factor
---

## Step 4: Final Payout
- Payout = AvgHourlyIncome × LostHours × Coverage %
---

# 🤖 AI/ML Integration

### 1. Risk Prediction
- Rule-based → upgraded to ML (XGBoost)

### 2. Lost Hours Prediction
- LostHours = ML(rain, temp, AQI, traffic, time, location)
### 3. Dynamic Pricing
- Premium ≈ % of predicted income loss
### 4. Fraud Detection
- Hybrid system (rules + ML anomaly detection)

---

# 🚨 Fraud Detection System

## Flags

- GPS Integrity
- Login Continuity
- Proximity
- Static Position
- Intentional Idle
- Device Fingerprint
- Historical Abuse
- Event Consensus
- Opportunity Loss

---

## Fraud Score
- Fraud Score = Σ (Flag × Weight)


  
---

## Decision Engine

| Score | Action |
|------|--------|
| < 0.3 | Approve |
| 0.3–0.6 | Review |
| > 0.6 | Reject |

---

# 🛡️ Adversarial Defense & Anti-Spoofing Strategy

## 1. Differentiation

### Genuine User
- Natural movement
- Consistent behavior
- Matches real disruptions

### Fraud Actor
- Teleporting GPS
- Static fake activity
- No real orders

---

## 2. Data Signals Beyond GPS

- GPS trajectory (not just coordinates)
- Speed & acceleration
- Device fingerprint
- IP address patterns
- Earnings behavior
- Claim frequency
- Cross-user comparison

---

## 3. UX Balance

| Case | Action |
|------|--------|
| Low risk | Instant payout |
| Medium | Soft review |
| High | Manual verification |

### Key Principles
- No harsh rejection
- Grace for network failure
- Transparent flags
- Appeal mechanism

---

# 🏗️ System Architecture
User App
↓
Data Layer (APIs + GPS + Earnings)
↓
Backend Server
↓
AI Layer (Risk + Pricing + Fraud)
↓
Decision Engine
↓
Payout System
↓
Dashboard

---

# 📱 Platform Choice

### Mobile App
- GPS tracking required
- Real-time updates
- Best suited for gig workers

---

# 🔌 API Integrations

- Weather API
- AQI API
- Google Maps API
- Mock delivery platform API
- Razorpay sandbox

---

# 🗄️ Tech Stack

Frontend: React Native / Flutter  
Backend: Node.js / FastAPI  
ML: Python (Scikit-learn, XGBoost)  
Database: PostgreSQL  
Realtime: WebSockets  

---


# 🧪 Development Plan

### Phase 1
- UI + risk engine

### Phase 2
- automation + pricing + payout

### Phase 3
- fraud detection + ML + dashboards

---

# 💡 Key Innovations

- Income-aware insurance
- Real-time AI risk scoring
- Dynamic pricing model
- Parametric payouts
- Advanced fraud detection

---

# 🎯 Final Statement

This system transforms traditional insurance into a real-time, AI-driven financial safety net for gig workers, ensuring fairness, transparency, and scalability.
