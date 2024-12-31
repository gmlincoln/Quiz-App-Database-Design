# Quiz App Database Schema

This repository contains the database schema for the Quiz App, designed to manage users, quizzes, questions, answer options, and student responses efficiently.

## Overview

The Quiz App database supports:

- User management (teachers and students)
- Quiz creation and participation
- Tracking answers and ensuring data integrity through relational design

---

## Entity-Relationship (ER) Diagram

Below is the ER diagram for the database schema:

![ER Diagram](./1.%20ER%20Diagram/ER-Diagram%20Quiz%20App.png)

> Replace `path_to_your_er_diagram_image.png` with the actual path or URL to your ER diagram image.

---

## Database Tables

The schema is designed with the following tables:

### 1. Users

- **Purpose:** Manage teacher and student data
- **Primary Key:** `id`

### 2. Quizzes

- **Purpose:** Store quiz metadata
- **Primary Key:** `id`
- **Foreign Key:** `teacher_id` references `users.id`

### 3. Questions

- **Purpose:** Store questions for quizzes
- **Primary Key:** `id`
- **Foreign Key:** `quiz_id` references `quizzes.id`

### 4. Options

- **Purpose:** Store answer options for each question
- **Primary Key:** `id`
- **Foreign Key:** `question_id` references `questions.id`

### 5. Student_Answers

- **Purpose:** Track student responses
- **Primary Key:** `id`
- **Foreign Keys:**
  - `student_id` references `users.id`
  - `quiz_id` references `quizzes.id`
  - `question_id` references `questions.id`
  - `option_id` references `options.id`
