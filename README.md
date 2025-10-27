# Advanced AI Chatbot

This is a single-page web application for an advanced AI chatbot powered by the Gemini API. It features a modern, dark-themed, responsive interface and supports text, image, and voice interactions.

## Features

**Multimodal Chat**: Send text prompts or upload images for analysis.

**Voice-to-Text (STT)**: Use your microphone to dictate prompts.

**Text-to-Speech (TTS)**: Enable voice responses to have the bot speak its answers.

**Grounded Responses**: Toggle "Enable Google Search" to get real-time, verifiable answers with sources.

**File Handling**: Attach images for visual Q&A.

**Secure API Key**: Loads API key from an ignored config.js file to keep your key private in a public repository.

**Dark Theme**: Sleek, modern dark mode interface.

## Technologies Used

-HTML5

- Tailwind CSS

- JavaScript (ES6+)

- Gemini API (for text generation, image understanding, TTS, and search grounding)

- Browser Web Speech API (for speech-to-text)

## Project Setup

To run this project locally, follow these steps:

Clone the Repository (or download the files):

```
git clone [https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git](https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git)
cd YOUR_REPO_NAME
```


Get Your `Gemini API Key`:

Go to `Google AI Studio`.

Create a new API key.

Create the `config.js` File:

Rename config.example.js to config.js.

Open config.js and paste your API key inside the quotes:

const GEMINI_API_KEY = "PASTE_YOUR_GEMINI_API_KEY_HERE";


## Run the Application:

You cannot just open advanced_chatbot.html directly in your browser due to security rules (CORS) for local files.

You must serve it from a local web server. The easiest way is using the live-server VS Code extension or running a simple Python server:

## If you have Python 3
```python -m http.server```


Then, open your browser and go to http://localhost:8000/advanced_chatbot.html.

## Deployment

- You can deploy this project as a static website on platforms like Netlify, Vercel, or GitHub Pages.

- Important for Deployment: You cannot use the config.js file method for a deployed site, as it would be publicly visible. You have two main options:

- (Not Recommended) Hard-code the key: Paste your key directly into advanced_chatbot.html. This is easy but very insecure. Anyone can steal your key.

- (Recommended) Use a Serverless Function:

- Deploy this as a static site (e.g., on Netlify).

- Create a Netlify "serverless function" (in JavaScript) that acts as a middle-man.

- Your frontend (HTML) calls this function.

- The function (running on Netlify's server) adds your API key (stored as a secure "environment variable") and then calls the Gemini API.

- This keeps your key 100% private.# advanced-ai-chatbot
