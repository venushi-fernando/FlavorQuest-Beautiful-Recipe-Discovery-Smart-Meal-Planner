# Agile Methodology & Project Analysis

This document outlines the Agile workflow, sprint structure, and methodology rationale for the **FlavorQuest** project, an intelligent recipe manager and meal planner built with Next.js and Python.

## 1. Methodology Rationale: Agile vs. Waterfall

For the development of FlavorQuest, our team has selected an **Agile Methodology** rather than a traditional Waterfall approach. Because we are developing a full-stack application that includes integrating an AI Chatbot and a live admin dashboard, we require a highly adaptable workflow.

### 1.1 Why Agile?
*   **Iterative Delivery:** Unlike Waterfall, where testing and deployment happen at the very end of the project, Agile allows us to deliver functional components (like the core SQLite database and UI) at the end of Sprint 1. 
*   **Adaptability:** Following our lecturer's feedback, we pivoted from a PyInstaller desktop app to a live-deployed web application (Vercel/Render). Agile easily accommodated this shift in requirements mid-project.
*   **Continuous Feedback & Cultural Alignment:** Agile sprint reviews allow us to continuously evaluate our progress against the technical requirements and the cultural considerations outlined in our kickoff meeting (specifically ensuring alignment with the *Te Tiriti o Waitangi* principles of Partnership, Participation, and Protection).

---

## 2. Process Diagram
*Click on the diagram below to open it live in the Draw.io editor.*

[![Agile Diagram](./agile-workflow.drawio.svg)](https://app.diagrams.net/#Hvenushi-fernando/FlavorQuest-Beautiful-Recipe-Discovery-Smart-Meal-Planner/main/docs/agile-workflow.drawio.svg)

---

## 3. Sprint Planning & Deliverables

Our development cycle is divided into three focused sprints to ensure steady progress and high-quality code.

### Sprint 1: Core Foundation (Week 1)
**Objective:** Establish the development environment, database schema, and initial UI.
*   **Tasks:**
    * Initialize the shared GitHub repository with separate `frontend/` (Next.js/Tailwind) and `backend/` (Python) directories.
    * Design and implement the SQLite database schema (Recipes, Plans, Ratings).
    * Implement basic CRUD (Create, Read, Update, Delete) API routes for recipe management.
*   **Deliverable:** A functional local environment where recipe data can be stored and retrieved.

### Sprint 2: Feature Expansion & Analytics (Week 2)
**Objective:** Build the core user features and integrate the Admin dashboard.
*   **Tasks:**
    * Integrate the static Kaggle dataset to populate the recipe database.
    * Develop the Admin Data Analysis Dashboard using `Chart.js` to visualize user and recipe metrics.
    * Build the interactive drag-and-drop weekly meal calendar interface.
*   **Deliverable:** A fully functional recipe management system with visual analytics.

### Sprint 3: Smart Tools & Live Deployment (Weeks 3-4)
**Objective:** Finalize intelligent features, conduct user testing, and push to production.
*   **Tasks:**
    * Integrate the AI "Sous-Chef" Chatbot for intelligent recipe suggestions and "fridge search" functionality.
    * Build the algorithm to consolidate meal plan ingredients into an automated shopping list.
    * Perform acceptance testing against user stories.
    * Deploy the Next.js frontend to **Vercel** and the Python API to **Render**.
*   **Deliverable:** The final, live web application ready for client and lecturer presentation.

---

## 4. Collaborative Workflow & Tools
To ensure professional, culturally informed teamwork as required by the MSE800 assessment:
*   **Version Control:** We utilize this shared GitHub repository. No code is pushed directly to the `main` branch. All features are developed on separate branches and merged via Pull Requests.
*   **Communication:** We conduct daily 15-minute stand-ups via Microsoft Teams to discuss task allocation and blockers.
*   **Task Management:** User stories and sprint backlogs are managed collaboratively, ensuring labor and resources are distributed equitably.

# FlavorQuest: Software Verification Specifications

Below is the list of project specifications and their one-line descriptions for software verification.

## 1. Functional Specifications
* **FS-01 Recipe Dataset Integration:** The system must read and load recipe data from the designated static CSV dataset into the SQLite database.
* **FS-02 Recipe Search:** The system must allow users to search for recipes by name, tags, or ingredient keywords.
* **FS-03 Drag-and-Drop Meal Planner:** The system must allow users to drag a recipe card and drop it into a specific day/meal slot on the weekly calendar.
* **FS-04 Automated Shopping List:** The system must aggregate ingredients from the weekly meal plan and generate a consolidated shopping list.
* **FS-05 AI Sous-Chef Chatbot:** The system must integrate an AI chatbot endpoint that responds to user prompts regarding recipes and ingredients.
* **FS-06 Admin Dashboard:** The system must provide a protected admin route to display data visualizations (e.g., total users, popular recipes) using Chart.js.

## 2. Non-Functional Specifications
* **NFS-01 Frontend Performance:** The Next.js web application must load the recipe dashboard in under 3 seconds on a standard broadband connection.
* **NFS-02 UI Responsiveness:** The application UI must be built with Tailwind CSS and remain fully functional across desktop, tablet, and mobile breakpoints.
* **NFS-03 API Response Time:** The Python backend API must respond to standard database queries (e.g., fetching a recipe) in under 500 milliseconds.
* **NFS-04 Database Integrity:** The SQLite database must enforce foreign key constraints between the `users`, `recipes`, and `meal_plans` tables.
* **NFS-05 Cross-Origin Resource Sharing (CORS):** The backend API must explicitly allow CORS requests from the Vercel-hosted Next.js frontend domain.

## 3. Security Specifications
* **SS-01 Environment Variables:** API keys (e.g., OpenAI) and database credentials must be loaded via `.env` files and never hardcoded into the source code.
* **SS-02 Input Sanitization:** The backend must sanitize all user inputs from the frontend to prevent SQL Injection (SQLi) attacks.
* **SS-03 Admin Authorization:** The admin dashboard route must verify an authentication token before rendering sensitive data visualizations.
