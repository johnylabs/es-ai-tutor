# 🇪🇸 es-ai-immersion-lab

Spanish learning assistant built for myself.

This project is an **AI-powered Spanish immersion lab** where I can:

- Talk to an AI only in Spanish (with corrections and feedback).
- Save my mistakes and new vocabulary.
- Generate simple Anki decks from my logs so I can review later.

It’s built as a small Python app (with a Hugging Face / Gradio front end) so it both:
- Helps me reach **near-native Spanish**, and  
- Shows practical **NLP + language-learning tooling** on my GitHub.

---

## 🎯 Goals

- Learn Spanish by **doing**, not just flashcards:
  - Daily conversation sessions with an AI tutor.
  - Automatic logging of mistakes and new phrases.
- Track progress:
  - How many minutes I actually speak.
  - How many new words/phrases I learn.
- Make the project **deployable**:
  - Local app.
  - Optional Hugging Face Space as a public demo.

---

## 🧱 Project Structure

```text
es-ai-immersion-lab/
├── README.md
├── app.py                      # Gradio UI: chat + stats view
├── requirements.txt
├── config/
│   ├── model-config.yaml       # model + prompt settings
│   └── app-settings.yaml       # host/port, paths, language level, etc.
├── data/
│   ├── logs/
│   │   ├── sessions/           # raw JSON for each conversation session
│   │   └── summaries/          # daily/weekly summaries
│   ├── vocab/
│   │   ├── known_words.txt     # running list of "I already know these"
│   │   ├── new_words.csv       # extracted unknown words with context
│   │   └── anki_export.csv     # ready for import into Anki
│   └── prompts/
│       └── conversation-topics.md  # seed topics in Spanish (tech, travel, etc.)
├── src/
│   ├── es_ai_immersion_lab/
│   │   ├── __init__.py
│   │   ├── tutor.py            # main chat logic (Spanish-only, correction mode)
│   │   ├── logger.py           # save session logs + metadata
│   │   ├── analyzer.py         # parse logs, extract mistakes + new vocab
│   │   ├── vocab_builder.py    # build vocab lists + Anki CSV
│   │   └── prompts.py          # system/user prompt templates (A2/B1/B2 modes)
│   └── run_analysis.py         # CLI: reprocess logs, regenerate vocab/Anki
├── hf-space/
│   └── README-space.md         # Hugging Face-specific instructions
├── docs/
│   ├── learning-plan.md        # my Spanish learning plan + how this tool fits
│   ├── usage.md                # how to use the app day-to-day
│   └── screenshots/
│       ├── chat-session.png
│       └── vocab-stats.png
└── tests/
    ├── test_analyzer.py
    ├── test_vocab_builder.py
    └── test_logger.py