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
