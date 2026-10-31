# Customer Requirements Specification (CRS)

## AI-Powered Kanban Planner (Smart Kanban)

| Document Information | Details |
|---|---|
| Project Name | AI-Powered Kanban Planner |
| Project Version | 1.0.0 |
| Document Type | Customer Requirements Specification |
| Document Version | 1.0 |
| Status | Draft |
| Backend Technology | Java, Spring Boot |
| Frontend Technology | React.js, Tailwind CSS |
| Database | MongoDB |
| AI Integration | Google Gemini API |

---

## 1. Project Overview

### 1.1 Purpose

The purpose of the AI-Powered Kanban Planner is to develop an intelligent task management system that simplifies project planning, task organization, and productivity tracking.

Traditional Kanban systems require users to manually create and organize individual tasks. This process can be time-consuming, especially when managing complex projects.

The proposed system integrates Google Gemini AI with a Kanban board to automatically break down user-defined goals into smaller, actionable tasks.

The application will provide task management, drag-and-drop functionality, productivity analytics, and AI-powered documentation.

### 1.2 Project Objectives

The primary objectives are:

- Automate task creation using Artificial Intelligence.
- Simplify project and task management.
- Provide a visual Kanban board for tracking work.
- Improve productivity through analytics and progress tracking.
- Generate task completion summaries using AI.
- Provide secure user authentication and data management.

## 2. User Roles

The system will primarily support the following roles:

### 2.1 Project Manager / Developer

The user will be able to:

- Register and log in securely.
- Create and manage project goals.
- Generate tasks using AI.
- View and manage tasks on the Kanban board.
- Move tasks between different workflow stages.
- View project progress and productivity analytics.
- Access AI-generated task summaries.

### 2.2 AI Assistant

The AI Assistant will:

- Understand user-defined project goals.
- Generate smaller, actionable subtasks.
- Suggest an appropriate task breakdown.
- Generate completion summaries when tasks are marked as Done.

## 3. Functional Requirements

### 3.1 User Interface and Kanban Board

**FR-01: Visual Kanban Board**

The system shall provide a Kanban board containing four workflow columns:

- To-Do
- In Progress
- Review
- Done

**FR-02: Drag and Drop**

The user shall be able to move tasks between workflow columns using drag-and-drop functionality.

The application will use the `@hello-pangea/dnd` library.

**FR-03: Task Management**

The user shall be able to create, view, update, and delete tasks.

Each task shall contain relevant information such as title, description, status, and creation date.

**FR-04: Analytics Dashboard**

The system shall display project productivity information, including:

- Total tasks.
- Completed tasks.
- Pending tasks.
- Tasks currently in progress.
- Overall project completion percentage.

The application will use Recharts to display charts and graphs.

### 3.2 AI Integration Module

**FR-05: AI Task Breakdown**

The user shall be able to enter a project goal or task description.

Example:

"Build a secure login page with JWT authentication."

The system shall communicate with the Google Gemini API and generate approximately 4–5 smaller, actionable subtasks.

**FR-06: AI-Generated Task Suggestions**

The system shall present AI-generated tasks to the user for review before adding them to the Kanban board.

**FR-07: Automatic Documentation**

When a task is marked as Done, the system shall generate a short AI-powered completion summary in the background.

### 3.3 Backend and Security

**FR-08: User Authentication**

The system shall provide secure registration and login functionality using Spring Security and JWT authentication.

**FR-09: Asynchronous Processing**

The system shall use Java asynchronous processing through Spring's `@Async` functionality for suitable background operations, such as AI task generation and completion summaries.

**FR-10: Database Management**

The system shall store and manage user, project, board, and task information using MongoDB.

**FR-11: REST API**

The backend shall expose RESTful APIs to support communication between the React frontend and Spring Boot backend.

## 4. Non-Functional Requirements

### 4.1 Performance

- The application should provide responsive user interactions.
- AI task generation should return results within a reasonable target time under normal network and API conditions.
- Background processing should prevent long-running AI operations from blocking normal application interactions.

### 4.2 Security

- User authentication shall be implemented using JWT.
- Protected APIs shall require valid authentication.
- Sensitive configuration values, including API keys, shall not be exposed in frontend code or public repositories.

### 4.3 Maintainability

- The backend shall follow a layered architecture using Controller, Service, and Repository packages.
- Code should follow SOLID principles where applicable.
- The frontend and backend should maintain clear separation of responsibilities.

### 4.4 Scalability

- The system should support multiple users and their independent projects.
- The architecture should allow future enhancements and increased application workload.

### 4.5 Usability

- The user interface should be simple and intuitive.
- Users should be able to manage tasks with minimal effort.
- Task status and project progress should be clearly visible.

## 5. Technology Stack

| Component | Technology |
|---|---|
| Frontend | React.js |
| UI Styling | Tailwind CSS |
| Backend | Java + Spring Boot |
| Database | MongoDB |
| AI Integration | Google Gemini API |
| Authentication | Spring Security + JWT |
| Drag and Drop | @hello-pangea/dnd |
| Charts | Recharts |
| Build Tool | Maven |
| API Testing | Postman |
| Unit Testing | JUnit 5 + Mockito |
| Version Control | Git + GitHub |

## 6. Project Scope

### 6.1 In Scope

The initial version of the application will include:

- User registration and authentication.
- Project goal management.
- AI-powered task breakdown.
- Kanban board with four workflow stages.
- Drag-and-drop task movement.
- Task CRUD operations.
- Productivity analytics.
- AI-generated completion summaries.
- MongoDB data storage.

### 6.2 Out of Scope

The following features are not included in the initial release but may be considered for future versions:

- Real-time team collaboration.
- Advanced role-based enterprise permissions.
- Third-party project management integrations.
- Mobile application.
- Advanced predictive analytics.

## 7. Assumptions and Dependencies

- Users will have an active internet connection.
- Google Gemini API access will be available.
- MongoDB will be configured and accessible.
- The application will be accessed through a supported web browser.
- AI-generated outputs may vary depending on API availability and model responses.

## 8. Acceptance Criteria

The initial application will be considered acceptable when:

1. Users can register and log in securely.
2. Users can create, view, update, and delete tasks.
3. Users can manage tasks across all four Kanban columns.
4. Users can move tasks using drag-and-drop.
5. The AI integration can generate actionable subtasks from a project goal.
6. The analytics dashboard displays task and project progress.
7. The system can generate task completion summaries.
8. User and task data are stored and retrieved successfully from MongoDB.
9. Invalid inputs and application errors are handled appropriately.

## 9. Future Enhancements

Possible future improvements include:

- Email and push notifications.
- Team collaboration.
- Sprint planning and management.
- Advanced productivity reports.
- AI-based task prioritization.
- Cloud deployment and monitoring.

---

**End of Document**

Document: Customer Requirements Specification (CRS)  
Project: AI-Powered Kanban Planner  
Version: 1.0.0
