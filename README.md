# Project 1 - Build Your Personal Website

**CSCI 498E / 598E - Coding with AI Agents**

| | |
|---|---|
| **Weight** | 20% of your final grade |
| **Released** | Thursday, September 3 |
| **Due** | Tuesday, September 22 |
| **Work** | Individual |

You hand in five things:

1. A **live website** on a public GitHub Pages URL
2. **`DECISIONS.md`** - your decision log
3. **`verification/`** - proof the site actually works
4. A **3-5 minute video**, submitted on Canvas
5. **Comments on two classmates' sites**, in the Canvas discussion

---

## What you are building

A personal website, built by driving Claude Code, live on the public internet.

**There are no required sections.**
No required framework, no required page count, no required look.
A one-page site is fine. A twelve-page site is fine.
Put your research on it, your music, your climbing photos, your resume, or something nobody has thought of.
It is your site and it should look like it belongs to you and not to a template.

## What this project is actually about

Not the website.

You will be graded on your **judgment and your process**, not on how the page looks.
Nobody is scoring your CSS.
A plain, honest, working site with a sharp decision log is worth more here than a beautiful one you cannot explain.

There is no rubric and no list of required features.
What I want out of this project is simple: a personal website you are proud to show the world.

The habit this project is building is the one from Lecture 3: **never trust an agent result you have not given it a way to check.**
Your agent will tell you it deployed successfully. That claim is worth nothing until you look at the live URL yourself.

## Start here

1. Click **Use this template** at the top of this repo, then **Create a new repository**.
2. **Name it `<your-github-username>.github.io`.** Read the next section before you skip this.
3. Make it **Public**. GitHub Pages needs a public repo on a free account.
4. Clone it, open the folder, and start Claude Code:
   ```bash
   git clone https://github.com/<your-username>/<your-username>.github.io.git
   cd <your-username>.github.io
   claude
   ```
5. Turn on Pages: **Settings > Pages > Build and deployment > Source > Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
6. Wait a minute, then open `https://<your-username>.github.io` and confirm you see "Hello, world."

Once that page is live, you have a working deploy pipeline and everything after it is just changing files.
Get to this point on day one, before you have any idea what you want to build.

### Why the repo name matters

If you name your repo anything else, your site lives at `https://<username>.github.io/<repo-name>/` instead of at the root.

That sounds harmless. It is the single most common way this project breaks.
Any link written as `/style.css` will look for the file at `<username>.github.io/style.css`, which does not exist, and your site will deploy successfully and render as an unstyled wall of text.

Naming the repo `<your-username>.github.io` puts your site at the root and this whole class of bug never happens.
You also end up with a URL you will actually want to put on a resume.

## How to build it

**Plain HTML and CSS is the recommended path**, and it is what this template gives you.
Nothing to install, nothing to build, and the deploy is instant.

You may use anything you want as long as it reaches a live Pages URL.
Two honest warnings from experience: **Hugo** and **Next.js static export** are the two most likely to consume your three weeks on toolchain problems rather than on your site.
If you want a Markdown blog, GitHub Pages runs **Jekyll** natively without you installing anything, which is the smoothest of the framework options.

Preview locally before you push:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

`RESOURCES.md` has design guidance, accessibility basics, real personal sites worth studying, and a section on getting genuinely good design work out of Claude.
Read that one before you start choosing fonts.

## Your decision log

`DECISIONS.md` is already in this repo with five questions in it.

Answer them as you go, not the night before it is due.
This is your methods section: what you chose, what you rejected, and how you know it works.
Specifics beat polish. A short honest answer is worth more than a long vague one.

Question 3 asks about a time you overruled the agent.
That question is the heart of this project, so do not let the agent answer it for you.

## Proving it works

Make a `verification/` folder containing exactly three things:

```
verification/
  screenshot.png     your live site in a browser, with the URL bar visible
  fetch.txt          the response from fetching your live URL
  README.md          three lines (below)
```

`verification/README.md`:

```
URL checked: https://<your-username>.github.io
When: 2026-09-21 14:32
What would have made this fail: <one sentence>
```

The URL bar has to be visible in the screenshot.
A screenshot of `localhost` proves your laptop works, which is not the claim you are making.

That last line is the one that matters.
"It would have failed if the site was broken" is not a real answer.
"It would have 404'd if I had left index.html inside a subfolder" is.

You already did this exact check in the Lecture 3 lab. This is the same motion.

## The video

Record 3-5 minutes and submit it on Canvas. Any tool, any quality, phone camera is fine.

Three things to cover:

1. Introduce your site: open the live URL and give a short tour of what you built.
2. Explain your design choices: what you picked, what you rejected, and why it looks the way it does.
3. Describe a challenge or an issue you hit, and how you got past it.

Here is why the video exists.
Everything else in this project was built by driving an AI, and that is the point of the course.
The video is the one deliverable an agent cannot make for you: your voice, your reasons, your story.
That human side matters more, not less, when the code came from a model.

## Reviewing each other's sites

A personal site is made to be seen, and this class is your first real audience.

There is a discussion for P1 on Canvas.
Visit two classmates' sites and leave each of them a comment: one specific thing that works, and one thing you would try differently.
"Nice site" helps nobody, so point at something real.

## Ground rules

- **Using Claude Code is the point**, not something you need to disclose or apologize for. This is a course about driving agents well.
- **Your repo is public.** So is every commit in its history. Do not commit API keys, your home address, your phone number, unpublished work, or other people's photos without permission. A secret you delete in a later commit is still readable.
- **Late work** loses 20%, and nothing is accepted more than one week late.
- Canvas is the system of record for the deadline. If Canvas and this file ever disagree, Canvas wins, and please tell me so I can fix it.

## When it breaks

Three things account for most of the pain, and all three produce a *successful* deploy with a broken page.

- **Blank or unstyled page.** Almost always a path problem. Use relative paths (`style.css`, not `/style.css`). Check the browser console for red 404s.
- **"I pushed and nothing changed."** GitHub caches for up to 10 minutes. Try an incognito window before you conclude anything is wrong. If `curl` shows the new content and your browser does not, it is your browser.
- **Files vanishing from the live site.** Anything starting with `_` gets stripped unless a `.nojekyll` file exists at the repo root. This template ships one. Do not delete it.

Still stuck after 20 minutes? Office hours are Tue/Thu 9-10 am and 2-3 pm, CTLM 246L.
Bring the actual error, not a description of it.
