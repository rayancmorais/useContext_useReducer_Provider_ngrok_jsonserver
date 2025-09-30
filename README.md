# ⚛️ useContext, useReducer, Provider, ngrok & json-server Demo

This repository serves as a boilerplate or demonstration project showcasing best practices for **global state management** in a modern React application. It integrates the **`useContext`** and **`useReducer`** Hooks for predictable, centralized state, and connects the front-end to a simulated local **REST API** using **`json-server`**, which is then exposed publicly with **`ngrok`**.

---

## 🛠️ Tech Stack & Concepts

| Technology | Purpose |
| :--- | :--- |
| **React** | Front-end library for building user interfaces. |
| **`useContext` & `Provider`** | React's built-in mechanism for global state access, specifically designed to avoid **prop drilling**. |
| **`useReducer`** | A state management hook for complex state logic, often used as a scalable, built-in alternative to Redux. |
| **`json-server`** | A lightweight tool to quickly spin up a fake **REST API** from a simple JSON file. |
| **`ngrok`** | A utility that creates a secure tunnel from a public endpoint to a locally running service, making the API accessible externally (e.g., for mobile testing). |

---

# React State Management with Mock Backend

## useContext_useReducer_Provider_ngrok_jsonserver

This project is a boilerplate demonstrating a robust and scalable method for **React state management** using the built-in **`useContext`** and **`useReducer`** hooks. It simulates a full-stack application by utilizing **`json-server`** as a lightweight, fake REST API backend and includes instructions for using **`ngrok`** to expose this local API to the internet for testing or external consumption.

---

## 🚀 Features

* **Centralized State:** Implements a global state using the Context API (`useContext`) wrapped in a custom `Provider` component.
* **Predictable State Logic:** Uses the **`useReducer`** hook to handle complex state transitions in an organized and testable manner, following the Redux pattern (Actions and Reducers).
* **Mock Backend:** Utilizes **`json-server`** to quickly spin up a RESTful API for handling CRUD operations without the need for a full database setup.
* **Public Tunneling:** Includes instructions for using **`ngrok`** to create a secure tunnel to the locally running `json-server`, making the API accessible via a public URL.

---

## 🛠️ Prerequisites

Before you begin, ensure you have the following installed on your machine:

* **Node.js** (LTS version recommended)
* **npm** or **yarn** (for package management)
* **ngrok** (If you plan to expose your local API publicly. Install globally via `npm install -g ngrok` or download from the [ngrok website](https://ngrok.com/)).

---

## ⚙️ Installation and Setup

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/rayancmorais/useContext_useReducer_Provider_ngrok_jsonserver.git](https://github.com/rayancmorais/useContext_useReducer_Provider_ngrok_jsonserver.git)
    cd useContext_useReducer_Provider_ngrok_jsonserver
    ```

2.  **Install dependencies:**
    ```bash
    # Using npm
    npm install

    # Or using yarn
    yarn install
    ```

3.  **Setup the Mock API (`json-server`)**:
    * Ensure there is a file named **`db.json`** in the project root to define your mock data structure.
    * The `package.json` should contain a script to run the server (e.g., `npm run server`).

---

## 🏃 Running the Project

This project requires two separate processes to run concurrently: the **Mock API Server** and the **React Client**.

### 1. Start the Mock API

Start `json-server`. Assuming the API runs on port **3004** (a common default for `json-server`) and the script is defined:

```bash
# Start the fake API server (usually runs on http://localhost:3004)
npm run server
# or
yarn server
```

2. Start the React Client

Start the React development server:

```bash
# Start the React client application (usually runs on http://localhost:3000)
npm start
# or
yarn start
```
Your application should now be running and communicating with the local mock API.
---
3. (Optional) Expose the API using ngrok

If you need to share your mock API with others or test webhooks, use ngrok. Assuming your json-server is running on port 3004:
```bash
# Create a public URL for your local json-server
ngrok http 3004
```
Note: This command will output a temporary public HTTPS URL (e.g., https://abcdefg.ngrok.io). You will need to update your React application's API configuration to use this new URL instead of http://localhost:3004.

---

## 💡 Key Concepts

| Concept | Description |
| :--- | :--- |
| `useContext` | A React hook that allows components to consume context (global data) without passing props deep down the tree. |
| `useReducer` | The preferred state hook for complex state logic. It manages state using a **`reducer`** function, which takes the current state and an action to return a new state. |
| **`Provider`** | The component that wraps the application's root, providing the global state and dispatch function via the Context API. |
| **`json-server`** | A zero-setup tool to create a full fake REST API in less than a minute, based on a JSON file. |
| **`ngrok`** | A tool that exposes local web servers to the public internet over secure tunnels. |
