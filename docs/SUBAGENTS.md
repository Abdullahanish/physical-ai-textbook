
# Bonus: Subagents & Reusable Intelligence

To accelerate the creation and maintenance of the textbook, we can design a system of specialized "subagents" built on top of a powerful language model like Claude. These agents act as expert assistants, each with a specific role in the content lifecycle.

This approach introduces the concept of **Reusable Intelligence**, where we define and refine specific "skills" that can be used by different agents or combined to perform complex tasks.

## 1. Subagent Design

We can define a team of subagents, each with a clear responsibility. These would be implemented as distinct prompts or classes within a larger content management framework.

### a) The Chapter Writer Agent

-   **Role:** The primary content generator.
-   **Prompt/Instructions:**
    ```
    You are an expert technical writer specializing in AI and Robotics for beginners. Your task is to write a section of the textbook "Physical AI & Humanoid Robotics" based on the Spec-Kit Plus methodology.

    Your tone should be clear, simple, and encouraging. Use short paragraphs, bullet points, and simple analogies. Avoid jargon where possible, and explain it clearly when necessary.

    You will be given the Chapter Title, the Section (e.g., "Detailed Explanation"), and a list of key topics to cover. You must generate content that is Docusaurus-compatible Markdown.
    ```
-   **Input:** `{ "Chapter": "Humanoid Robots", "Section": "Detailed Explanation", "Topics": ["Bipedal Locomotion", "ZMP", "Dexterous Manipulation"] }`
-   **Output:** A well-structured Markdown document for that specific section.

### b) The Quiz Generator Agent

-   **Role:** Creates assessment materials for each chapter.
-   **Prompt/Instructions:**
    ```
    You are an AI assessment creator. Based on the provided chapter content, generate a set of questions to test a beginner's understanding.

    You must generate:
    - 4 multiple-choice questions with a single correct answer.
    - 3 true/false questions.
    - 2 short-answer questions that require a 1-2 sentence explanation.

    Provide an answer key at the end. The questions should directly relate to the key concepts in the text.
    ```
-   **Input:** The full Markdown content of a chapter.
-   **Output:** A Markdown file with questions and a separate answer key, matching the `06-assessment-questions.md` format.

### c) The Diagram Generator Agent

-   **Role:** Creates visual aids using Mermaid diagrams.
-   **Prompt/Instructions:**
    ```
    You are a visual explanation expert. Your task is to create a Mermaid diagram that visually represents the provided concept.

    The diagram should be as simple as possible while still being informative. Choose the best diagram type (flowchart, sequence, graph).

    Concept: [Description of the concept to be visualized]
    ```
-   **Input:** A text description, e.g., `"Show how a closed-loop feedback system works, including the setpoint, process variable, error, controller, and actuator."`
-   **Output:** A Docusaurus-compatible Markdown code block containing the Mermaid diagram.
    ```mermaid
    graph TD
        A(Setpoint) --> B{Compare};
        C(Process Variable) --> B;
        B -- Error --> D[Controller];
        D -- Command --> E(Actuator);
        E --> F(System);
        F -- Measured by Sensor --> C;
    ```

### d) The Content Reviewer Agent

-   **Role:** Acts as an editor to simplify and improve content.
-   **Prompt/Instructions:**
    ```
    You are an expert editor tasked with simplifying technical content for a first-year student. Review the following text and identify any jargon, complex sentences, or unclear explanations.

    Your goal is to make the text more readable and accessible without losing technical accuracy. Suggest specific rephrasing or alternative analogies.
    ```
-   **Input:** A chunk of text from the textbook.
-   **Output:** A list of suggested edits or a fully rewritten, simplified version of the text.

## 2. Reusable Agent Skills

The true power of this system comes from defining a library of **reusable skills**. A skill is a well-defined function or prompt that an agent can call to perform a specific, atomic task. These skills can be chained together to accomplish more complex goals.

### Skill Definition Example

A skill can be defined as a Python function that calls the LLM with a specific prompt.

```python
def explain_simply(text: str, audience: str = "a first-year student") -> str:
    """
    Takes a piece of text and asks an LLM to explain it simply
    for a specific audience.
    """
    prompt = f"""
    Explain the following text simply, as if you were talking to {audience}.
    Focus on the core concept and use a simple analogy if possible.

    Text: "{text}"

    Simple Explanation:
    """
    # ... code to call the LLM with the prompt ...
    return llm_response
```

### Library of Reusable Skills

-   `explain_this_chapter_simply(chapter_content)`: Uses the "explain simply" skill on the chapter summary.
-   `generate_mcqs(text_chunk, num_questions=3)`: Generates a set of multiple-choice questions based *only* on the provided text chunk.
-   `summarize_selected_text(text_chunk)`: Provides a concise summary of a piece of text.
-   `create_exam_questions(list_of_chapters, num_questions=20)`: A more complex skill that can pull from multiple chapters to create a final exam, ensuring a mix of topics.
-   `suggest_diagram(text_chunk)`: Reads a piece of text and suggests if a diagram would be helpful, and if so, what kind.
-   `check_for_jargon(text_chunk)`: Identifies potentially confusing terms in a piece of text that might need a glossary definition.

By building out this library of skills, you create a powerful "Content OS" where complex editorial and content creation tasks can be automated by combining simple, reliable, and intelligent building blocks.
