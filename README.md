# Healthcare Management Platform

A comprehensive platform that connects doctors, patients, pharmacists, and administrators under one unified system.

---

## What We're Building

A full-featured healthcare management system that handles everything from scheduling consultations to managing medical records, pharmacy inventory, and billing — all in one place.

---

## Core Features

### 👨‍⚕️ Doctor Management
- Doctor profiles with specialization and language preferences
- Session and appointment scheduling
- Access to patient records and transcripts

### 🧑‍🤝‍🧑 Patient Management
- Patient profiles with medical history, blood group, and emergency contacts
- QR-based patient identification
- Multi-language support
- Record and lab report access

### 📅 Sessions & Appointments
- Schedule, track, and manage consultations
- Support for in-person and remote sessions
- Automatic session transcription

### 📝 Medical Records
- Detailed records per consultation including diagnosis, vitals, and prescriptions
- Lab report integration
- Follow-up tracking
- Bill generation per visit

### 🧾 Transcripts
- AI-powered transcription of doctor-patient sessions
- Linked directly to records for easy reference

### 🧪 Lab Reports
- Order and track lab tests per patient
- Link results back to medical records
- Support for structured data and file-based reports (e.g., PDFs, scans)

### 💊 Pharmacy & Medicines
- Medicine inventory management
- Pharmacist-controlled stock updates
- Medicine details including dosage, cost, and expiry

### 💰 Billing
- Per-record bill generation
- Tracks consultation fees, medicine costs, and lab charges

### 🔐 Role-Based Access
- Separate roles for Doctors, Patients, Pharmacists, and Admins
- Each role has access only to what they need

---

## Schemas Overview

| Schema | Purpose |
|---|---|
| Doctors | Stores doctor profiles and their sessions |
| Patients | Stores patient profiles, records, and health info |
| Sessions | Tracks each consultation between a doctor and patient |
| Transcripts | Stores session transcriptions linked to records |
| Records | Full consultation record including vitals, diagnosis, and medicines |
| Lab Reports | Lab test orders and results linked to records |
| Medicines | Pharmacy inventory with dosage and cost info |
| Pharmacists | Pharmacist profiles with inventory access |
| Admins | Platform administrators with system-wide access |

---

## Tech Stack & Infrastructure

The platform is fully hosted on **AWS** with the following services:

| Service | Usage |
|---|---|
| **Amazon S3** | Stores all multimedia files including lab report scans, PDF uploads, and profile pictures |
| **AWS CodePipeline** | Automates CI/CD — triggers build and deployment pipelines on code changes |
| **Amazon Bedrock** | Powers AI features such as session transcription and medical data processing using managed foundation models |
| **AWS Elastic Beanstalk** | Hosts and manages the backend application with auto-scaling and load balancing |
| **Amazon CloudFront** | Acts as the CDN and handles HTTP to HTTPS redirection, securing all client-server communication |

---

## Tech Notes

- All schemas include `created_at` and `updated_at` timestamps
- Soft delete (`isDeleted`) is used across schemas to comply with medical data retention requirements
- IDs are auto-generated (UUID format)
- Date of Birth is stored instead of Age to keep data accurate over time
