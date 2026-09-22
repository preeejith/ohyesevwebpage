# Oh Yes App - EV Charging Marketing Website

This project is a static, single-page marketing website built with Vue 3 (Composition API), Vite, and Tailwind CSS. It is fully component-based and highly optimized for performance and SEO.

## Features
- **Modern Design:** Dark navy and electric green theme with glassmorphism and glow effects.
- **Responsive:** Mobile-first layout that looks perfect on all devices.
- **Animations:** Custom IntersectionObserver wrapper (`RevealOnScroll`) for scroll animations, counting numbers, and infinite marquees.
- **Interactive Calculator:** Client-side earnings calculator built with Vue reactivity.
- **Easy Content Management:** All text, numbers, and settings live in `src/data/content.js`.

## Setup & Development

```bash
# Install dependencies
npm install

# Run the development server
npm run dev

# Build for production
npm run build
```

## Customization Guide

### 1. Replacing the Video
Replace the placeholder video by uploading your actual video file to `public/evvideo.mp4`. Ensure it is compressed and preferably under 5MB for fast loading.

### 2. Updating Content and Copy
Open `src/data/content.js` to modify text, statistics, FAQ answers, partner models, and calculator options.

### 3. Updating the WhatsApp Number
In `src/data/content.js`, locate the `whatsapp.number` field and update it to your actual business number (include country code without the `+`, e.g., `919876543210`).

### 4. Updating App Store Links
In `src/components/sections/AppDownloadSection.vue`, locate the `<a href="#">` tags and update the `href` attribute with your actual Google Play and App Store links.

### 5. Updating Logos
The infinite marquee in `src/components/sections/ChargerBrands.vue` currently uses text placeholders. You can replace the `<span>` tags with `<img>` tags pointing to brand logos in your `public` or `src/assets` folder.

## Deployment

To deploy this static site to platforms like **Netlify, Vercel, or cPanel**:

1. Run the build command:
   ```bash
   npm run build
   ```
2. A `dist/` folder will be generated in the root directory.
3. **Netlify / Vercel:** Drag and drop the `dist/` folder, or connect your Git repository and set the build command to `npm run build` and output directory to `dist`.
4. **cPanel (Shared Hosting):** Zip the contents of the `dist/` folder (not the folder itself), upload it to your `public_html` directory via File Manager, and extract it.
# ohyesevwebpage
