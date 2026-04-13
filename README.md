# 📚 FlashCard AI

Turn any PDF into smart, practice-ready flashcards using AI.

## Live Demo
🔗 https://srimat-cuemath-studio.vercel.app/

## What it does
- Upload any PDF (textbook, notes, chapter)
- AI generates 15-25 high quality flashcards instantly
- Study with flip cards — mark what you know and what you missed
- Spaced repetition (SM-2) — missed cards come back sooner, known cards fade
- Mastery tracking — see % mastered per deck
- Due for review badges — know exactly which decks need attention
- Search across all your decks

## Tech Stack
- **Frontend:** Next.js 14, React
- **AI:** Groq API (Llama 3.3 70B)
- **PDF Parsing:** unpdf
- **Storage:** localStorage
- **Deployment:** Vercel

## Key Decisions
- **Groq over OpenAI** — free tier, extremely fast, high quality output
- **localStorage over database** — no auth needed, instant setup, works offline
- **SM-2 algorithm** — proven spaced repetition used by Anki, backed by cognitive science
- **Next.js API routes** — keeps API key on server side, secure

## Challenges
- PDF parsing library (pdf-parse) had ESM compatibility issues with Next.js 16 — switched to unpdf
- SM-2 card index bug — due cards were saving progress to wrong indices — fixed by storing originalIndex on each card
- Free AI API rate limits — tried Gemini and OpenRouter before settling on Groq

## What I'd improve
- User auth + cloud sync so decks persist across devices
- Better math formula rendering (LaTeX support)
- Streamed card generation
- Mobile app

## Setup locally
1. Clone the repo
2. Run `npm install`
3. Create `.env.local` with `GROQ_API_KEY=your_key`
4. Run `npm run dev`
