# Charms of David - Learning Project

A song search engine for Christian songs. Learn web development by building something real.

![Landing Page](plan/01-frontend/01-landing-page.png)

## Before You Start

### 1. Set up Claude for beginner-friendly help

Claude can explain concepts as you build. Set up a custom style for better answers:

1. Go to [claude.ai](https://claude.ai/)
2. Click the Settings icon (bottom left)
3. Select **Use Style** → **Create & Edit Styles** → **Create Custom Style**
4. Name it "Beginner's Guide"
5. Paste this in the style box:

```
Write for a coding beginner with patience and clarity. Treat the user as a beginner by default. Start every explanation with a 1-3 sentence overview before introducing any technical terms. Use short, clear, imperative sentences and prefer bullet points over long paragraphs. Avoid jargon entirely unless the user explicitly asks to 'explain deeper'—if you must use technical terms, define them briefly. Use intuitive analogies and relatable comparisons sparingly, only when they genuinely clarify a concept; skip analogies if they don't add real understanding. Present one idea at a time, never overwhelming with multiple approaches or new libraries. Build concepts incrementally, layer by layer, ensuring each foundational piece is fully understood before introducing the next. Frequently check understanding by asking if the user follows along before moving forward. When providing code, keep it simple and explicit with brief 'why' comments that explain the reasoning behind each line rather than just what it does. Include code examples and small ASCII diagrams or timelines when helpful to clarify concepts. Break complex tasks into small, manageable steps that build confidence and reinforce prior learning. Only add deeper technical detail when the user explicitly asks for it. Maintain an encouraging, supportive tone that celebrates small wins and normalizes confusion as part of learning. Eliminate unnecessary headings, labels, and extra sections—every word should serve a purpose.
```

6. Click **Save**
7. Select "Beginner's Guide" from the style dropdown when you need help

### 2. Understand the 🤔 Ask Claude links

Throughout the tutorials, you'll see links like: [🤔 What is TailwindCSS?](https://claude.ai/new?q=...)

These open Claude with a pre-written question designed to give you clear explanations. Click them whenever you want to
understand something better.

## Setup

### Install Tools

**uv** (Python package manager):

- macOS/Linux: `curl -LsSf https://astral.sh/uv/install.sh | sh`
- Windows: `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`
- Verify: `uv --version`
- [🤔 What is uv and why use it?](https://claude.ai/new?q=I%27m%20learning%20Python%20web%20development.%20What%20is%20uv%20and%20why%20would%20I%20use%20it%20instead%20of%20pip%3F%20Explain%20simply%20for%20a%20beginner.)

**Git**:

- Download from [git-scm.com/downloads](https://git-scm.com/downloads)
- [🤔 What is Git and why do I need it?](https://claude.ai/new?q=I%27m%20learning%20web%20development.%20What%20is%20Git%20and%20why%20do%20I%20need%20it%3F%20Explain%20simply%20for%20a%20beginner.)

**PyCharm Community** (recommended):

- Download: [jetbrains.com/pycharm/download](https://www.jetbrains.com/pycharm/download/)
- [🤔 What is PyCharm?](https://claude.ai/new?q=I%27m%20learning%20Python.%20What%20is%20PyCharm%20and%20why%20would%20I%20use%20it%20instead%20of%20a%20simple%20text%20editor%3F%20Explain%20simply.)

**New to command line?
** [🤔 How do I use the terminal?](https://claude.ai/new?q=I%27m%20new%20to%20programming.%20What%20is%20the%20command%20line%2Fterminal%20and%20how%20do%20I%20use%20it%3F%20Explain%20the%20basics%20for%20a%20beginner.)

### Get the Project

```bash
git clone https://github.com/AMiCUS-dev/charms-of-david.git
cd charms-of-david
```

[🤔 What does this command do?](https://claude.ai/new?q=I%27m%20learning%20Git.%20What%20does%20%27git%20clone%27%20do%3F%20And%20what%20does%20%27cd%27%20mean%3F%20Explain%20simply.)

## How to Work

### Stage 1: Frontend (HTML + TailwindCSS)

1. Open `plan/01-frontend/01-landing-page.md`
2. Follow the instructions
3. Build the page in `app/templates/`
4. Test: Right-click HTML file → Open in Browser

Save your work:

```bash
git add .
git commit -m "Complete: Landing page"
git push
```

[🤔 What do these git commands do?](https://claude.ai/new?q=I%27m%20learning%20Git.%20What%20do%20%27git%20add%27%2C%20%27git%20commit%27%2C%20and%20%27git%20push%27%20do%3F%20Explain%20each%20command%20simply.)

### Stage 2: Backend (Python + Database)

Setup once:

```bash
uv init
uv add fastapi uvicorn jinja2 python-multipart
```

Run the server:

```bash
uv run uvicorn app.main:app --reload
```

[🤔 What does uvicorn do?](https://claude.ai/new?q=I%27m%20learning%20FastAPI.%20What%20is%20uvicorn%20and%20what%20does%20it%20do%3F%20Why%20do%20I%20need%20it%3F%20Explain%20simply.)

Open [localhost:8000](http://localhost:8000) in your browser.

[🤔 What is localhost:8000?](https://claude.ai/new?q=I%27m%20learning%20web%20development.%20What%20does%20localhost%3A8000%20mean%3F%20Explain%20simply%20for%20a%20beginner.)

## Getting Help

**Stuck?** Ask Claude with this format:

- What you're trying to do
- What you tried
- The exact error message

**Example:**
> "I'm trying to make the search bar rounded, but `rounded-lg` isn't working. I added it to the `<input>` tag. The
> browser shows no errors."

## Project Structure

```
charms-of-david/
└── app/
    ├── templates/  # Your HTML files
    ├── static/     # CSS, images
    └── main.py     # Python code
```

---

## Important: TailwindCSS v4

This project uses **TailwindCSS v4**. When searching for help or asking AI, always specify **v4** in your questions.

**Key difference from v3:**

- v3: `bg-gradient-to-b` ❌
- v4: `bg-linear-to-b` ✅

---

**Go slow. Understanding beats speed.**