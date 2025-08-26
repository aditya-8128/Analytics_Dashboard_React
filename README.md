# React Analytics Dashboard

A responsive **React Admin/Analytics Dashboard** with dark/light themes, interactive data tables, validated forms, calendar scheduling, and rich charts. The project is adapted and customized with original assets and styling for analytics use cases.

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Run (Development)](#run-development)
  - [Build (Production)](#build-production)
  - [Lint and Tests (optional)](#lint-and-tests-optional)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Tables (MUI Data Grid)](#tables-mui-data-grid)
- [Charts (Nivo)](#charts-nivo)
- [Calendar (FullCalendar)](#calendar-fullcalendar)
- [Forms (Formik--yup)](#forms-formik--yup)
- [Scripts (packagejson)](#scripts-packagejson)
- [Deployment](#deployment)
- [Screenshots](#screenshots)
- [Roadmap](#roadmap)
- [Credits](#credits)
- [License](#license)

---

## Features

- **Theme system** with light/dark mode toggle, shared color tokens, and consistent typography.
- **Data tables** (MUI Data Grid) with sorting, filtering, column show/hide, density control, row selection, pagination, and CSV export.
- **Charts** (Bar, Line, Pie, Geography) implemented with Nivo and tuned for responsiveness.
- **Calendar** with FullCalendar supporting add/drag/delete events and day/week/list views.
- **Forms** built with Formik + Yup for schema‑based, real‑time validation.
- **App shell** with Sidebar navigation, Topbar actions/search, and route‑based pages.

---

## Tech Stack

- **React 18**, **React Router**
- **Material UI (MUI)** + **MUI X Data Grid**
- **Nivo Charts**
- **FullCalendar**
- **Formik + Yup**
- **Vite** or **CRA** build tooling (adjust commands below to match the repo scripts)

---

## Getting Started

### Prerequisites

- **Node.js** (LTS recommended) and **npm** installed
- **Git** installed to clone the repository

Check versions:

```bash
node -v
npm -v
```

### Installation

```bash
# Clone
git clone https://github.com/aditya-8128/React_Analytics_Dashboard.git
cd React_Analytics_Dashboard/Analytics_Dashboard-main

# Install dependencies
npm install
```

### Run (Development)

```bash
npm start
```

Then open: `http://localhost:3000`

The dev server supports **hot reload**. Save a file and the page updates.

### Build (Production)

```bash
npm run build
```

This produces an optimized build in the `build/` (or `dist/`) directory, suitable for static hosting (Netlify, Vercel, GitHub Pages, etc.).

### Lint and Tests (optional)

If configured in `package.json`:

```bash
npm run lint
npm test
```

---

## Project Structure

```text
src/
  assets/                 # Images/icons customized for this fork
  components/             # Reusable UI (charts wrappers, cards, etc.)
  data/                   # Mock datasets and geo features for charts/tables
  scenes/
    global/               # App shell: Sidebar, Topbar
    dashboard/            # Main dashboard page
    tables/               # Users / Contacts / Invoices tables
    forms/                # Formik + Yup forms
    calendar/             # FullCalendar page
    faq/                  # FAQ with accordions
    charts/               # Bar / Line / Pie / Geography pages
  theme/                  # MUI theme tokens & color-mode context
  App.jsx
  main.jsx or index.jsx
```

> **Notes**
>
> - “**scenes**” are page‑level features organized by route.  
> - “**global**” contains layout components shared across pages.  
> - “**theme**” exports the color tokens, MUI theme settings, and a color‑mode toggle via context.

---

## Configuration

- **Theme:** Edit values in `src/theme` to customize palette tokens, typography, and component defaults.
- **Routes:** Update routes in `App.jsx` (or router file) to add/remove pages.
- **Data:** Replace mock data in `src/data` with API calls or real datasets.
- **Assets:** Place custom images in `src/assets` and reference them in components.

---

## Tables (MUI Data Grid)

**Key behaviors included:**

- Sorting by column headers
- Column visibility toggle (toolbar)
- Quick filter / search
- Density selector (compact/comfortable)
- Row selection with checkboxes
- Pagination
- CSV export

**To adjust:**

- Update column definitions and row data in the corresponding table scene.
- Enable or remove `GridToolbar` for filtering/columns/export UI.
- Tune pagination and page size options as needed.

---

## Charts (Nivo)

**Provided chart pages:** Bar, Line, Pie, and Geography (choropleth) charts with responsive containers, custom themes, legends, and tooltips.

**To adjust:**

- Swap datasets via props
- Edit color scales, legends, axes, and tooltip renderers
- Geography chart requires a geo features file (already included under `src/data`)

---

## Calendar (FullCalendar)

- Add new events via input handlers
- Drag to move, click to delete, and switch views (day/week/list)

**To adjust:** configure plugins, initial events, and event handlers in the calendar scene.

---

## Forms (Formik + Yup)

- Client-side schema validation (required fields, email pattern, number ranges)
- On submit, gather values for API submission or local processing

**To adjust:**

- Update Yup schema for field rules
- Add/remove fields in the Formik form component

---

## Scripts (package.json)

Common scripts (actual names may vary by your repo):

```json
{
  "scripts": {
    "start": "react-scripts start or vite",
    "build": "react-scripts build or vite build",
    "test": "react-scripts test or vitest",
    "lint": "eslint ."
  }
}
```

---

## Deployment

- **Static Hosts:** Upload the production build directory (`build/` or `dist/`) to Netlify, Vercel, or GitHub Pages.
- **SPA Routing:** On Netlify/Vercel, enable **SPA fallback** so client‑side routing works on refresh.
  - **Netlify**: Create a `_redirects` file in the build output with:
    ```
    /*    /index.html   200
    ```
  - **Vercel**: Use `rewrites` in `vercel.json`:
    ```json
    {
      "rewrites": [{ "source": "/(.*)", "destination": "/" }]
    }
    ```

---

## Screenshots

Add a few images or GIFs here (dashboard, tables, charts, calendar) to help reviewers quickly understand the UI.

---

## Roadmap

- Optional: hook tables and charts to a real API
- Add authentication and role-based access control
- Persist calendar events to a backend
- Add E2E tests (Playwright/Cypress) and CI workflow

---

## Credits

Based on an admin dashboard tutorial with subsequent customizations (images, styling, data, and features).

**Libraries:** Material UI, MUI X Data Grid, Nivo, FullCalendar, Formik, Yup.

---

## License

This project uses open‑source libraries under their respective licenses. Review licensing if upgrading to any Pro/Premium components.
