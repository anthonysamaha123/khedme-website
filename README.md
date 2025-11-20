# KHEDME Marketing Website

A production-ready single-page marketing website for KHEDME, Lebanon's platform for organizing everyday home services.

## Overview

This is a static, single-page website built with pure HTML, TailwindCSS (via CDN), and vanilla JavaScript. All graphics are inline SVG, making it completely self-contained with no external image dependencies.

## Features

- **9 Complete Sections**: Hero, Today vs KHEDME, How It Works, Categories, Why KHEDME, Testimonials, Movement, Final CTA, and Footer
- **Responsive Design**: Mobile-first approach that works beautifully on all devices
- **Smooth Animations**: GSAP-powered scroll animations and micro-interactions
- **Conversion-Focused**: Expert copywriting designed to drive app downloads
- **Zero Build Tools**: Pure HTML/CSS/JS - no build process required
- **CDN-Based**: All dependencies loaded via CDN (TailwindCSS, GSAP, Google Fonts)

## File Structure

```
khedme-website/
├── index.html          # Main HTML file with all content
├── README.md           # This file
├── .gitignore          # Git ignore rules
└── .nojekyll           # Prevents Jekyll processing on GitHub Pages
```

## Local Development

Simply open `index.html` in your web browser. No server or build process required.

For a better development experience, you can use a local server:

```bash
# Using Python 3
python3 -m http.server 8000

# Using Node.js (if you have http-server installed)
npx http-server

# Using PHP
php -S localhost:8000
```

Then visit `http://localhost:8000` in your browser.

## Deployment to GitHub Pages

### Step 1: Create GitHub Repository

1. Go to [GitHub](https://github.com) and create a new repository
2. Name it `khedme-website` (or any name you prefer)
3. Do NOT initialize with README, .gitignore, or license (we already have these)

### Step 2: Push Your Code

```bash
# Navigate to the website folder
cd /Users/anthonysamaha/Desktop/khedme-website

# Initialize git (if not already done)
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: KHEDME marketing website"

# Add your GitHub repository as remote (replace YOUR_USERNAME with your GitHub username)
git remote add origin https://github.com/YOUR_USERNAME/khedme-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on **Settings**
3. Scroll down to **Pages** in the left sidebar
4. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**

Your site will be available at: `https://YOUR_USERNAME.github.io/khedme-website/`

## Setting Up Custom Domain (khedme.org)

### Step 1: Configure DNS

In your domain registrar (where you bought khedme.org), add the following DNS records:

**Option A: Using A Records (Recommended)**
```
Type: A
Name: @
Value: 185.199.108.153
TTL: 3600

Type: A
Name: @
Value: 185.199.109.153
TTL: 3600

Type: A
Name: @
Value: 185.199.110.153
TTL: 3600

Type: A
Name: @
Value: 185.199.111.153
TTL: 3600
```

**Option B: Using CNAME (Alternative)**
```
Type: CNAME
Name: www
Value: YOUR_USERNAME.github.io
TTL: 3600
```

### Step 2: Add Custom Domain in GitHub

1. Go to your repository on GitHub
2. Click **Settings** → **Pages**
3. Under **Custom domain**, enter: `khedme.org`
4. Check **Enforce HTTPS** (this will be available after DNS propagates)
5. Click **Save**

### Step 3: Add CNAME File (Optional but Recommended)

Create a file named `CNAME` in the root of your repository with just:
```
khedme.org
```

Then commit and push:
```bash
echo "khedme.org" > CNAME
git add CNAME
git commit -m "Add custom domain CNAME"
git push
```

### Step 4: Wait for DNS Propagation

DNS changes can take anywhere from a few minutes to 48 hours to propagate. You can check the status in GitHub Pages settings.

## Updating Links

Currently, all external links are placeholders (href="#"). To update them:

1. **App Store Links**: Replace `href="#"` in the App Store button with your actual App Store URL
2. **Google Play Links**: Replace `href="#"` in the Google Play button with your actual Play Store URL
3. **Social Media Links**: Update Instagram, TikTok, and Facebook links in the Final CTA section
4. **Footer Links**: Update About, Privacy Policy, and Terms links when those pages are ready

Search for `href="#"` in `index.html` to find all placeholder links.

## Waitlist Form

The waitlist form currently shows an alert. To connect it to a backend:

1. Replace the form submission handler in the JavaScript section
2. Point it to your API endpoint
3. Handle the response appropriately

Example:
```javascript
waitlistForm.addEventListener('submit', async (e) => {
    e.preventDefault();
    const email = waitlistForm.querySelector('input[type="email"]').value;
    
    try {
        const response = await fetch('YOUR_API_ENDPOINT', {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify({ email })
        });
        // Handle response
    } catch (error) {
        // Handle error
    }
});
```

## Color Palette

- **Charcoal**: `#2E2E2E` - Primary text and dark elements
- **Warm Highlight**: `#FFD369` - Accent color, CTAs
- **Teal**: `#008080` - Brand color, links, buttons
- **Background**: `#F7F7F7` - Light background

## Typography

- **Font Family**: Poppins (from Google Fonts)
- **Weights**: 400 (regular), 500 (medium), 700 (bold)

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Maintenance

- All content is in `index.html` - easy to update
- No build process means no compilation needed
- Simply edit HTML and push to GitHub for updates

## License

This website is a product of ACORP Inc. All rights reserved.

## Contact

For questions about this website, contact: hello@khedme.app

---

🇱🇧 Made in Lebanon, for Lebanon. With ❤️ for workers and families.

