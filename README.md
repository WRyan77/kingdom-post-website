# Kingdom Post

A minimal blog platform for [kingdompost.news](https://kingdompost.news).

## Pages

| URL | Description |
|-----|-------------|
| `/` | Blog reader — displays posts with sidebar navigation |
| `/editor` | Markdown editor — paste formatted text, convert, and save to GitHub |
| `/app` | Redirect to the Kingdom Post iPhone app |

## Blog Editor Setup

The editor at `/editor` lets you paste formatted text (from Google Docs, Word, a webpage, etc.), converts it to clean markdown, and commits it directly to this repo via the GitHub API.

### 1. Create a GitHub Personal Access Token

1. Go to **GitHub > Settings > Developer settings > Personal access tokens > Tokens (classic)**
2. Click **Generate new token (classic)**
3. Give it a name like "Kingdom Post Editor"
4. Select the **`repo`** scope (full control of private repositories)
5. Click **Generate token** and copy it

### 2. Configure the Editor

1. Open the editor page (`kingdompost.news/editor`)
2. Click the **gear icon** in the top right
3. Fill in:
   - **Personal Access Token**: paste the token from step 1
   - **Repository**: `WRyan77/kingdom-post`
   - **Branch**: `main`
   - **Blog Directory**: `blog`
4. Click **Save Settings**

Settings are stored in your browser's localStorage — they never leave your machine.

### 3. Using the Editor

1. **Paste** formatted text into the editor (Ctrl/Cmd+V)
2. Click **Markdown** to see the converted markdown and make edits
3. Click **Preview** to switch back to the formatted view
4. Enter a **filename** (e.g. `my-new-post.md`)
5. Click **Save to GitHub** to commit the file to the blog directory

### How Authentication Stays Private

The editor page is public, but saving requires a GitHub Personal Access Token that only you possess. The token is stored exclusively in your browser's localStorage — it is never embedded in the source code, sent to any server, or accessible to other visitors. Without the token, the "Save to GitHub" button does nothing.

## Adding Blog Posts

Each blog post is a markdown file in `blog/` with YAML frontmatter:

```yaml
---
title: "Your Post Title"
author: "Author Name"
date: "YYYY-MM-DD"
image: "url-or-path-to-thumbnail"
---

# Your Post Title

Content here...
```

After adding a new file, add a corresponding entry to `blogs.json` so it appears on the main page.
