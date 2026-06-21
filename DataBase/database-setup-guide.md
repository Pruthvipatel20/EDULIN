# Database Setup Guide

## Overview

This document explains the database structure and setup process used in the EDULIN Educational Learning Platform.

The database module is responsible for storing user information, learning progress, quiz results, and managing relationships between different entities within the application.




The project uses:

* PostgreSQL Database
* Prisma ORM
* TypeScript
* Next.js

---

## Database Structure

The database consists of three main tables:

### User

Stores user account information.

Fields:

* id
* email
* name
* password
* createdAt
* updatedAt

Purpose:

* User registration
* User authentication
* User management

---

### UserSubject

Stores learning progress for each subject.

Fields:

* id
* userId
* subject
* progress
* createdAt
* updatedAt

Purpose:

* Track subject completion
* Monitor learning progress
* Store educational activity

---

### UserQuiz

Stores quiz results and performance.

Fields:

* id
* userId
* quizId
* score
* completed
* createdAt
* updatedAt

Purpose:

* Track quiz attempts
* Store quiz scores
* Monitor student performance

---

## Database Relationships

### User → UserSubject

One User can have multiple subjects.

```text
User
  │
  └── UserSubject
```

---
OAOAOAOAOAOAOAOAOAOAOA
OAOAOAOA### User → UserQuiz

OAOAOAOAOAOne User can have multiple quiz records.
OAOAOAOAOAOA
```text
User
OAOAOAOAOA  │
  └── UserQuiz
OAOAOAOAOAOA```

---
OAOAOAOAOAOAOA
OAOAOAOAOAOAOA## Database Schema File
OAOAOAOAOA
File:
OAOAOAOA
```text
OAOAOAOAOAdatabase-schema.prisma
```
OAOAOAOAOAOAOAOAOAOA
OAOAOAOAOAOAResponsibilities:
OAOAOAOAOAOA
OAOAOAOAOAOA* Define database models
* Configure relationships
OAOAOAOAOAOAOAOAOAOAOAOAOAOAOAOAOA* Configure constraints
* Generate Prisma Client

OAOAOAOAOA---

## Database Migration File

File:
OAOAOAOAOA
OAOAOAOA```text
database-migration.sql
OAOAOAOAOA```
OAOAOAOA
Responsibilities:

OAOAOAOAOA* Create tables
* Create indexes
OAOAOAOAOAOAOAOAOAOAOAOAOA* Add foreign keys
OAOAOAOAOA* Configure cascade deletion
OAOAOAOA
OAOA---
OAOAOA
## Database Client
OAOAOAOA
File:
OAOAOA
```text
OAOAOAOAdatabase-client.ts
```
OAOAOAOAOAOA
OAOAOAResponsibilities:
OAOA
OAOA* Initialize Prisma Client
* Manage database connections
OAOA* Reuse database instances
* Configure query logging

---

OA## Environment Variables

Create a .env file:
OAOA
```env
DATABASE_URL=postgresql://username:password@localhost:5432/edulin
```

---

## Installation Steps

### Install Dependencies

```bash
npm install
```

### Install Prisma

```bash
npm install prisma @prisma/client
```

### Generate Prisma Client

```bash
npx prisma generate
```

### Run Database Migration

```bash
npx prisma migrate dev
```

### Start Application

```bash
npm run dev
```

---

## Security Considerations

* Store database credentials in environment variables.
* Never commit .env files to GitHub.
* Use unique constraints for user emails.
* Enable foreign key constraints to maintain data integrity.
* Use password hashing before storing credentials.

---

## Future Enhancements

* Subject categories
* Achievement tracking
* User analytics
* Learning history
* Advanced reporting
* Admin database tools

---

## Module Maintainer

Member B

Responsibilities:

* Database Design
* Prisma Schema Management
* Database Migration Management
* Database Documentation

---

## Version

Database Module Version: 1.0

Project: EDULIN Educational Learning Platform

