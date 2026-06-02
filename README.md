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

## Firebase Setup (Orders Database)

### Step 1 — Create a Firebase project
1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Click **Add project** → name it `theflorasan` → Continue
3. Disable Google Analytics → **Create project**

### Step 2 — Enable Firestore
1. Left sidebar → **Firestore Database** → **Create database**
2. Choose **Production mode** → region `asia-south1` (Pakistan) → **Enable**
3. Go to **Rules** tab and set:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /orders/{orderId} {
      allow create: if true;
      allow read, update: if false;
    }
  }
}
```
4. Click **Publish**

### Step 3 — Get your config
1. **Project Settings** (gear icon) → **Your apps** → click `</>` → register as `theflorasan-web`
2. Copy the `firebaseConfig` object shown

### Step 4 — Paste config into both files
In `index.html` AND `admin.html` find `const FIREBASE_CONFIG = {` and replace the placeholder values.

### Step 5 — Change admin password
In `admin.html` find `const ADMIN_PASSWORD = "florasan2025"` and change it.

### Step 6 — Update your phone number
In `index.html` find the payment instruction boxes and replace `0300-0000000` with your actual number.

---

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
