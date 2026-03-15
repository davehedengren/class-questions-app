# Sunday School Object Lesson Games — Claude Code Context

## Mission
Draw people closer to Jesus Christ through the teachings of The Church of Jesus Christ of Latter-day Saints. Every project built here serves that goal. When in doubt, ask: "Does this help a teenager feel the Spirit or understand a gospel principle?"

## Tone & Voice
Write like a **fun improv comedy youth minister**. Think: someone who would open a lesson with a ridiculous hypothetical, get the kids laughing, then land a genuinely moving spiritual point. Humor is the vehicle, not the destination.

- Warm, energetic, slightly irreverent (but never disrespectful to sacred things)
- Use language teens actually use — no "thee/thou" unless it's a joke
- Object lessons should feel like games first, lessons second
- The spiritual connection should land naturally, not feel forced
- When writing LLM prompts for in-game characters or activities, maintain this voice

## Audience
**LDS teens, ages 15–18** (Sunday School / seminary context)
- They have phones. Use that.
- They know scripture stories but may not connect them to real life yet
- They respond to competition, humor, and moments of genuine sincerity
- Assume a class of 5–15 students with one teacher projecting to a screen

## Tech Stack & Patterns
Based on prior projects, follow these conventions:

- **Backend:** Python + Flask (lightweight, no build step)
- **Frontend:** Jinja2 templates, vanilla JS, minimal CSS — no frameworks unless the project demands it
- **Database:** SQLite (simple, file-based, Replit-friendly)
- **LLM integration:** Use the API keys in `.env` (OpenAI, Anthropic, Gemini, Hugging Face)
- **Image generation:** Hugging Face or OpenAI DALL-E via `.env` keys
- **Deployment target:** Replit (fork, set secrets, run)
- **Entry point:** `start.py` with sensible defaults for missing env vars

### Project Structure Convention
```
project-name/
├── app.py              # Flask routes
├── db.py               # Database helpers (if needed)
├── schema.sql          # SQLite schema (if needed)
├── prompts.py          # LLM prompt templates
├── start.py            # Entry point (Replit-ready)
├── requirements.txt    # Python dependencies
├── .env                # API keys (never commit)
├── .gitignore
├── static/
│   ├── css/
│   └── js/
└── templates/
```

### Replit Deployment Checklist
1. API keys go in **Replit Secrets** (not .env)
2. `start.py` should set sane defaults if env vars are missing
3. Host on `0.0.0.0`, default port `8080`
4. SQLite file persists on Replit disk — no external DB needed
5. Zero build step — `python start.py` and go

## .env API Keys Available
- `OPENAI_API_KEY` — GPT models, DALL-E image generation
- `ANTHROPIC_API_KEY` — Claude models
- `GEMINI_API_KEY` — Google Gemini models
- `HUGGING_FACE_API_KEY` — Open-source models, image generation (Stable Diffusion, FLUX, etc.)

## What Gets Built Here
This repo is a **staging workspace**. Projects start here, get prototyped, then move to standalone repos for Replit hosting. Types of things we build:

- **Object lesson games** — interactive activities that teach a gospel principle through gameplay
- **Survey/polling tools** — collect and display student responses in real time
- **Scripture-based activities** — quizzes, matching games, story builders using scripture content
- **Image-based games** — generate or use images as part of lessons (e.g., "guess the scripture story")
- **LLM-powered activities** — chatbots, story generators, or debate simulators with a gospel twist

## Working In This Repo
- Each new project gets its own subdirectory
- Shared utilities (if any emerge) go in a top-level `shared/` directory
- When a project is ready to ship, it should be self-contained and copyable to its own repo
- Always include a `requirements.txt` and `start.py` in each project
- Test locally before considering it Replit-ready
