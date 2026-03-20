# 3DCraftum Waitlist Page

A dark-mode waitlist landing page for 3DCraftum — a micro-SaaS that generates SEO-optimized Etsy listings from 3D model metadata.

## Quick Start (Local)

```bash
cd 3dcraftum-waitlist
# Open directly in browser
open index.html
# Or serve with any static server
npx serve .
```

## Features

- **Live Demo**: Enter model name, material, print time, and dimensions to generate a sample Etsy listing (title, description, tags)
- **Email Collection**: Built-in waitlist form ready for Formspree integration
- **Dark Mode**: Professional design matching the Mission Control aesthetic
- **Responsive**: Works on mobile and desktop

## Deployment Options

### Option 1: Vercel (Recommended)

```bash
# Install Vercel CLI if needed
npm i -g vercel

# Deploy
cd 3dcraftum-waitlist
vercel --prod
```

### Option 2: Netlify (Drag & Drop)

1. Go to [netlify.com](https://netlify.com)
2. Drag the `3dcraftum-waitlist` folder onto the drop zone
3. Done!

### Option 3: Cloudflare Pages

1. Go to [pages.dev](https://pages.dev)
2. Connect your GitHub or drag & drop the folder

### Option 4: GitHub Pages

```bash
cd 3dcraftum-waitlist
git init
git add .
git commit -m "Add 3DCraftum waitlist page"
# Push to GitHub, then enable Pages in settings
```

## Email Collection Setup

### Option A: Formspree (Recommended)

1. Sign up at [formspree.io](https://formspree.io)
2. Create a form and get your form ID
3. In `index.html`, find this line and replace `YOUR_FORM_ID`:

```javascript
const formspreeEndpoint = 'https://formspree.io/f/YOUR_FORM_ID';
```

4. Uncomment the fetch call in the waitlist form handler

### Option B: Web3 Forms (Free, no account)

1. Get your access key at [web3forms.com](https://web3forms.com)
2. Update the form action in the HTML

### Option C: Custom Backend

Replace the fetch call in the script with your own API endpoint:

```javascript
await fetch('YOUR_API_ENDPOINT', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ email })
});
```

## Customization

- **Waitlist count**: Change `247` in the HTML and JS sections
- **Accent color**: Edit `--accent` in the CSS (default: `#f97316` orange)
- **Demo inputs**: Modify the form fields in the demo section as needed
- **Tag generation**: Adjust the `generateTags()` function in the script

## Files

```
3dcraftum-waitlist/
├── README.md    # This file
└── index.html   # Complete waitlist page with embedded CSS + JS
```

## How It Works

1. **Demo Section**: Users can enter their 3D model details and click "Generate Listing" to see a sample output
2. **Listing Generation**: The JavaScript adapts the logic from `generate_listing.py` to create SEO-optimized titles (≤140 chars), descriptions (≤950 chars), and 13 relevant tags
3. **Waitlist CTA**: Email collection form with social proof (animated counter)

---

**Tech**: Single HTML file with embedded CSS + vanilla JS. No build step required. ~21KB total.