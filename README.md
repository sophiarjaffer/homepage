# Sophia Jaffer — Personal Site
## How to edit and publish your site (no coding experience needed)

This guide walks you through everything from scratch. Take it one section at a time.

Some steps below are **one-time only** — you do them once when setting up a new computer, then never again. Others are **ongoing** — things you do every time you want to add or change something. Each section is clearly labelled.

---

## Part 0 — One-time computer setup *(do this once, on each new computer)*

Before you can work on your site, four free tools need to be installed, and the site files need to be downloaded to your computer. Do these steps in order — each one builds on the previous.

### 0a — Install Visual Studio Code

**Visual Studio Code** (VS Code) is a free app where you will do all your editing. Think of it like a very powerful Notepad or Word, built for working with website files.

1. Go to [https://code.visualstudio.com](https://code.visualstudio.com)
2. Click the big blue **Download** button — it will detect your system automatically
3. Open the downloaded file and follow the installer (click Next → Next → Install)
4. Open VS Code once the installation is done

### 0b — Install Git

**Git** is the tool that tracks your changes and communicates with GitHub. VS Code uses it behind the scenes — you do not type Git commands directly, but it needs to be installed.

1. Go to [https://git-scm.com/downloads](https://git-scm.com/downloads) and click the download for your system
2. Run the installer — click **Next** all the way through, keeping all the default settings
3. When it finishes, you do not need to open anything — Git works quietly in the background

### 0c — Install Quarto

**Quarto** is the tool that turns your writing files (`.qmd`) into a proper website. Without it, you cannot preview or publish your site.

1. Go to [https://quarto.org/docs/get-started/](https://quarto.org/docs/get-started/)
2. Click the download button for your system and run the installer
3. Keep all the default settings and click through to finish

### 0d — Install GitHub Copilot and sign in to GitHub

**GitHub Copilot** is an AI assistant built into VS Code. It can answer your questions, help you write, and explain things — all without leaving the app. You will also sign in to GitHub here so VS Code can communicate with it.

1. In VS Code, click the **Extensions** icon in the left sidebar (it looks like four squares)
2. In the search box, type: `GitHub Copilot`
3. Click **Install** on the first result (published by GitHub)
4. A prompt will appear asking you to sign in to GitHub — click **Sign in**
   - If you do not have a GitHub account, go to [https://github.com](https://github.com) and create a free one first
5. A browser window will open — log in to GitHub and click **Authorise Visual Studio Code**
6. Switch back to VS Code — you are now signed in

> **Tip:** To use Copilot, click the speech bubble icon in the left sidebar and ask it anything in plain English — for example: *"How do I add a new post to the music section?"*

### 0e — Clone the repository

**Cloning** means downloading a full copy of your website from GitHub onto your computer, with an automatic connection so you can push changes back up later. You only do this once per computer.

1. In VS Code, press `Ctrl + Shift + P` to open the command palette (a search bar appears at the top)
2. Type `Git: Clone` and press Enter
3. Paste the following URL and press Enter:
   ```
   https://github.com/sophiarjaffer/homepage
   ```
4. A window will ask you to choose a folder — this is where the files will be saved. Pick somewhere easy to find, like your Documents folder
5. Click **Select as Repository Destination**
6. VS Code will ask "Would you like to open the cloned repository?" — click **Open**

Your site files are now on your computer and linked to GitHub. You are ready to work.

---

## Part 1 — Understanding local and remote (the key concept)

Your website files live in **two places** at the same time:

| Place | What it is |
|---|---|
| **Local** | The copy on your computer |
| **Remote (GitHub)** | The copy stored online at github.com |

When you edit files in VS Code, you are editing your **local** copy. To make those changes appear on your website, you need to send them up to GitHub.

The key words:

- **Commit** = putting your changes into an envelope with a label describing what you changed
- **Push** = sending that envelope to GitHub
- **Pull** = bringing the latest version from GitHub down to your computer

You always edit **locally**, then **push** to make changes live.

---

## Part 2 — How to edit a post

Your posts are files that end in `.qmd`. They are plain text files — you write in them just like you would in a notes app, using a simple format called Markdown.

### Find the file you want to edit

In the left panel of VS Code, navigate to a section folder:

```
nature/
  posts/
    2025-01-01-the-january-garden.qmd   ← click this to open it
```

### The structure of a post

Every post has two parts:

```
---
title: "The January Garden"
description: "A short description of your post."
author: "Sophia Jaffer"
date: "2025-01-01"
categories:
  - Seasons
---

Your writing goes here.

## A heading

More writing under the heading.
```

The section between the `---` lines at the top is the **header** — it controls the title, date, and category shown in the listing. Everything below is your actual text.

### Basic formatting (Markdown)

| What you type | What it looks like |
|---|---|
| `**bold text**` | **bold text** |
| `*italic text*` | *italic text* |
| `## Heading` | A large heading |
| `### Smaller heading` | A smaller heading |
| A blank line | A new paragraph |

### Add a cover image to your post

To show a thumbnail image in the listing grid, add an `image:` line to the header:

```
---
title: "My Post"
author: "Sophia Jaffer"
date: "2025-02-01"
image: "https://your-image-url.jpg"
---
```

### Add a new post

1. Inside the relevant section folder (e.g. `nature/posts/`), create a new file
2. Name it with today's date and a short title, e.g. `2025-06-06-morning-walk.qmd`
3. Copy the header block from an existing post and update the title, date, and description
4. Write your text below the second `---`

---

## Part 3 — Preview your site locally

Before pushing your changes online, you can preview the site on your own computer:

1. In VS Code, go to **Terminal → New Terminal** (a black panel will open at the bottom)
2. Type the following and press Enter:

```
quarto preview
```

3. A browser tab will open showing your site — it updates live as you edit files
4. When you are done previewing, press `Ctrl + C` in the terminal to stop it

---

## Part 4 — Push your changes to GitHub *(ongoing)*

Once you are happy with your edits, you need to push them. This is a three-step process: **Stage → Commit → Push**.

1. Click the **Source Control** icon in the left sidebar (it looks like a branching diagram)
2. You will see a list of files you have changed
3. Hover over each file and click the **+** button to **stage** it (this is like putting it in the envelope)
4. In the **Message** box at the top, type a short description of what you changed
   - Example: `Add new nature post about morning walk`
5. Click the **Commit** button (the blue tick/checkmark)
6. Click the **Sync Changes** button that appears (or the cloud icon with an arrow) to **push**

Your changes are now on GitHub. The site will update within a couple of minutes.

---

## Part 5 — Publish your site as a live website *(do this once)*

This step turns your GitHub repository into a real public URL that anyone can visit. It only needs to be done once.

### Step 1 — Run the publish command

1. In VS Code, go to **Terminal → New Terminal**
2. Type the following and press Enter:

```
quarto publish gh-pages
```

3. Quarto will ask:

   > Publish site to `https://sophiarjaffer.github.io/homepage/` using gh-pages? (Y/n)

   Press Enter to confirm

4. Quarto builds your site and uploads it to GitHub. This takes a minute or two — wait for a success message in the terminal

### Step 2 — Enable GitHub Pages

1. Open a browser and go to:
   [https://github.com/sophiarjaffer/homepage/settings/pages](https://github.com/sophiarjaffer/homepage/settings/pages)
   *(log in to GitHub if prompted)*

2. Under **Source**, select **Deploy from a branch**

3. Under **Branch**, choose `gh-pages`, keep the folder as `/ (root)`, and click **Save**

4. Wait two to three minutes, then visit:
   **[https://sophiarjaffer.github.io/homepage/](https://sophiarjaffer.github.io/homepage/)**

Your site is live.

### After the first time

Once this is set up, normal edits do **not** need `quarto publish gh-pages` again. Just edit, then Stage → Commit → Push (Part 4). GitHub updates the site automatically.

---

## Quick reference

| Task | How |
|---|---|
| Set up on a new computer *(once)* | Install VS Code, Git, Quarto → clone repo via `Ctrl+Shift+P` → Git: Clone |
| Publish site for the first time *(once)* | Terminal → `quarto publish gh-pages` → enable Pages in GitHub Settings |
| Edit a post | Open the `.qmd` file in VS Code, edit the text, save |
| Add a new post | Create a new `.qmd` file in the right `posts/` folder |
| Preview locally | Terminal → `quarto preview` |
| Publish changes | Source Control → Stage → Commit → Sync |
| Ask for help | GitHub Copilot chat → ask in plain English |

---

## Need help?

Open the GitHub Copilot chat in VS Code (speech bubble icon in the left sidebar) and ask in plain English. For example:

- *"How do I add a new post to the music section?"*
- *"What does this error message mean?"*
- *"How do I add a link in Markdown?"*
