
# Frontend Integration: Adding the Chatbot to Docusaurus

Integrating a custom React-based chatbot into a Docusaurus project can be done smoothly by leveraging Docusaurus's architecture, specifically by creating a custom component and using the "swizzling" feature.

## 1. Adding a Floating Chatbot UI

The goal is to have a floating action button (FAB) in the corner of the screen that opens the chatbot interface.

### Step 1: Create the Chatbot Component

First, you would create the entire chatbot UI as a self-contained React component. This would likely be a folder `src/components/Chatbot` containing:

-   `Chatbot.js`: The main component that manages the state (open/closed, messages, loading status).
-   `Chatbot.css`: Styles for the floating button, the chat window, messages, etc.
-   `ChatbotIcon.js`: The icon for the floating button.

The `Chatbot.js` component would handle all its internal logic, such as:
- Toggling the chat window's visibility.
- Maintaining an array of chat messages.
- Displaying a "loading" indicator while waiting for the backend.
- Calling the API service to send requests.

### Step 2: Swizzle the Root Component

Docusaurus allows you to override any theme component using a command called `swizzle`. The best place to add a site-wide component like a chatbot is in the root layout.

You would run the following command:

```bash
npm run swizzle @docusaurus/theme-classic Root
```

This command ejects the `Root.js` component from the default theme into your `src/theme` directory. Now you can edit it.

### Step 3: Integrate the Chatbot

You would then modify the newly created `src/theme/Root.js` file to import and render your chatbot component.

```jsx
// src/theme/Root.js
import React from 'react';
import Root from '@theme-original/Root'; // Import the original component

// Import your custom chatbot component
import Chatbot from '../../components/Chatbot/Chatbot';

export default function RootWrapper(props) {
  return (
    <>
      {/* The original Root component renders the entire Docusaurus site */}
      <Root {...props} />

      {/* Render your Chatbot component alongside it */}
      <Chatbot />
    </>
  );
}
```

Because your `Chatbot` component's CSS will give it `position: fixed`, it will now float above all the other Docusaurus content, available on every page.

## 2. Connecting to the FastAPI Backend

The chatbot needs to communicate with the FastAPI backend you've designed.

### API Service Module

It's best practice to create a dedicated API service module to handle the HTTP requests.

```javascript
// src/components/Chatbot/apiService.js

const API_BASE_URL = 'https://your-fastapi-backend.com'; // Replace with your actual backend URL

export async function askQuestion(question, context = null) {
  const payload = {
    question: question,
  };

  if (context) {
    payload.context = context;
  }

  const response = await fetch(`${API_BASE_URL}/ask`, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
    },
    body: JSON.stringify(payload),
  });

  if (!response.ok) {
    throw new Error('Network response was not ok');
  }

  return response.json(); // Or handle streaming response
}
```

This service can then be imported and used within your `Chatbot.js` component whenever a user sends a message.

## 3. Passing User-Selected Text

To enable the feature where a user can highlight text and ask a question about it, you need to capture the selected text from the browser.

### Using the `window.getSelection()` API

You can add a global event listener to the `document` to detect when a user finishes making a text selection.

This logic could be placed in your `Chatbot.js` component using a `useEffect` hook.

```jsx
// Inside your Chatbot.js component

import React, { useState, useEffect } from 'react';

function Chatbot() {
  const [selectedText, setSelectedText] = useState(null);

  const handleSelection = () => {
    const text = window.getSelection().toString();
    if (text.length > 0) {
      setSelectedText(text);
      // Maybe show a small "Ask about this" button near the selection
    } else {
      setSelectedText(null);
    }
  };

  useEffect(() => {
    document.addEventListener('mouseup', handleSelection);
    return () => {
      document.removeEventListener('mouseup', handleSelection);
    };
  }, []);

  // ... rest of your chatbot logic

  // When the user asks a question, you can now check if `selectedText` exists
  // and pass it to your apiService.askQuestion function.
  const handleSendMessage = async (message) => {
    // ...
    const response = await apiService.askQuestion(message, selectedText);
    // ...
  };

  return (
    // ... your UI
  );
}
```

When the user selects text, a small pop-up could appear next to the highlighted text (e.g., "Ask about this selection"). Clicking this button would open the chatbot interface and pre-fill the context for the next question. This creates a powerful, context-aware interaction directly within the textbook content.
