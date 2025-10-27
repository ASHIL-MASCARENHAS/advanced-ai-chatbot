1. Project Objective

The primary objective was to create a modern, feature-rich chatbot web application. The goal was to move beyond simple text-only bots and incorporate advanced AI capabilities such as multimodal input (images), voice I/O (STT/TTS), and grounded, real-time web search.

2. Features Implemented

Core Chat: A responsive, dark-theme UI for conversations.

Multimodality: Users can upload images, and the AI (Gemini) will analyze the image as part of the prompt.

Voice-to-Text (STT): Leverages the browser's Web Speech API to transcribe user voice into text.

Text-to-Speech (TTS): Uses the Gemini TTS API to convert the bot's text response into audible speech.

Google Search Grounding: A toggle allows the bot to access Google Search for up-to-date information, providing sources and citations.

Secure API Management: The application is designed to load the secret API key from an external config.js file, which is explicitly ignored by Git to prevent it from being exposed in a public repository.

3. Technologies Used

Frontend: HTML, Tailwind CSS

Logic: JavaScript (ES6+)

APIs:

Gemini API (gemini-2.5-flash-preview-09-2025): For text generation and image understanding.

Gemini TTS API (gemini-2.5-flash-preview-tts): For audio generation.

Web Speech API (Browser): For speech recognition.