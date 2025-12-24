
# Physical AI & Humanoid Robotics: An AI-Native Textbook

Welcome to the AI-Native Textbook project for "Physical AI & Humanoid Robotics." This project was created for a hackathon and serves as a demonstration of building an educational resource using modern AI and web technologies.

This textbook is built with **Docusaurus**, structured with **Spec-Kit Plus**, and features a **RAG-based AI chatbot** for interactive learning.

## 1. Project Structure

-   `/docs`: Contains all the textbook content, written in Docusaurus-compatible Markdown.
    -   `/1-introduction-to-physical-ai`: Each chapter is a folder.
    -   `_category_.json`: This file in each chapter folder sets the title and position in the sidebar.
    -   `01-learning-objectives.md`, `02-key-concepts.md`, etc.: Each chapter is broken down into sections based on the Spec-Kit Plus methodology.
-   `/src`: Contains custom React components and Docusaurus configuration.
-   `/static`: For static assets like images.

## 2. How to Run This Project Locally

### Prerequisites

-   Node.js (v18 or newer)
-   npm or yarn

### Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd physical-ai-textbook
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

### Running the Development Server

To start the Docusaurus development server and view the textbook:

```bash
npm run start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server. The site is usually available at `http://localhost:3000`.

### Building the Project

To build a static, production-ready version of the site:

```bash
npm run build
```

This command generates static content into the `build` directory. This is the folder that will be deployed to a web server.

## 3. Key Features

-   **Spec-Kit Plus Structure:** Every chapter is consistently structured with Learning Objectives, Key Concepts, Detailed Explanations, Real-World Examples, Exercises, Assessment Questions, and a Chapter Summary.
-   **Docusaurus Framework:** A modern, documentation-focused framework that provides features like Markdown support, theming, and fast navigation.
-   **AI Chatbot (Conceptual):** The project includes detailed documentation for implementing a RAG-based chatbot that can answer questions based on the textbook's content. See `/docs/RAG_ARCHITECTURE.md` for details.
-   **Subagent Framework (Conceptual):** Documentation is included for a system of AI subagents to help automate content creation and review. See `/docs/SUBAGENTS.md` for details.
