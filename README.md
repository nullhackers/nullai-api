# NullAI API

REST API for the [NullAI](https://github.com/nullhackers/nullai) AI tools directory. Built with [JSON Server](https://github.com/typicode/json-server).

**Live:** [nullaidb.onrender.com](https://nullaidb.onrender.com)

## Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/tools` | Returns all AI tools |
| `GET` | `/tools/:id` | Returns a single tool by ID |
| `GET` | `/categories` | Returns all categories |
| `GET` | `/categories/:id` | Returns a single category by ID |

## Tool Schema

```json
{
  "id": "unique-slug",
  "name": "Tool Name",
  "website": "https://example.com/",
  "category": "AI Videos",
  "description": "Short description of the tool.",
  "access": {
    "loginRequired": true,
    "loginMethod": "Google",
    "credits": "400 credits/month"
  },
  "generation": {
    "type": ["Video", "Image"],
    "durations": ["5s", "8s", "12s"],
    "resolution": "1080p",
    "aspectRatio": "9:16"
  },
  "features": ["Feature 1", "Feature 2"],
  "notes": "Optional additional information.",
  "lastUpdated": "2026-09-26"
}
```

**Optional fields** — Set to `null` or omit if not applicable: `loginMethod`, `credits`, `resolution`, `aspectRatio`, `notes`. Use an empty array `[]` for `features` if the tool has none.

## Category Schema

```json
{
  "id": "ai-videos",
  "name": "AI Videos"
}
```

## Current Categories

- AI Videos
- AI Images
- Coding
- AI Audio
- AI Writing
- AI Productivity
- AI Design
- Other

## Adding a New Tool

Add a new object to the `tools` array in `db.json`:

```json
{
  "id": "new-tool-slug",
  "name": "New Tool",
  "website": "https://newtool.com/",
  "category": "AI Images",
  "description": "AI image generation tool.",
  "access": {
    "loginRequired": false,
    "loginMethod": null,
    "credits": null
  },
  "generation": {
    "type": ["Image"],
    "durations": null,
    "resolution": null,
    "aspectRatio": null
  },
  "features": ["Text to Image"],
  "notes": null,
  "lastUpdated": "2026-09-26"
}
```

The frontend will automatically display the new tool — no frontend code changes needed.

## Adding a New Category

Add a new object to the `categories` array in `db.json`:

```json
{
  "id": "ai-3d",
  "name": "AI 3D"
}
```

The frontend will automatically display the new category filter — no frontend code changes needed.

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18+)
- npm

### Installation

```bash
git clone https://github.com/nullhackers/nullai-api.git
cd nullai-api
npm install
```

### Run Locally

```bash
npm start
```

The API runs on [http://localhost:5001](http://localhost:5001) by default. Set the `PORT` environment variable to use a different port.

## Deployment

This API is deployed on [Render](https://render.com/). Push changes to the `main` branch to trigger a redeploy.

## Contact

- Twitter: [@nullhackers](https://twitter.com/nullhackers)
