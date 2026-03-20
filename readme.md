# Welcome to React Router!

A modern, production-ready template for building full-stack React applications using React Router.

[![Open in StackBlitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github/remix-run/react-router-templates/tree/main/default)

## Features

- 🚀 Server-side rendering
- ⚡️ Hot Module Replacement (HMR)
- 📦 Asset bundling and optimization
- 🔄 Data loading and mutations
- 🔒 TypeScript by default
- 🎉 TailwindCSS for styling
- 📖 [React Router docs](https://reactrouter.com/)

## Getting Started

### Installation

Install the dependencies:

```bash
npm install
```

### Development

Start the development server with HMR:

```bash
npm run dev
```

Your application will be available at `http://localhost:5173`.

## Building for Production

Create a production build:

```bash
npm run build
```

## Deployment

### Docker Deployment

To build and run using Docker:

```bash
docker build -t my-app .

# Run the container
docker run -p 3000:3000 my-app
```

The containerized application can be deployed to any platform that supports Docker, including:

- AWS ECS
- Google Cloud Run
- Azure Container Apps
- Digital Ocean App Platform
- Fly.io
- Railway

### DIY Deployment

If you're familiar with deploying Node applications, the built-in app server is production-ready.

Make sure to deploy the output of `npm run build`

```
├── package.json
├── package-lock.json (or pnpm-lock.yaml, or bun.lockb)
├── build/
│   ├── client/    # Static assets
│   └── server/    # Server-side code
```

## Styling

This template comes with [Tailwind CSS](https://tailwindcss.com/) already configured for a simple default starting experience. You can use whatever CSS framework you prefer.

---

Built with ❤️ using React Router.
# 📄 Frontend Architecture Case: Notification System (SOLID)

## 🎯 Objective
Build a flexible and extensible Notification System UI for a web application. The system must support multiple notification types and delivery channels while remaining scalable and maintainable.

## 🧩 Scenario
You are building the notification layer of a SaaS admin panel. The system should be able to:
- Display notifications in the UI.
- Support different notification types.
- Allow multiple delivery strategies.
- Be easily extendable without modifying core logic.

---

## 🧠 Requirements

### 1. Notification Model
Each notification has the following structure:

type Notification = {
  id: string;
  type: string;
  title: string;
  message: string;
  createdAt: Date;
};

### 2. Notification Types
At minimum, support:
- **info**, **success**, **warning**, **error**.
- Each type should have different UI behavior (style, icon, etc.).

### 3. Notification Rendering
- Notifications should be rendered in a list.
- Each notification type may render differently.
- Rendering logic must be extensible.

### 4. Notification Source
- **Static source:** Notification[]
- **Remote source:** fetchNotifications(): Promise<Notification[]>

### 5. Actions
Each notification may support optional actions:
- **dismiss**, **retry**, **navigate**.
- Actions differ depending on notification type.

### 6. Extensibility (CRITICAL)
You must be able to do the following without modifying existing core components:
- Add a new notification type (e.g., system-alert).
- Add new action types without breaking existing ones.
- Add new data sources without changing UI logic.

### 7. State Management
You are free to choose: local state, hooks, context, or any lightweight approach.

---

## 🚫 Constraints
- **No External UI Libraries:** Do NOT use MUI, Ant Design, etc.
- **No Conditional Abuse:** Do NOT hardcode logic with large if/else or switch statements.
- **No Tight Coupling:** Do NOT tightly couple data fetching with rendering.
- **No Monolithic Components:** Break down the logic into smaller, focused pieces.

## ✅ Expected Capabilities
- Adding a new notification type seamlessly.
- Switching from static to remote data source easily.
- Attaching different behaviors to notifications dynamically.

## 🧪 Bonus (Optional)
- Queue System (max visible notifications).
- Auto-dismiss after timeout.
- Animation support.
- Grouping notifications.

---

## 🧾 Deliverables
1. Working React implementation.
2. Clean project structure.
3. Clear separation of concerns.
4. Readable and maintainable code.

## 🧠 Evaluation Criteria
- Architecture design (SOLID).
- Extensibility & Dependency management.
- Component API design.
- Ability to handle change.

**Time Expectation:** 60–90 minutes