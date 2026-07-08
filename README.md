# Cloud-Native Intrusion Detection System (IDS)

## Project Overview
A real-time intrusion detection system built on AWS that monitors cloud infrastructure for security threats and uses machine learning to filter false positives.

## Architecture
GuardDuty (Threat Detection)
↓
EventBridge (Event Router)
↓
Lambda (Event Processor)
↓
RDS PostgreSQL (Threat Storage)
↓
ML Classifier (Alert Filtering)
↓
Django Dashboard (Visualization)
↓
SNS (Alerts)
## Tech Stack
- **Cloud Platform:** AWS
  - GuardDuty (Threat Detection)
  - CloudTrail (API Audit Logs)
  - VPC Flow Logs (Network Monitoring)
  - Lambda (Serverless Processing)
  - EventBridge (Event Routing)
  - RDS PostgreSQL (Database)
  - SNS (Alerting)
  - EC2 (Hosting)
  - IAM (Access Control)

- **Backend:** Django + Python
- **Frontend:** Django Templates + Chart.js
- **ML:** scikit-learn (Threat Classification)
- **Database:** PostgreSQL

## Project Goal
Reduce false positive alerts in cloud security monitoring by 80%+ using adaptive ML classification.

## Timeline
- **Days 1-2:** AWS Infrastructure Setup
- **Days 3-4:** Lambda + RDS Pipeline
- **Days 5-6:** SNS Alerting + Event Processing
- **Days 7-9:** Data Collection + Django Setup
- **Days 10-12:** ML Model Development
- **Days 13-14:** Integration + Dashboard UI
- **Day 15:** Testing & Deployment

## Key Features (To Be Implemented)
- [ ] Real-time threat detection from GuardDuty
- [ ] Automatic threat storage in PostgreSQL
- [ ] ML-based false positive filtering
- [ ] Django web dashboard
- [ ] Threat visualization & analytics
- [ ] Alert confidence scoring
- [ ] Email/SMS notifications for high-confidence threats

## Results (To Be Updated)
- False Positive Reduction: [TBD]
- Alert Processing Latency: [TBD]
- Model Accuracy: [TBD]

## Author
Dafyd Paul

## License
MIT
