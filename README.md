# Sunday School Object Lesson Games

A workspace for prototyping interactive gospel-teaching games for LDS teens (ages 15–18).

## What This Is

This repo is a **staging area** for building Sunday School object lesson games. Each project starts here as a subdirectory, gets prototyped and tested, then ships to its own Replit for classroom use.

The goal: **draw people closer to Jesus Christ** through interactive, fun, teen-friendly activities that connect gameplay to gospel principles.

## How It Works

1. **Start a new project** — create a subdirectory with the standard structure (see below)
2. **Build and test locally** — Flask apps, vanilla JS, SQLite
3. **Ship to Replit** — copy the project to its own repo, set secrets, deploy

## Project Structure

Each game/activity lives in its own folder:

```
sunday-school-claude-code/
├── CLAUDE.md               # Context for Claude Code sessions
├── agents.md               # Reusable LLM prompt templates
├── .env                    # API keys (OpenAI, Anthropic, Gemini, HuggingFace)
├── .gitignore
├── README.md
└── project-name/           # Each game is a self-contained Flask app
    ├── app.py
    ├── start.py
    ├── requirements.txt
    ├── templates/
    └── static/
```

## Available API Keys (.env)

| Key | Use |
|-----|-----|
| `OPENAI_API_KEY` | GPT models, DALL-E images |
| `ANTHROPIC_API_KEY` | Claude models |
| `GEMINI_API_KEY` | Google Gemini |
| `HUGGING_FACE_API_KEY` | Open-source models, Stable Diffusion/FLUX |

## Past Projects

- **[sunday-school-survey-tool](../sunday-school-survey-tool/)** — Real-time student response board with QR code join, presenter mode, and AI "best response" selection

## Game Ideas (from agents.md)

- **Would You Rather** — Gospel-themed choices with scripture connections
- **Scripture Telephone** — Paraphrase chain with drift scoring
- **Prophet or Nah** — Real vs. fake quote guessing game
- **The Parable Machine** — Modern scenarios turned into parables
- **Emoji Scripture** — Guess the scripture story from emojis
- **Debate Simulator** — LLM argues a position, students sharpen their thinking

## Deploying to Replit

1. Copy the project folder to a new Replit
2. Add API keys to **Replit Secrets** (not .env)
3. Run `python start.py`
4. Share the URL with your class
