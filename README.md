# Speedr - Speed Reading App

A fast, efficient speed reading app using RSVP (Rapid Serial Visual Presentation) technique with ORP (Optimal Recognition Point) highlighting.

## Features
- Upload PDF, DOCX, or TXT files
- Adjustable reading speed (100-1000 WPM)
- Automatic pause after sentences
- Clean, minimal interface
- Keyboard shortcuts (Space, Arrow keys, R)

## Deploy to Netlify

### Option 1: Drag & Drop
1. Go to [Netlify](https://app.netlify.com)
2. Drag the entire `speedr-deploy` folder onto the Netlify dashboard
3. Done! Your site is live

### Option 2: CLI
```bash
npm install -g netlify-cli
cd speedr-deploy
netlify deploy --prod
```

### Option 3: Git
1. Push this folder to a GitHub repo
2. Connect the repo in Netlify dashboard
3. Deploy automatically on push

## Files Included
- `index.html` - Main application
- `netlify.toml` - Netlify configuration
- `README.md` - This file

## Usage
1. Upload a document (PDF, DOCX, or TXT)
2. Adjust WPM speed to your preference
3. Press Play or hit Spacebar
4. Read at superhuman speeds!

## Keyboard Shortcuts
- **Space** - Play/Pause
- **Left Arrow** - Previous word
- **Right Arrow** - Next word
- **R** - Restart

Built with vanilla JavaScript, PDF.js, and Mammoth.js
