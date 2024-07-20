# TicketHive - Next.js Ticketing App

## Overview

**TicketHive** is a ticketing application where users can create, update, and delete tickets. Each ticket includes various fields such as title, description, category, priority, progress, and status.

## Directory Structure

```
app/
│   ├── (components)/
│   │   ├── DeleteBlock.jsx
│   │   ├── Nav.jsx
│   │   ├── PriorityDisplay.jsx
│   │   ├── ProgressDisplay.jsx
│   │   ├── StatusDisplay.jsx
│   │   ├── TicketCard.jsx
│   │   ├── TicketForm.jsx
│   ├── (models)/
│   │   ├── Tickets.js
│   ├── api/
│   │   ├── Tickets/
│   │   │   ├── [id]/
│   │   │   │   ├── route.js
│   │   │   ├── route.js
│   ├── TicketPage/
│   │   ├── [id]/
│   │   │   ├── page.jsx
│   ├── favicon.ico
│   ├── layout.js
│   ├── globals.css
│   ├── page.jsx
├── tailwind.config.js
```

## Setup

### Creating a New App

To create a new app, use the following command:

```bash
npx create-next-app <your-app-name>
```

**Note:** Avoid using capital letters in the app name.

### Extensions Used in VS Code

- **ES7 + React/Redux/React-Native Snippets**
- **ESLint**
- **Prettier**
- **Tailwind CSS IntelliSense**

### Useful Shortcuts

- **rafce**: Creates a default page component.
- **Ctrl+Shift+L**: Allows you to change all occurrences of a word on a page.

### Folder Naming Conventions

Folders with names enclosed in parentheses `()` will not be included in routing (e.g., `(components)`).

### Installing Icons

To use free icons, install the following packages:

```bash
npm install @fortawesome/free-solid-svg-icons @fortawesome/react-fontawesome
```

### Tailwind CSS Configuration

Define your default colors and other settings in `tailwind.config.js`.

### Global CSS

Define global properties in `globals.css`.

## Components and Functionalities

### Navigation

In `Nav.jsx`, links to the home page and ticket page are added, along with an email ID.

### Dashboard

Components such as `TicketCard` and `DeleteBlock` are created and displayed on the dashboard. Ticket sizes adjust according to screen size.

### TicketForm

Basic functionalities for the `TicketForm` are added and connected to MongoDB Atlas. For this project, access is allowed from anywhere, though this is not recommended for production.

- **Database Name**: TicketDB
- **Collection Name**: tickets

### Database Connection

1. **Create a model** for your data.
2. Navigate to `Overview -> Connect -> Connect to <cluster-name> -> Copy string`.
3. Paste the connection string in `.env.local`.

### Adding Tickets

A form to add ticket data is created in `route.js`, using `clientJS` in `TicketForm.js`.

### Data Handling

- Use `==` for type-insensitive comparisons.
- Create a route to get all tickets using an asynchronous GET function.
- Categorize tickets into **Hardware**, **Software**, and **Projects**.
- Use destructuring to handle state updates and other operations.

### Ticket Operations

Tickets can be updated and deleted, utilizing functional components.

## Future Enhancements

- Add authentication.
- Allow users to add custom categories.
- Improve organization and structure.

## FAQs

### Question 1: Why do we use "use client" in the TicketForm?

The `"use client"` directive indicates that the component should be rendered on the client side. This is important for interactive elements and client-specific operations.

### Question 2: What is Destructuring?

Destructuring is a syntax in JavaScript that allows you to unpack values from arrays or properties from objects into distinct variables.

Example:

```javascript
setFormData((prevState) => ({
  ...prevState,
  [name]: value,
}));
```

In this example, the previous state is spread into a new object, and the `[name]` property is updated with the new `value`.

### Question 3: What are async Functions?

Async functions are functions that return a `Promise` and allow the use of the `await` keyword to pause execution until the `Promise` is resolved.

### Question 4: Why do we use await?

The `await` keyword is used to pause the execution of an async function until the `Promise` is resolved, allowing for asynchronous, non-blocking code execution.

### Question 5: What are hooks in Next.js and how does wrapping happen?

Hooks in Next.js are special functions (like `useState` and `useEffect`) that allow you to use state and other React features in functional components. Wrapping occurs when hooks are used within functional components to manage state and lifecycle methods.

---
