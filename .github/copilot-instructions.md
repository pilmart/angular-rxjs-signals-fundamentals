## Copilot Instructions for angular-rxjs-signals-fundamentals

This codebase contains two Angular projects (`apm-begin` and `apm-final`) demonstrating RxJS and Angular Signals for reactive state management. Use these instructions to maximize AI agent productivity and maintain project conventions.

### Project Structure & Architecture
- **Two main projects:**
  - `apm-begin/`: Starter code for course exercises.
  - `apm-final/`: Completed reference implementation.
- **Key folders:**
  - `src/app/products/`, `src/app/cart/`, `src/app/reviews/`, `src/app/utilities/`, `src/app/home/`
  - Each feature (products, cart, reviews) is organized in its own folder, using standalone Angular components and services.
- **State management:**
  - Uses Angular Signals (`signal`, `computed`, `effect`) for local and shared state.
  - RxJS is used for async data flows, HTTP, and derived state.
  - Example: `ProductService` combines signals and RxJS to manage product selection and data retrieval.
- **Data layer:**
  - Uses `angular-in-memory-web-api` for mock HTTP endpoints (see `app-data.ts`).
  - Product and review data are static and defined in `product-data.ts` and `review-data.ts`.
- **Routing:**
  - Configured in `app.routes.ts` using Angular standalone routing APIs.
  - Lazy loading via `loadComponent` for feature modules.

### Developer Workflows
- **Install dependencies:**
  - Run `npm install` in either `apm-begin` or `apm-final`.
- **Start dev server:**
  - `npm start` or `ng serve` (default port: 4200).
- **Build:**
  - `npm run build` or `ng build`.
- **Test:**
  - `npm test` or `ng test` (runs Karma/Jasmine unit tests).
- **VS Code tasks:**
  - Predefined in `.vscode/tasks.json` for `start` and `test`.
- **Debugging:**
  - Use `.vscode/launch.json` for Chrome-based debugging (`ng serve` and `ng test`).

### Project-Specific Conventions
- **Standalone components:**
  - All Angular components, directives, and pipes are created as standalone (see `angular.json` schematics).
- **Signals and RxJS:**
  - Prefer signals for state; use RxJS for async and derived state.
  - Example: `CartService` uses signals for cart state and computed properties for totals.
- **Error handling:**
  - Centralized in `http-error.service.ts`.
- **Styling:**
  - Uses Bootstrap 5 (imported in `styles.css`).
- **Mock backend:**
  - All HTTP requests are handled by the in-memory API; no real backend.

### Integration & Cross-Component Patterns
- **Services:**
  - Provided in root; injected using Angular's `inject()` API.
  - Cross-feature communication via service signals (e.g., cart count in `AppComponent`).
- **Data flow:**
  - Product selection and cart updates propagate via signals and service methods.
- **Testing:**
  - Unit tests are colocated with source files and use Jasmine/Karma.

### References
- See `README.md` in each project for CLI usage.
- For RxJS/Signals patterns, review `ProductService`, `CartService`, and their usage in components.
- For routing and lazy loading, see `app.routes.ts`.

---
**When adding new features:**
- Place new features in their own folder under `src/app/`.
- Use standalone components and signals for state.
- Update routing in `app.routes.ts` as needed.