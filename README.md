# Frontend React Project Standardization

## Table of Contents

1. [Introduction](#introduction)
2. [Project Setup](#project-setup)
   - [Tooling](#tooling)
   - [Dependencies](#dependencies)
   - [Folder Structure](#folder-structure)
3. [Code Style & Conventions](#code-style--conventions)
   - [JSX and React Components](#jsx-and-react-components)
   - [State Management](#state-management)
   - [Component Design](#component-design)
   - [Naming Conventions](#naming-conventions)
4. [License](#license)

---

## Introduction

This document defines the standard guidelines and best practices for React frontend projects. The goal is to maintain consistency, scalability, and maintainability across all development efforts. This standardization ensures high-quality code, a well-organized structure, and seamless collaboration among team members.

---

## Project Setup

### Tooling

1. **Husky**

   - Configure pre-commit and pre-push hooks to enforce linting, testing, and formatting standards.
   - Example setup:
     ```bash
     npx husky-init && npm install
     ```
   - Use `lint-staged` to lint only staged files during commits.

2. **ESLint**

   - Enforce consistent code style and detect errors.
   - Extend from an existing ESLint configuration.
   - Integrate ESLint with Husky pre-commit hooks.

3. **Prettier**
   - Automatically format code for consistency.
   - Integrate Prettier with ESLint to avoid conflicts.

---

### Dependencies

- **React**: Use version 18.x or the latest stable release.
- **Redux Toolkit**: Preferred for state management. Avoid directly using Redux without the Toolkit.
- **React Router DOM**: For handling navigation.
- Install additional dependencies like Axios or React Query based on project requirements.

---

### Folder Structure

### Running the Project

You can run the project using one of the following methods:

1. **Using npm**  
   Run the development server locally with the following command:

   ```bash
   npm run dev
   ```

   Ensure all dependencies are installed beforehand with:

   ```bash
   npm install
   ```

2. **Using Docker**  
   Build and run the project using Docker:
   ```bash
   docker build -t react-frontend .
   docker run -p 3000:3000 react-frontend
   ```
   Replace `react-frontend` with your desired image name.

#### **Absolute Imports**

- Configure `jsconfig.json` or `tsconfig.json` for absolute imports to avoid relative path hell.

#### **Modular Approach**

- Each feature or section lives in its own folder for better organization.
- Example folder structure:
  ```
  src/
  ├── modules/
  │   └── FeatureName/
  │       ├── partials/ (shared components)
  │       ├── router/ (module-based routing)
  │       ├── utils/ (utilities for the module)
  │       ├── views/ (module-specific pages)
  │       └── tests/ (optional)
  ├── services/ (feature-specific actions, reducers, slices)
  ```

---

## Code Style & Conventions

### JSX and React Components

- Use **functional components** and hooks; avoid class components.
- Destructure props and state for cleaner code.
- Use `useEffect` with proper dependency arrays for side effects.
- Use **PropTypes** or **TypeScript** for type-checking.
- Ensure all rendered lists have a unique `key` prop.

---

### State Management

- Use **Redux Toolkit** for application-level state management.
- Organize state using `createSlice` for modular and maintainable state logic.

---

### Component Design

- Keep components **small, reusable, and single-purpose**.
- Separate presentation and logic:
  - **Presentational Components**: Handle UI rendering.
  - **Container Components**: Handle logic and state.

---

### Naming Conventions

#### File and Folder Names

- **Components**: Use PascalCase.  
  Example: `MyComponent.tsx`
- **Utilities/Helpers**: Use camelCase.  
  Example: `apiService.ts`
- **Tests**: Use PascalCase with `.test.js` or `.spec.js` suffix.  
  Example: `MyComponent.test.js`

#### Variables and Functions

- Use camelCase: `handleClick`, `fetchData`.
- Event handlers: Prefix with "handle" or "on".  
  Example: `handleSubmit()`, `onClick()`.

#### Constants

- Use UPPERCASE with underscores: `MAX_COUNT`, `DEFAULT_THEME`.

#### Environment Variables

- UPPERCASE with underscores: `REACT_APP_API_URL`.

#### React Components

- Use PascalCase for component names.  
  Example: `Header.ts`, `UserProfile.ts`.

#### Props

- Use camelCase for props.  
  Example: `<MyComponent userName="John" onClick={handleClick} />`.
- Event handlers: Prefix with "on".  
  Example: `<MyComponent onSubmit={handleSubmit} />`.

#### CSS Class Names

- Use kebab-case for traditional CSS: `.button-primary`.
- For CSS Modules, use camelCase or PascalCase depending on context: `styles.buttonPrimary`.

#### Hooks

- Prefix with "use": `useAuth`, `useFetchData`.

#### Context

- Use PascalCase: `UserContext`, `ThemeContext`.

#### General Guidelines

- Avoid abbreviations unless widely recognized (e.g., `Button` instead of `Btn`).
- Boolean variables: Use prefixes like `is`, `has`, or `can`.  
  Example: `isActive`, `hasPermission`.

---

## License

This project is licensed under the [MIT License](LICENSE).

---
