# React Sidebar and Modal Component with Context API

This project demonstrates how to implement and manage the state of a Sidebar and a Modal component in a React application using the Context API for global state management. It features a main page with buttons to toggle the visibility of both the sidebar and the modal. The state (whether the sidebar or modal is open) is handled globally via a custom context hook (`useGlobalContext`), making it accessible throughout the component tree without prop drilling. The content for the sidebar links and social icons is dynamically loaded from a separate data file.

## ✨ Features

- **Global State Management:** Utilizes React Context API (`createContext`, `useContext`) to manage the open/closed state of the sidebar and modal globally.
- **Custom Hook:** Implements a `useGlobalContext` custom hook for easy access to the global state and actions.
- **Toggleable Sidebar:** A sidebar component that can be opened and closed via a button click, displaying navigation links and social icons.
- **Toggleable Modal:** A modal component that can be opened and closed, overlaying the main content.
- **Data-Driven Content:** Sidebar links and social icons are sourced from a `data.jsx` file for easy modification.
- **Icon Integration:** Uses `react-icons` for visual elements like toggle buttons, close buttons, and navigation icons.
- **CSS Transitions:** (Assumed based on class toggling like `show-sidebar`, `show-modal`) Uses CSS for smooth transitions when opening/closing components.

## 🚀 Live Demo

[Link to Live Demo](https://sidebarnoto.netlify.app/)

## 🛠️ Technologies Used

- **Frontend:** React.js (Hooks: `useState`, `useContext`)
- **State Management:** React Context API
- **Icons:** `react-icons`
- **Styling:** CSS

## ⚙️ Setup and Installation

To run this project locally, follow these steps:

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/NoToRacism/Sidebar
    cd <your-repository-directory>
    ```

2.  **Install dependencies:**
    Make sure you have Node.js and npm (or yarn) installed.

    ```bash
    npm install
    # or
    yarn install
    ```

3.  **Run the development server:**
    ```bash
    npm start
    # or
    yarn start
    ```
    This will typically open the application in your default browser at `http://localhost:3000`.

## 📖 Usage / Integration

1.  **Wrap your App:** Ensure your main application component (or relevant part of the tree) is wrapped with the `AppProvider` from `Context.jsx` to make the global context available.

    ```javascript
    // In main.jsx or index.js
    import React from "react";
    import ReactDOM from "react-dom/client";
    import App from "./App";
    import { AppProvider } from "./Context"; // Import the provider
    import "./index.css"; // Import CSS

    ReactDOM.createRoot(document.getElementById("root")).render(
      <React.StrictMode>
        <AppProvider>
          {" "}
          {/* Wrap App with the provider */}
          <App />
        </AppProvider>
      </React.StrictMode>
    );
    ```

2.  **Trigger Components:** The `Home` component demonstrates how to use the `useGlobalContext` hook to access `openSidebar` and `openModal` functions, which are triggered by button clicks.
3.  **Closing Components:** The `Sidebar` and `Modal` components use the `useGlobalContext` hook to access `closeSidebar` and `closeModal` functions, respectively, typically triggered by a close button (e.g., `<FaTimes />`).
4.  **Conditional Rendering:** The visibility of the `Sidebar` and `Modal` is controlled by CSS classes (`show-sidebar`, `show-modal`) which are conditionally applied based on the `isSidebarOpen` and `isModalOpen` state values from the global context.

## 🏗️ Project Structure

- `src/`: Contains the main source code.
  - `App.jsx`: Renders the main components (`Home`, `Modal`, `Sidebar`).
  - `Context.jsx`: Defines the `AppContext`, creates the `AppProvider` component (which holds the state and functions), and exports the `useGlobalContext` custom hook.
  - `Home.jsx`: Displays the main content and buttons to trigger the sidebar and modal using functions from the global context.
  - `Modal.jsx`: The modal component. Conditionally rendered based on `isModalOpen` state from context. Contains a close button.
  - `Sidebar.jsx`: The sidebar component. Conditionally rendered based on `isSidebarOpen` state from context. Displays links and social icons from `data.jsx`. Contains a close button.
  - `data.jsx`: Exports arrays (`links`, `social`) containing data and `react-icons` components for the sidebar.
  - `logo.svg`: (Assumed) Logo used in the Sidebar.
  - CSS Files (`index.css`, `App.css`, etc.): (Assumed) Contain the necessary styles for layout, transitions, and appearance of the components.
- `public/`: Contains static assets.
- `package.json`: Lists project dependencies and scripts.

## 🤝 Contributing

Contributions are welcome! If you'd like to contribute, please follow these steps:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-feature-name`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add some feature'`).
5.  Push to the branch (`git push origin feature/your-feature-name`).
6.  Open a Pull Request.
