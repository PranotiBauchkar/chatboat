# Recipedia Chatbot

A conversational chatbot for **Recipedia: Cook Smart. Waste Less.** — explains platform specs and **generates real recipes** via the **Gemini API**. Includes voice input (mic) and recipe card display.

## Setup

### 1. Install dependencies

```bash
cd recipedia-chatbot
npm install
cd server && npm install && cd ..
```

### 2. Add Gemini API key (for recipes)

1. Copy `server/.env.example` to `server/.env`
2. Add your key: `GEMINI_API_KEY=your-gemini-key-here`
3. Get a key at [Google AI Studio](https://aistudio.google.com/app/apikey)

### 3. Run the app

**Terminal 1 — Backend (required for recipes):**
```bash
npm run server
```

**Terminal 2 — Frontend:**
```bash
npm run dev
```

Open **http://localhost:5173** in your browser.

## Features

- **Recipedia info** — Platform overview, features, tech stack, future goals
- **Recipe generation** — Ask for any recipe; Gemini returns full recipes
- **Recipe display** — Recipes shown in a styled card (ingredients, steps, etc.)
- **Voice input** — Use the mic button to speak your request (Chrome/Edge)

## What You Can Ask

**Recipes (uses Gemini):**
- "Give me a recipe for pasta"
- "Recipe for chicken curry"
- "Easy breakfast with eggs"
- "Vegetarian dinner with rice"

**Platform info (local knowledge):**
- "What is Recipedia?"
- "What features does it have?"
- "Tech stack?" / "Future goals?"

## Tech Stack

- **Frontend:** React, Vite, CSS3
- **Backend:** Node.js, Express (Gemini API proxy)
- **Voice:** Web Speech API (browser)

## Project Structure

```
recipedia-chatbot/
├── src/
│   ├── App.jsx           # Chat UI, mic, message handling
│   ├── RecipeDisplay.jsx  # Recipe card component
│   ├── api.js            # Gemini API client (calls our backend)
│   ├── chatbotLogic.js   # Recipe detection + local responses
│   └── recipediaKnowledge.js
├── server/
│   ├── index.js          # Express + Gemini proxy
│   ├── .env              # GEMINI_API_KEY (create from .env.example)
│   └── package.json
└── package.json
```
