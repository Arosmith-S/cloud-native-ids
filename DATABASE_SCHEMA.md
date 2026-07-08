# Database Schema Design

## Purpose
Store GuardDuty findings and metadata for threat analysis and ML training.

## Table: findings

| Column | Type | Description |
|--------|------|-------------|
| id | SERIAL PRIMARY KEY | Auto-incrementing ID |
| finding_id | VARCHAR(255) UNIQUE | GuardDuty finding ID |
| severity | VARCHAR(20) | Low, Medium, High |
| finding_type | VARCHAR(255) | UnauthorizedAccess, Recon, Trojan, etc. |
| resource_type | VARCHAR(100) | IAM, EC2, S3, etc. |
| resource_id | VARCHAR(255) | Specific resource ARN |
| region | VARCHAR(50) | AWS region |
| source_ip | VARCHAR(50) | Source IP of suspicious activity |
| created_at | TIMESTAMP | When GuardDuty created finding |
| updated_at | TIMESTAMP | Last update timestamp |
| description | TEXT | Detailed description |
| raw_json | JSON | Full GuardDuty finding JSON |
| is_reviewed | BOOLEAN DEFAULT FALSE | Human reviewed? |
| confidence_score | FLOAT DEFAULT NULL | ML classifier confidence (0-1) |
| is_false_positive | BOOLEAN DEFAULT NULL | Human label: real or fake threat |
| status | VARCHAR(50) DEFAULT 'new' | new, investigating, resolved |
| created_in_db_at | TIMESTAMP DEFAULT CURRENT_TIMESTAMP | When record created |

## Future Tables (Days 7+)
- `threat_chains` — correlate multiple findings into attack chains
- `ip_reputation` — cache IP reputation scores
- `alerts_sent` — log when SNS alerts were triggered

## Indexes (for fast queries)
- `finding_id` (UNIQUE, for duplicate prevention)
- `severity` (for filtering)
- `created_at` (for time-range queries)
- `status` (for dashboard filtering)