# Smart Task Manager Project Plan

The goal of this project is to build a premium, highly responsive **Smart Task Manager** web application using vanilla HTML, CSS, and JavaScript. The application will feature a modern, glassmorphic UI, rich interactive components, and offline storage capability.

Key focus areas include clean state management, modular component-driven JavaScript code, responsiveness across all device sizes, and highly engaging visual feedback (transitions, hover effects, dark/light themes).

---

## Key Features

1. **Interactive Dashboard**:
   - Visual statistics of task completion (total tasks, pending, completed, overdue).
   - Category breakdowns and weekly productivity trends.
   - Dynamic charts using custom SVGs or a lightweight charting library (e.g., Chart.js via CDN).

2. **Smart Task List & Kanban Board**:
   - Multiple views: Grid list, List list, and Kanban Board.
   - Task search, multi-criteria filtering (by status, priority, category, due date), and sorting.
   - Task actions: Add, edit, delete, mark complete/incomplete, set subtasks.
   - Task attributes: Priority (High, Medium, Low), Category (Work, Personal, Health, Finance, etc.), due dates, and tags.

3. **Focus & Pomodoro Timer**:
   - Built-in Pomodoro timer for focus sessions.
   - Tracks focus time per task to link time spent with tasks.
   - Sound notifications and visual countdown.

4. **Category & Tag Management**:
   - Custom category creation with color coding.
   - Tag system for fine-grained organization.

5. **Local Storage Persistence**:
   - Automatically saves all tasks, categories, timer history, and configurations local to the browser.
   - Export/Import data backup capability.

6. **Premium Responsive Design**:
   - Dark and Light modes.
   - Smooth transition animations (adding/removing tasks, modal slide-ins, tab changes).
   - Interactive glassmorphic styling, curated HSL color systems, and modern typography (Google Fonts).

---

## Folder Structure

We will organize the project in a clean, modular structure:

```text
Smart Task Manager/
├── index.html                   # Entry point and HTML structure
├── src/
│   ├── css/
│   │   └── styles.css           # Core styling, variables, layout, and theme tokens
│   ├── js/
│   │   ├── app.js               # App initiator, routing, and event handling coordinator
│   │   ├── store.js             # Data layer: State management, CRUD, LocalStorage persistence
│   │   ├── ui.js                # UI rendering engine: Lists, board, modals, and dynamic components
│   │   ├── timer.js             # Pomodoro logic, countdown, state, and tracking
│   │   └── analytics.js         # Math and processing for productivity charts and metrics
│   └── assets/
│       └── (custom SVG icons / generated assets)
```

---

## User Review Required

> [!IMPORTANT]
> Please review the following key architectural decisions before we begin implementation:
>
> 1. **Visual Style**: The default design uses a premium, modern dark mode with glassmorphic cards and dynamic accent glows. Let us know if you prefer a light-first theme or a different aesthetic choice.
> 2. **Charts Library**: We plan to load `Chart.js` via CDN for smooth, interactive productivity charts. If you prefer a zero-dependency approach, we can design custom responsive SVG charts instead.
> 3. **Kanban Drag-and-Drop**: We will implement native HTML5 Drag and Drop for moving tasks between Kanban columns. This keeps dependencies light and performant.

---

## Open Questions

> [!NOTE]
> 1. Do you want to support task priority calculations (e.g., an automatic "smart priority score" based on proximity to due date and selected priority)?
> 2. Do you have any specific subtask features in mind (e.g., a progress bar showing the percentage of subtasks completed)?

---

## Proposed Changes

We will create the following files in the project workspace [Smart Task Manager](file:///E:/3rd%20YEAR/6th%20SEMESTER/XEBIA/Smart%20Task%20Manager):

### Core Application

#### [NEW] [index.html](file:///E:/3rd%20YEAR/6th%20SEMESTER/XEBIA/Smart%20Task%20Manager/index.html)
- Main HTML structure.
- Sidebar for navigation (Dashboard, Tasks, Board, Timer, Analytics, Settings).
- Main viewport areas for each section (SPA feel, hidden/shown via tab state).
- Modals for Task Creation/Editing.
- CDN integrations for fonts (Outfit/Inter) and Chart.js.

#### [NEW] [styles.css](file:///E:/3rd%20YEAR/6th%20SEMESTER/XEBIA/Smart%20Task%20Manager/src/css/styles.css)
- Core design token variables (colors, shadows, spacing, glassmorphism filters, animations).
- Theme toggles (`[data-theme="dark"]` vs default light/dark preference).
- Sidebar, Grid layout, Flexbox list structures, and responsive layouts down to mobile sizes.
- Custom stylized scrollbars, inputs, buttons, and animations (e.g., fade-in, scale-in, slide-over).

#### [NEW] [app.js](file:///E:/3rd%20YEAR/6th%20SEMESTER/XEBIA/Smart%20Task%20Manager/src/js/app.js)
- Global routing and navigation logic.
- Main DOM listeners (modal openers, theme togglers, view switchers).
- Syncing state between components.

#### [NEW] [store.js](file:///E:/3rd%20YEAR/6th%20SEMESTER/XEBIA/Smart%20Task%20Manager/src/js/store.js)
- Class or module representing the Task Store.
- State: `tasks`, `categories`, `timerHistory`, `settings`.
- Methods: CRUD tasks, add category, fetch/save to LocalStorage, import/export JSON backup.

#### [NEW] [ui.js](file:///E:/3rd%20YEAR/6th%20SEMESTER/XEBIA/Smart%20Task%20Manager/src/js/ui.js)
- View renderers: Tasks grid/list rendering, Kanban board columns rendering, category select dropdowns, search/filter handlers.
- Dynamic task completion updates and subtask checkboxes.

#### [NEW] [timer.js](file:///E:/3rd%20YEAR/6th%20SEMESTER/XEBIA/Smart%20Task%20Manager/src/js/timer.js)
- Timer controller: start, pause, reset, switch mode (Pomodoro, Short Break, Long Break).
- Integrates with the selected task to record focus duration.

#### [NEW] [analytics.js](file:///E:/3rd%20YEAR/6th%20SEMESTER/XEBIA/Smart%20Task%20Manager/src/js/analytics.js)
- Dashboard overview card computation.
- Feeds data to Chart.js charts (completion rates, workload by category, productivity trends).

---

## Development Roadmap & Execution Phases

### Phase 1: Foundation & Design Tokens
- Set up project files.
- Build the core design system in `styles.css`.
- Develop layout skeleton in `index.html` (sidebar and view containers).

### Phase 2: Data Store & Basic CRUD
- Create `store.js` with robust state handling and LocalStorage triggers.
- Build HTML modals for task creation/editing.
- Implement basic task list rendering in `ui.js` and wire action buttons (create, edit, delete, complete).

### Phase 3: Advanced Views (Kanban & Board)
- Develop Kanban board structure.
- Implement HTML5 drag-and-drop to update task status in real time.
- Implement filters, search, and sorting systems.

### Phase 4: Focus Timer & Custom Analytics
- Build the Pomodoro timer layout and count-down engine.
- Wire timer tracking to active tasks.
- Implement dashboard analytics cards and charts (productivity trends and workload distributions).

### Phase 5: Polishing & Validation
- Add micro-animations, hover states, and toast notifications.
- Optimize layouts for mobile, tablet, and desktop viewports.
- Run edge-case validation tests (e.g., past due dates, empty lists, large datasets, data export/import).

---

## Verification Plan

### Automated Tests
- Since this is a vanilla JS application, we will verify core JavaScript utility functions by outputting unit checks to the developer console or utilizing a lightweight testing script.

### Manual Verification
- **Functional Checks**: Verify adding, updating, deleting, drag-dropping tasks, setting focus timers, and checking dashboard metrics.
- **Persistence Checks**: Refresh the page to verify data remains intact; try export and import functionality.
- **Cross-device Checks**: Resize viewport to inspect sidebar responsive collapses and kanban wrapping.
- **Themes Check**: Toggle between dark and light mode, verifying text contrast, colors, and shadows are readable and match aesthetic standards.
