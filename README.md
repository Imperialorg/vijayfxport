# Vijay FX - Video Editor Portfolio

A stunning, cinematic portfolio website for video editors with Netflix-style aesthetics and smooth animations.

## 🎬 Features

- **Cinematic Design**: Dark theme with red accents inspired by Netflix
- **Smooth Animations**: Engaging scroll effects and transitions
- **Responsive Layout**: Works perfectly on all devices
- **Portfolio Showcase**: Grid layout for projects with video previews
- **Showreel Section**: Embedded video player for your demo reel
- **Contact Form**: Easy way for clients to reach out
- **Fast Loading**: Optimized performance with lazy loading

## 🚀 Quick Start

### Option 1: Deploy to Netlify (Recommended)

1. Fork or clone this repository
2. Go to [Netlify](https://netlify.com)
3. Click "Add new site" → "Import an existing project"
4. Connect your GitHub account and select this repository
5. Click "Deploy site"

Your site will be live in seconds at `https://your-site-name.netlify.app`

### Option 2: Deploy to GitHub Pages

1. Fork this repository
2. Go to Settings → Pages
3. Under "Source", select "main" branch
4. Click Save
5. Your site will be live at `https://yourusername.github.io/vijayfxport`

### Option 3: Run Locally

```bash
# Clone the repository
git clone https://github.com/yourusername/vijayfxport.git

# Navigate to the directory
cd vijayfxport

# Open with a local server (Python example)
python -m http.server 8000

# Or use VS Code Live Server extension
# Right-click index.html → "Open with Live Server"
```

## 📝 Customization Guide

### 1. Personal Information

Edit `index.html`:

- **Line 18**: Update page title
- **Lines 42-44**: Change hero title text
- **Line 45**: Update subtitle with your title
- **Lines 71-75**: Edit about section text
- **Lines 218-230**: Update contact information

### 2. Add Your Videos

Replace placeholder videos with your own:

```html
<!-- Hero Background Video -->
<video autoplay muted loop playsinline class="hero-video">
    <source src="assets/hero-bg.mp4" type="video/mp4">
</video>

<!-- Portfolio Project Videos -->
<source src="assets/project1-preview.mp4" type="video/mp4">
```

### 3. Portfolio Projects

Edit the portfolio section in `index.html` (lines 113-232):

```html
<div class="portfolio-item" data-category="commercial">
    <div class="portfolio-thumbnail">
        <img src="assets/project1.jpg" alt="Your Project">
    </div>
    <div class="portfolio-info">
        <span class="category">CATEGORY</span>
        <h3>Project Title</h3>
        <p>Project description</p>
    </div>
</div>
```

### 4. Showreel Video

Replace the Vimeo embed (line 240):

```html
<iframe 
    src="https://player.vimeo.com/video/YOUR_VIDEO_ID" 
    frameborder="0" 
    allowfullscreen>
</iframe>
```

Or use YouTube:

```html
<iframe 
    src="https://www.youtube.com/embed/YOUR_VIDEO_ID" 
    frameborder="0" 
    allowfullscreen>
</iframe>
```

### 5. Colors & Branding

Edit `styles.css` (lines 11-18):

```css
:root {
    --primary-color: #e50914;     /* Main accent color */
    --secondary-color: #f5f5f1;   /* Secondary accent */
    --dark-bg: #0a0a0a;          /* Dark background */
    --darker-bg: #000000;         /* Darker background */
    --accent-gold: #d4af37;       /* Gold accent */
}
```

### 6. Social Links

Update social media links (lines 282-322 in `index.html`):

```html
<a href="https://instagram.com/yourusername" target="_blank">
<a href="https://vimeo.com/yourusername" target="_blank">
<a href="https://youtube.com/@yourusername" target="_blank">
<a href="https://linkedin.com/in/yourusername" target="_blank">
```

## 📁 Project Structure

```
vijayfxport/
├── index.html          # Main HTML file
├── styles.css          # All styles and animations
├── script.js           # JavaScript functionality
├── netlify.toml        # Netlify configuration
├── README.md           # This file
└── assets/             # Your media files (create this folder)
    ├── hero-bg.mp4     # Hero section background video
    ├── profile.jpg     # Your photo
    ├── project1.jpg    # Project thumbnails
    ├── project1-preview.mp4
    └── ...
```

## 🎨 Assets Folder Setup

Create an `assets` folder and add:

1. **hero-bg.mp4**: Full HD video (1920x1080) for hero section
2. **profile.jpg**: Your professional photo
3. **project thumbnails**: High-quality images (16:9 ratio recommended)
4. **project previews**: Short video clips (5-10 seconds)

### Recommended Sizes:
- Hero video: 1920x1080, compressed, max 10MB
- Project thumbnails: 1280x720 JPG
- Project previews: 720p MP4, max 5MB each
- Profile image: 800x800 or larger

## 🔧 Contact Form Setup

The contact form is ready to use. Choose one option:

### Option 1: Netlify Forms (Easiest)

Add to your `<form>` tag:
```html
<form class="contact-form" netlify>
```

Netlify will automatically handle submissions!

### Option 2: Formspree

1. Sign up at [Formspree.io](https://formspree.io)
2. Update the form action:
```html
<form class="contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

### Option 3: EmailJS

1. Sign up at [EmailJS.com](https://www.emailjs.com/)
2. Follow their integration guide
3. Update `script.js` with your EmailJS credentials

## 🎯 SEO Optimization

1. Update meta tags in `index.html`:
```html
<meta name="description" content="Your description">
<meta name="keywords" content="video editor, your name, etc">
```

2. Add Open Graph tags for social sharing:
```html
<meta property="og:title" content="Your Name - Video Editor">
<meta property="og:description" content="Your description">
<meta property="og:image" content="assets/og-image.jpg">
```

3. Create a `sitemap.xml` for better indexing

## 📱 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 🚀 Performance Tips

1. **Compress videos**: Use HandBrake or FFmpeg
2. **Optimize images**: Use TinyPNG or ImageOptim
3. **Enable caching**: Netlify handles this automatically
4. **Use CDN**: Netlify provides global CDN

## 📄 License

This project is free to use for personal and commercial purposes. Attribution appreciated but not required.

## 🤝 Support

Need help? 
- Open an issue on GitHub
- Check the customization guide above
- Review the code comments

## 🎬 Credits

Design inspiration: Netflix, modern video portfolios
Fonts: Bebas Neue, Inter (Google Fonts)
Icons: Custom SVG

---

**Made with ❤️ for video editors and creative professionals**

Ready to showcase your work? Deploy now and start attracting clients! 🚀