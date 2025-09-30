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

## ✨ Features

* **Centralized State Logic:** All complex state updates are managed by a single **reducer** function, ensuring predictable state transitions.
* **Global Access:** Application state and dispatch functionality are globally accessible via the Context Provider, simplifying component code.
* **Mock API Setup:** Easy-to-use API backend for development, allowing you to prototype quickly without a dedicated back-end service.
* **External Access via ngrok:** Provides a temporary public URL for the local API, useful for testing on physical devices or sharing progress.

---

## 🚀 Getting Started

### Prerequisites

You must have the following installed on your system:

1.  **Node.js** (LTS recommended)
2.  **npm** or **yarn** (npm is used in the commands below)
3.  **ngrok** (You will need to [install it](https://ngrok.com/download) and [set up an account](https://dashboard.ngrok.com/signup) to get an auth token.)

### Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/rayancmorais/useContext_useReducer_Provider_ngrok_jsonserver.git](https://github.com/rayancmorais/useContext_useReducer_Provider_ngrok_jsonserver.git)
    cd useContext_useReducer_Provider_ngrok_jsonserver
    ```

2.  **Install front-end dependencies:**
    ```bash
    npm install
    ```

3.  **Create your JSON Database file:**
    Create a file named `db.json` in the project root to serve as your fake API database.

    *Example `db.json`:*
    ```json
    {
      "items": [
        { "id": 1, "name": "Item A" },
        { "id": 2, "name": "Item B" }
      ]
    }
    ```

4.  **Set up ngrok Auth Token:**
    If you haven't already, authenticate your `ngrok` installation using the token from your ngrok dashboard:
    ```bash
    ngrok config add-authtoken <YOUR_AUTH_TOKEN>
    ```

---

## 🏃 Running the Project

This project requires **three separate terminals** running concurrently for the full environment.

### Terminal 1: Start the Fake API (`json-server`)

This command starts the local mock API, typically on port `3000`.

```bash
npx json-server --watch db.json --port 3000
