# Resume Tracker Pro

Course project for **Team 7** at Harrisburg University, **ISEM 564**.

Resume Tracker Pro is a full stack application for collecting job listings from RSS feeds, ranking them with configurable rules, and tracking each role through your pipeline. The goal is a calm, focused workflow that stays out of your way.

## System architecture

**Backend**

* **Language:** Python three point twelve
* **Framework:** FastAPI
* **Persistence:** SQLAlchemy with SQLite
* **Location:** `backend` directory at repository root

**Frontend**

* **Runtime:** React 18 with Vite
* **Styling:** Tailwind CSS version four
* **Icons:** Lucide React
* **Routing:** React Router
* **Location:** `frontend` directory at repository root

## Repository layout

```
ResumeTracker_ISEM564/
├── backend/          API, models, database, services
├── frontend/         Vite React application
├── .gitignore        Ignores venv, node_modules, databases, caches
└── README.md         This file
```

## Backend onboarding

These steps assume a terminal on macOS or Linux. Adjust paths if you use Windows PowerShell.

1. **Open a terminal** and move into the backend folder:

   ```bash
   cd backend
   ```

2. **Create a virtual environment** (recommended name `venv`):

   ```bash
   python3.12 -m venv venv
   ```

   If `python3.12` is not on your PATH, install Python three point twelve from python.org or your package manager, then run the command again.

3. **Activate the environment**

   * macOS and Linux:

     ```bash
     source venv/bin/activate
     ```

   * Windows (Command Prompt):

     ```bat
     venv\Scripts\activate.bat
     ```

4. **Install Python dependencies**

   If the project includes a `requirements.txt` file in `backend`, run:

   ```bash
   pip install -r requirements.txt
   ```

   If that file is not present yet, install the core stack directly:

   ```bash
   pip install fastapi uvicorn sqlalchemy pydantic email-validator feedparser
   ```

5. **Run the API** from the `backend` folder with the virtual environment active:

   ```bash
   uvicorn main:app --reload
   ```

   The default development URL is `http://127.0.0.1:8000`. Open `/docs` in a browser for the interactive OpenAPI documentation.

6. **Database**

   SQLite data is stored as `jobs.db` in the backend working directory when you use the default configuration. This file is ignored by Git when listed in the root `.gitignore`.

## Frontend onboarding

1. **Install Node.js** (LTS recommended). Confirm versions:

   ```bash
   node -v
   npm -v
   ```

2. **Move into the frontend folder** at repository root:

   ```bash
   cd frontend
   ```

3. **Install packages**

   ```bash
   npm install
   ```

4. **Start the development server**

   ```bash
   npm run dev
   ```

   Vite prints a local URL (commonly `http://localhost:5173`). Open that address in your browser.

5. **Production build** (optional)

   ```bash
   npm run build
   npm run preview
   ```

## Design standard for UI work

All interface development must follow the **Simplify** minimalist direction.

**Rules**

* Prefer a white or near white canvas, restrained typography, and generous spacing.
* Use **Tailwind CSS version four** utility classes for layout, color, and motion. Avoid large bespoke CSS files unless a pattern truly cannot be expressed with utilities.
* Reach for Lucide icons at small and medium sizes; keep icon color muted so content stays primary.
* Favor clarity over decoration. One primary action per view when possible.

This standard applies to new pages, dashboards, forms, and any future marketing or onboarding surfaces inside the app.

## Contributing and course notes

* Keep commits small and descriptive.
* Run the backend and frontend together when testing integration (for example RSS fetch and job listing).
* Do not commit `venv`, `node_modules`, local `.db` files, or `.DS_Store`; the root `.gitignore` is configured for those paths.

## License and attribution

This repository is maintained for academic use in ISEM 564. Add a license file at the root if you distribute the project beyond the course context.
