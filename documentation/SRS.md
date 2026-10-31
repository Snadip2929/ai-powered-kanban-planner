# Software Requirements Specification (SRS)

## AI-Powered Kanban Planner

| Document Information | Details |
|---|---|
| Project Name | AI-Powered Kanban Planner |
| Document Name | Software Requirements Specification |
| Version | 1.0.0 |
| Status | Draft |
| Backend | Java, Spring Boot |
| Frontend | React.js, Tailwind CSS |
| Database | MongoDB |
| AI Provider | Google Gemini API |

---

## 1. Introduction

### 1.1 Purpose

This Software Requirements Specification (SRS) document describes the functional and non-functional requirements of the AI-Powered Kanban Planner.

It defines the expected system behavior, software components, external interfaces, database requirements, and technical constraints.

This document will serve as a reference for developers, testers, and project stakeholders throughout the software development lifecycle.

### 1.2 Product Scope

The AI-Powered Kanban Planner is a web-based application designed to simplify task planning and improve individual and team productivity.

The application will allow users to create projects, generate tasks using AI, organize tasks through a visual Kanban board, and monitor productivity through analytics.

### 1.3 Intended Audience

- Software Developers
- Software Testers
- Project Contributors
- Academic Evaluators
- Project Stakeholders

### 1.4 Definitions and Abbreviations

| Term | Description |
|---|---|
| SRS | Software Requirements Specification |
| API | Application Programming Interface |
| AI | Artificial Intelligence |
| JWT | JSON Web Token |
| CRUD | Create, Read, Update, Delete |
| UI | User Interface |
| DB | Database |
| DnD | Drag and Drop |

---

## 2. Overall Description

### 2.1 Product Perspective

The application will follow a frontend-backend architecture.

The React frontend will communicate with the Spring Boot backend through REST APIs.

The backend will manage business logic, database operations, authentication, and AI integration.

MongoDB will store application data, while Google Gemini API will provide AI-powered task generation and summaries.

### 2.2 Product Functions

The major functions of the application are:

1. User Registration and Login.
2. Project and Goal Creation.
3. AI-Based Task Generation.
4. Task CRUD Operations.
5. Kanban Board Management.
6. Drag-and-Drop Task Movement.
7. Productivity Analytics.
8. AI-Generated Task Summaries.
9. Secure Data Storage.

### 2.3 User Classes

**Registered User**

A registered user can create projects, manage tasks, generate AI suggestions, and view productivity information.

**AI Assistant**

The AI integration processes user goals, generates actionable subtasks, and creates task completion summaries.

---

## 3. Functional Requirements

### 3.1 Authentication Module

**FR-01: User Registration**

The system shall allow new users to register by providing the required account information.

**FR-02: User Login**

The system shall authenticate registered users using valid credentials.

**FR-03: JWT Authentication**

The backend shall generate and validate JWT tokens for protected API access.

### 3.2 Project and Task Module

**FR-04: Create Task**

The system shall allow users to create tasks with a title, description, and status.

**FR-05: View Tasks**

The system shall allow users to retrieve all available tasks.

**FR-06: View Task by ID**

The system shall allow users to retrieve a specific task using its unique identifier.

**FR-07: Update Task**

The system shall allow users to update task information and status.

**FR-08: Delete Task**

The system shall allow users to delete an existing task.

**FR-09: Task Validation**

The system shall validate required fields and reject invalid task information.

### 3.3 AI Task Generation Module

**FR-10: Goal Input**

The system shall allow users to enter a project goal or development objective.

**FR-11: AI Task Breakdown**

The backend shall send the user-provided goal to Google Gemini API.

The AI service shall generate approximately 4–5 actionable subtasks.

**FR-12: Task Review**

The system shall display AI-generated subtasks for user review before saving them.

**FR-13: AI Error Handling**

The system shall handle AI service failures, invalid responses, and API timeouts appropriately.

### 3.4 Kanban Board Module

**FR-14: Board Columns**

The system shall provide the following workflow columns:

- To-Do
- In Progress
- Review
- Done

**FR-15: Drag and Drop**

The user shall be able to move tasks between columns using drag-and-drop functionality.

**FR-16: Status Synchronization**

Whenever a task changes its column, the updated status shall be saved in the database.

### 3.5 Analytics Module

**FR-17: Task Statistics**

The system shall calculate total, completed, pending, and in-progress tasks.

**FR-18: Progress Visualization**

The system shall display project progress using charts and graphical representations.

### 3.6 Auto-Documentation Module

**FR-19: Completion Summary**

When a task is marked as Done, the system shall initiate background processing to generate a completion summary using AI.

**FR-20: Summary Storage**

The generated summary shall be associated with the relevant task and stored in the database.

---

## 4. External Interface Requirements

### 4.1 User Interface

The frontend shall be developed using React.js and Tailwind CSS.

The interface shall provide:

- Registration and Login pages.
- Project creation interface.
- Kanban board.
- Task creation and editing interface.
- AI task generation interface.
- Analytics dashboard.

### 4.2 Software Interfaces

| Interface | Purpose |
|---|---|
| React Frontend | User interaction |
| Spring Boot REST API | Backend communication |
| MongoDB | Data storage |
| Google Gemini API | AI task generation and summaries |
| Spring Security | Authentication and authorization |

### 4.3 Communication Interface

The frontend and backend shall communicate using HTTP/HTTPS and REST APIs.

Data exchange shall use JSON format.

---

## 5. Non-Functional Requirements

### 5.1 Performance

- The application should provide responsive user interactions.
- AI processing should execute asynchronously where appropriate.
- API response times should be monitored under normal operating conditions.

### 5.2 Security

- Passwords shall be securely hashed.
- JWT authentication shall protect secured endpoints.
- API keys and sensitive credentials shall not be exposed publicly.
- Users shall only access data they are authorized to access.

### 5.3 Reliability

- The system shall handle unexpected errors gracefully.
- Database failures and external API failures shall produce controlled error responses.
- Invalid user input shall be rejected through validation.

### 5.4 Maintainability

- The backend shall follow Controller, Service, and Repository layers.
- The codebase shall use modular packages.
- Common errors shall be handled centrally.
- The code shall follow appropriate coding standards.

### 5.5 Scalability

The application architecture should support future increases in users, projects, and task processing workloads.

### 5.6 Usability

The application shall provide a clear and user-friendly interface with understandable task statuses and progress indicators.

---

## 6. Database Requirements

The application shall use MongoDB as its primary database.

The initial database design shall include the following collections:

| Collection | Purpose |
|---|---|
| users | Stores user account information |
| projects | Stores project details and goals |
| tasks | Stores task information and status |
| summaries | Stores AI-generated completion summaries |

Each collection shall use unique document identifiers.

Relationships between users, projects, tasks, and summaries shall be maintained using appropriate document references or identifiers.

---

## 7. Technical Constraints

- Java shall be used for backend development.
- Spring Boot shall provide backend services.
- React.js shall provide the frontend interface.
- MongoDB shall be used for persistent storage.
- Google Gemini API shall provide AI functionality.
- Maven shall be used for backend dependency and build management.
- Git and GitHub shall be used for version control.

---

## 8. Error Handling Requirements

The application shall handle the following situations:

| Error Condition | Expected Behavior |
|---|---|
| Empty task title | Return 400 Bad Request |
| Invalid task input | Return validation error |
| Task not found | Return 404 Not Found |
| Invalid login credentials | Return authentication error |
| Gemini API failure | Return controlled AI service error |
| Database connection failure | Return controlled server error |

---

## 9. Acceptance Criteria

The system shall be considered functionally acceptable when:

1. Users can register and authenticate.
2. Users can create, retrieve, update, and delete tasks.
3. Task validation works correctly.
4. Tasks can be moved between Kanban columns.
5. AI can generate subtasks from user goals.
6. Analytics displays correct task statistics.
7. AI completion summaries can be generated and stored.
8. Application errors are handled appropriately.
9. User data is protected from unauthorized access.

---

## 10. Future Enhancements

The following features may be introduced in future versions:

- Email notifications.
- Team collaboration.
- Sprint planning.
- Advanced AI task prioritization.
- Productivity recommendations.
- Mobile application support.
- Cloud-based monitoring.

---

**End of Document**

Document: Software Requirements Specification (SRS)  
Project: AI-Powered Kanban Planner  
Version: 1.0.0
