# Jimi's Jobs Board - Setup Guide

## Quick Start

### 1. Install Claude Code
```bash
npm install -g @anthropic-ai/claude-code
```

### 2. Clone this repo
```bash
git clone https://github.com/StephgAHP/3d-motion-jobs
cd 3d-motion-jobs
```

### 3. Set up git identity
```bash
git config user.email "jimi@jimirichardson.com"
git config user.name "Jimi Richardson"
```

### 4. Install Vercel CLI (for deployments)
```bash
npm install -g vercel
vercel login
```

### 5. Link Vercel to the project
```bash
vercel link
```
Select the existing project when prompted.

### 6. Start Claude Code
```bash
claude
```

Claude Code will automatically read the CLAUDE.md file and understand the entire project.

## Things You Can Ask Claude Code

**Update jobs:**
- "Search for new 3D motion designer remote roles and update the board"
- "Remove any closed listings from the top picks"
- "Add this role to the top picks: [paste job URL]"

**Update pitches:**
- "Write a tailored pitch for [company name] and add it to apply.html"
- "Update my bio to include [new client/project]"

**Customise the site:**
- "Change the hero subtitle"
- "Add a new section for [whatever]"
- "Make the job cards wider on desktop"

**Deploy:**
- "Commit and push these changes"
(Vercel auto-deploys from master)

**Set up weekly auto-refresh:**
- "/schedule create a weekly agent that refreshes the job listings every Monday"

## File Structure
```
index.html        - Main jobs board
apply.html        - Pitches, outreach templates, tracker
gmail-setup.html  - Gmail CRM setup instructions
vercel.json       - Vercel config (noindex headers)
CLAUDE.md         - Context for Claude Code (read automatically)
README.md         - This file
```

## Live Site
https://3d-jobs-board.vercel.app
