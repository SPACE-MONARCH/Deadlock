# Deadlock Defender









An interactive Operating Systems learning platform for visualizing, simulating, and practicing **deadlock avoidance, detection, and recovery**.

## Overview

Deadlock Defender is a web-based educational application designed to make core OS deadlock concepts easier to understand through interactive tools, guided modules, and AI-assisted practice. Instead of learning only through static textbook examples, users can explore dynamic simulations, modify system states, and observe how processes and resources interact in real time.

The platform combines conceptual learning with hands-on experimentation through modules such as the **Resource Allocation Graph Simulator**, **Banker’s Algorithm Simulator**, **Deadlock Detection & Recovery**, **scenario-based games**, and an **adaptive AI quiz**. The application is built with **Next.js**, **TypeScript**, **Firebase**, **Tailwind CSS**, **shadcn/ui**, and **Genkit with Gemini-powered AI flows**.

## Screenshots

> Replace these paths with your actual screenshots after uploading them to the repository.

### Dashboard
```md
![Dashboard](./screenshots/dashboard.png)
```

### RAG Simulator
```md
![RAG Simulator](./screenshots/rag-simulator.png)
```

### Banker’s Algorithm
```md
![Banker's Algorithm](./screenshots/bankers-algorithm.png)
```

### Game Scenarios
```md
![Game Scenarios](./screenshots/scenarios.png)
```

## Features

- Interactive dashboard for accessing all learning modules
- Introductory learning module for processes, resources, and deadlock basics
- Deadlock prevention module with guided concept explanations
- **Resource Allocation Graph Simulator** for visualizing request/assignment edges and cycle detection
- **Banker’s Algorithm Simulator** for safe-state checking and resource allocation analysis
- **Deadlock Detection & Recovery** module for identifying deadlocked processes and testing recovery strategies
- **Game Scenarios** such as:
  - Printer Queue Jam
  - Database Connection Overload
  - Manufacturing Assembly Race
- **Adaptive AI Quiz** that changes difficulty based on learner performance
- AI-generated safe, unsafe, deadlocked, and random practice inputs
- Responsive dark-themed UI with sidebar navigation and loading states

## AI Capabilities

Deadlock Defender uses **Genkit + Gemini** to support dynamic learning experiences.

### Implemented AI flows
- `adaptive-learning-path.ts` — adjusts difficulty based on quiz performance
- `generate-deadlock-scenario.ts` — generates matrix-based random, safe, or deadlocked states
- `generate-rag-scenario.ts` — generates safe or cyclic resource allocation graphs
- `generate-scenario-state.ts` — creates scenario-specific state variations for games

These flows help the app produce fresh inputs for repeated practice instead of relying on only hardcoded examples.

## Tech Stack

### Frontend
- Next.js 15
- React 18
- TypeScript
- Tailwind CSS
- shadcn/ui
- Radix UI
- Framer Motion

### Backend / Services
- Firebase Firestore
- Firebase Authentication

### AI Layer
- Genkit
- Google Gemini 2.5 Flash

## Project Structure

```bash
src/
├── app/
│   ├── page.tsx
│   ├── adaptive-quiz/
│   ├── learn/
│   │   ├── basics/
│   │   └── prevention/
│   ├── scenarios/
│   │   ├── page.tsx
│   │   └── [id]/
│   └── tools/
│       ├── bankers-algorithm/
│       ├── detection-recovery/
│       └── rag-simulator/
├── ai/
│   ├── dev.ts
│   ├── genkit.ts
│   └── flows/
├── components/
│   ├── icons/
│   ├── layout/
│   └── ui/
├── firebase/
├── hooks/
└── lib/
```

## Installation

### Prerequisites

Make sure you have the following installed or configured:
- Node.js
- npm
- Firebase project
- Gemini / Google AI access for Genkit-based flows

### Clone and install

```bash
git clone <your-repo-url>
cd deadlock-defender
npm install
```

## Environment Variables

Create a `.env.local` file and add:

```env
NEXT_PUBLIC_FIREBASE_API_KEY=
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=
NEXT_PUBLIC_FIREBASE_PROJECT_ID=
NEXT_PUBLIC_FIREBASE_APP_ID=
```

If you are using Genkit and Gemini locally, also add the required Google AI credentials.

## Running Locally

### Start the app

```bash
npm run dev
```

### Start Genkit

```bash
npm run genkitdev
```

### Start Genkit in watch mode

```bash
npm run genkitwatch
```

## Available Scripts

```bash
npm run dev         # Start Next.js dev server
npm run genkitdev   # Start Genkit dev server
npm run genkitwatch # Start Genkit in watch mode
npm run build       # Create production build
npm run start       # Start production server
npm run lint        # Run linting
npm run typecheck   # Run TypeScript checks
```

## Firestore Setup

The app stores scenario data in the `scenarios` collection.

Related files:
- `src/lib/scenarios.ts` — scenario seed data
- `src/lib/seed.ts` — helper for seeding Firestore
- `firestore.rules` — Firestore access rules

> **Note:** The current Firestore rules are open for development and testing. Restrict read/write access before using the project in production.

## Deployment

This project is best deployed on **Vercel** for full Next.js compatibility, especially when using dynamic functionality and AI-assisted features.

Before deployment:
1. Add all Firebase and AI-related environment variables
2. Verify Firestore rules for production safety
3. Ensure Genkit / Gemini configuration is properly set

## Future Improvements

- Secure Firestore rules for production
- Add learner progress persistence
- Expand scenario library
- Add more analytics for adaptive learning
- Improve production deployment of AI-backed features

## License

This project is intended for educational and academic use.
