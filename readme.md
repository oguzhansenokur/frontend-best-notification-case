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

