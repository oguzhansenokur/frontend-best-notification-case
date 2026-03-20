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


#TASK
📄 README — Frontend Architecture Case (SOLID)
🎯 Objective

Build a flexible and extensible Notification System UI for a web application.

The system must support multiple notification types and delivery channels while remaining scalable and maintainable.

🧩 Scenario

You are building the notification layer of a SaaS admin panel.

The system should be able to:

Display notifications in the UI

Support different notification types

Allow multiple delivery strategies

Be easily extendable without modifying core logic

🧠 Requirements
1. Notification Model

Each notification has:

type Notification = {
  id: string;
  type: string;
  title: string;
  message: string;
  createdAt: Date;
};
2. Notification Types

At minimum, support:

info

success

warning

error

Each type should have different UI behavior (style, icon, etc.)

3. Notification Rendering

Notifications should be rendered in a list

Each notification type may render differently

Rendering logic must be extensible

4. Notification Source

Notifications can come from:

A) Static source
Notification[]
B) Remote source
fetchNotifications(): Promise<Notification[]>
5. Actions

Each notification may support optional actions:

dismiss

retry

navigate

Actions differ depending on notification type

6. Extensibility (CRITICAL)

You must be able to:

Add a new notification type without modifying existing core components

Add new action types without breaking existing ones

Add new data sources without changing UI logic

7. State Management

You are free to choose:

local state

hooks

context

any lightweight approach

🚫 Constraints

Do NOT use external UI libraries (no MUI, Ant, etc.)

Do NOT hardcode logic with large conditionals (if/else or switch abuse)

Do NOT tightly couple data fetching with rendering

Do NOT create a monolithic component

✅ Expected Capabilities

Your implementation should allow scenarios like:

adding a new notification type (e.g. system-alert)

switching from static to remote data source

attaching different behaviors to notifications dynamically

🧪 Bonus (Optional)

queue system (max visible notifications)

auto-dismiss after timeout

animation support

grouping notifications

🧾 Deliverables

Working React implementation

Clean project structure

Clear separation of concerns

Readable and maintainable code

🧠 Evaluation Criteria

You will be evaluated on:

architecture design

extensibility

dependency management

component API design

separation of concerns

ability to handle change

⏱️ Time Expectation

60–90 minutes

📌 Notes

Focus on design decisions, not visual perfection.

Bitti.