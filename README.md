# Solve with Love 💜

A single-page "solve the puzzle to reveal a love message" site — like the one in your video.

## Files
- `index.html` — everything (HTML + CSS + JS) in one file. No build step, no backend, no MCP server needed.

## How to customize
Open `index.html`, find the `CONFIG` block near the top of the `<script>` tag, and edit:

```js
const CONFIG = {
  recipientName: "Laddu",
  puzzleImage: "https://your-image-url.com/photo.jpg",
  message: "Your custom message here...",
  revealImage: "https://your-image-url.com/photo2.jpg",
  gridSize: 3,

  question: "Will you forever be mine?",
  questionHint: "You can't escape love! 💘",
  yesText: "Yes 💖",
  noText: "No 🙈",

  celebrateTitle: "It's a date then!",
  celebrateSubtitle: "Knew you'd say yes 😏",
  celebrateGif: "https://media.giphy.com/media/3o7TKSjRrfIPjeiVyM/giphy.gif",
  instagramUrl: "https://www.instagram.com/your_username"
};
```

### The 3 screens
1. **Puzzle** — visitor swaps tiles to solve a photo, just like the original.
2. **Reveal** — your custom message + photo appears with confetti. A "One more thing →" button leads to the question.
3. **Question** — "Will you forever be mine?" with a dodging "No" button (it jumps to a random spot in the box whenever you hover/tap it, so it can never actually be clicked) and a "Yes" button that grows larger as "No" gets dodged. Clicking "Yes" leads to the final celebration screen with a GIF, "Play Again", and a "Follow me on Instagram" button.

- `puzzleImage`: the photo that gets cut into a 3x3 (or NxN) sliding puzzle.
- `revealImage`: the photo shown after the puzzle is solved.
- `celebrateGif`: any GIF URL (Giphy/Tenor share links work — use the direct .gif URL).
- `instagramUrl`: your Instagram profile link — the "Follow me on Instagram" button on the final screen opens this in a new tab.
- Use a **square** image for `puzzleImage` so tiles line up cleanly.
- You can use any public image URL, or upload your own photos to the repo (see below) and reference them as relative paths like `images/photo.jpg`.

To use your own photos instead of URLs:
1. Create an `images/` folder in your repo.
2. Add `couple.jpg`, `mountains.jpg`, etc.
3. Set `puzzleImage: "images/couple.jpg"` in the config.

## Hosting it for free (GitHub Pages)

1. Create a new GitHub repo (or use your existing one).
2. Add `index.html` (and an `images/` folder if you have local photos) to the repo root.
3. Push to GitHub:
   ```bash
   git add .
   git commit -m "Add puzzle site"
   git push
   ```
4. On GitHub: go to **Settings → Pages**.
5. Under "Build and deployment", set **Source** to "Deploy from a branch".
6. Pick branch `main` and folder `/ (root)`, then Save.
7. Wait ~1 minute. Your site will be live at:
   `https://<your-username>.github.io/<repo-name>/`

That's it — no server, no hosting fees, no MCP server required.

## About the "MCP server" request

MCP (Model Context Protocol) servers let AI assistants call tools or read data from external systems — they're for connecting AI models to things like databases, APIs, or apps. A static personalized webpage like this doesn't need one; it's just HTML/CSS/JS that runs entirely in the visitor's browser. If you had something specific in mind for an MCP server (e.g., having an AI assistant generate new puzzle pages on demand), let me know and I can help with that separately.
