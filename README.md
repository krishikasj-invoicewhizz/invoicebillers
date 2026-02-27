# 📲 Invoicebillers — SaaS Invoicing via WhatsApp

A clean, modern landing page for a WhatsApp-native SaaS invoicing product. Built with pure HTML, CSS, and vanilla JavaScript — no frameworks, no build tools needed.

## 🚀 Live Preview

Open `index.html` in your browser, or deploy to GitHub Pages / Netlify / Vercel in one click.

## ✨ Features

- **Fully responsive** — works on mobile, tablet, and desktop
- **Smooth scroll animations** with IntersectionObserver
- **Interactive chat mockup** showing the product experience
- **Sticky navigation** with mobile hamburger menu
- **Pricing table** with highlighted recommended plan
- **FAQ accordion** section
- **Dark themed** with WhatsApp-green accent palette
- **Zero dependencies** — pure HTML/CSS/JS

## 📁 File Structure

```
invoicebillers/
├── index.html        # Single-file website (all CSS & JS inline)
└── README.md
```

## 🛠 How to Deploy

### GitHub Pages
1. Fork / clone this repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your site will be live at `https://yourusername.github.io/invoicebillers`

### Netlify (drag & drop)
1. Go to [netlify.com](https://netlify.com)
2. Drag the project folder onto the Netlify dashboard
3. Done — live URL in seconds

### Vercel
```bash
npx vercel
```

## 🎨 Customization

Edit these CSS variables at the top of `index.html` to change the color scheme:

```css
:root {
  --green: #25D366;       /* WhatsApp green */
  --green-dark: #128C7E;
  --black: #0a0a0a;       /* Background */
  --text: #e8ede9;        /* Body text */
}
```

## 📄 License

MIT — free to use and modify for personal or commercial projects.
