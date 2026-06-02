# Theflorasan — Official Website

Handmade pipe cleaner flowers & bouquets. Based in Pakistan.

## Project Structure

```
theflorasan-project/
├── index.html              ← Main website (all 4 pages)
├── images/
│   ├── bouquets/           ← Drop bouquet photos here
│   │   ├── mini-pink.jpg
│   │   ├── sunshine-mini.jpg
│   │   └── ...
│   └── singles/            ← Drop single flower photos here
│       ├── classic-rose.jpg
│       ├── sunflower.jpg
│       └── ...
└── README.md
```

## How to Add Your Images

1. Put your product photos in the correct `images/` folder
2. Open `index.html` and find the product you want to update
3. Replace the emoji with an `<img>` tag, like this:

**Before (emoji placeholder):**
```html
<div class="product-img" style="background:...">🌹</div>
```

**After (your real image):**
```html
<div class="product-img">
  <img src="images/singles/classic-rose.jpg" alt="Classic Rose"/>
</div>
```

**Tips for photos:**
- Size: 800×800px square works best
- Format: JPG or WebP for fastest loading
- Keep file sizes under 300KB each
- Name files simply: `pink-bouquet.jpg`, `blue-rose.jpg`, etc.

## How to Update Prices

Find the product in `index.html` and update:
```html
<span class="price">Rs. 450</span>
<button class="add-btn" onclick="addToCart(this,'Classic Rose',450,'🌹')">
```
Change both the display price AND the number in `addToCart(...)`.

## How to Update Product Descriptions

Find the `<p>` tag under the product name and replace the text.

## Checkout / Orders

Currently the checkout button opens WhatsApp with the order details.
Update this line in the `<script>` section with your actual WhatsApp number:
```js
window.open(`https://wa.me/923000000000?text=...`)
```
Replace `923000000000` with your number (country code + number, no spaces or +).

## Deploying Online (Free)

### Option A — Netlify (easiest)
1. Go to netlify.com → sign up free
2. Drag and drop this entire folder onto their dashboard
3. Your site is live instantly at a `.netlify.app` URL
4. Connect your custom domain in Settings → Domain Management

### Option B — GitHub Pages (free)
1. Push this folder to a GitHub repository
2. Go to repo Settings → Pages → set source to `main` branch
3. Your site is live at `yourusername.github.io/theflorasan`
4. Connect your custom domain in the Pages settings

## Custom Domain

Once you purchase a domain (e.g. theflorasan.com from Namecheap ~$10/year):
- On Netlify: add it under Site Settings → Domain Management
- On GitHub Pages: add a CNAME file with your domain name

---
Made with 💗 | © 2025 Theflorasan
