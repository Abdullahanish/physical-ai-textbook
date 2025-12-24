
# Hackathon Submission Checklist

Use this checklist to ensure your project is ready for submission and judging.

## 1. Core Project Requirements

-   [x] Project is a Docusaurus-based website.
-   [x] Textbook content is located in the `/docs` directory.
-   [x] Project follows the specified folder structure.
-   [x] Textbook is titled "Physical AI & Humanoid Robotics."

## 2. Content & Structure (Spec-Kit Plus)

-   [x] All chapters are structured using the Spec-Kit Plus methodology.
-   For each completed chapter, check the following:
    -   [x] `01-learning-objectives.md` exists and is filled out.
    -   [x] `02-key-concepts.md` exists and is filled out.
    -   [x] `03-detailed-explanation.md` exists and is filled out.
    -   [x] `04-real-world-examples.md` exists and is filled out.
    -   [x] `05-exercises.md` exists and is filled out.
    -   [x] `06-assessment-questions.md` exists and includes an answer key.
    -   [x] `07-chapter-summary.md` exists and is filled out.
-   [x] Content is written in simple, beginner-friendly language.
-   [x] Mermaid diagrams are used where helpful to explain concepts.

## 3. Technical Implementation (RAG Chatbot)

-   [x] High-level architecture is documented in `docs/RAG_ARCHITECTURE.md`.
-   [x] Document clearly outlines the backend stack (FastAPI, Postgres, Qdrant).
-   [x] Document explains the data ingestion and chunking strategy.
-   [x] Document explains the retrieval and response flow.
-   [x] Document covers both "whole book" and "selected text" query modes.

## 4. Frontend Integration

-   [x] Explanation for integrating a floating chatbot UI is documented in `docs/FRONTEND_INTEGRATION.md`.
-   [x] Document explains how the frontend connects to the FastAPI backend.
-   [x] Document explains the mechanism for passing user-selected text to the chatbot.

## 5. Bonus Features (Subagents)

-   [x] Design for subagents (Chapter Writer, Quiz Generator, etc.) is documented in `docs/SUBAGENTS.md`.
-   [x] Concept of reusable agent "skills" is defined and examples are provided.

## 6. Finalization & Deployment

-   [x] A comprehensive `README.md` is present in the project root.
    -   [x] README includes a project overview.
    -   [x] README includes clear setup and local running instructions (`npm install`, `npm run start`).
-   [x] Deployment instructions for GitHub Pages are documented in `docs/DEPLOYMENT.md`.
-   [ ] The project has been successfully deployed to a public URL (e.g., GitHub Pages).
-   [ ] The submission includes the link to the live, deployed textbook.
-   [ ] The submission includes the link to the source code repository.

---
### Final Review
- [ ] **Clarity and Polish:** Read through the deployed textbook. Is it easy to navigate? Is the content clear? Are there any broken links or formatting errors?
- [ ] **Hackathon Rules:** Double-check all the specific rules and scoring criteria for the hackathon to ensure all points have been addressed.
