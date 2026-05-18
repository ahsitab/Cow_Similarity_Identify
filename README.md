# 🐄 CowID Portal - Visual Intelligence Cow Database & Marketplace

An interactive, high-fidelity web dashboard, visual database, and catalog for tracking, grouping, and inquiring about individual cows based on visual similarity. This system utilizes a state-of-the-art self-supervised deep learning model (**DinoV2**) to extract semantic feature embeddings from 112 cow photos, clustering them into **51 distinct cows** with **100% visual accuracy and 0 false positives**.

This portal is fully optimized for **mobile phones** and incorporates direct **WhatsApp contact integration** (Number: `01712687383`), turning the database into a functional livestock marketplace.

---

## 🚀 Key Features

* **Visual Analytics Stats Bar:** Instantly tracks Unique Cows, Total Images, Average Photos per Cow, and Recurring Cows. Fully stacks and scales on mobile viewports.
* **Image Organization:** All 112 renamed cow photos are organized cleanly within a dedicated `images/` directory, keeping the project root light and neat.
* **Direct WhatsApp Integration:**
  * Global floating WhatsApp header link (`💬 WhatsApp: 01712687383`).
  * Direct **Inquiry WhatsApp** buttons on every cow card and inside the detail modal.
  * Clicking any button dynamically opens a chat with a custom, pre-filled inquiry text identifying the specific cow:
    `Hello! I am interested in Cow Tag [TagID] on your portal.`
* **Marketplace Badges:**
  * **Price Specification:** Defaulted to `Nego` (Negotiable) in rose-magenta styling.
  * **Weight Specification:** Defaulted to `TBA` (To Be Announced) in indigo styling.
* **Dynamic Search & Filters:** Instantly search by Tag ID and filter between "All Cows", "Multiple Photos (2+)", or "Single Photo (1)" with sorting.
* **Interactive Glassmorphic Modal Gallery:** Click on any cow to view a modal detail gallery containing:
  * An interactive sliding carousel of all photos of that cow.
  * Clickable thumbnail strips.
  * Interactive fullscreen view.
  * Fully accessible keyboard controls (Escape to close, Left/Right arrows to slide).
  * A transparent renaming audit log mapping the original WhatsApp image name to the new `images/Tag(Index)` format.

---

## 🛠️ Technology Stack

* **Feature Extraction & Clustering:** PyTorch, torchvision, DinoV2 (`dinov2_vits14` embeddings), Scikit-Learn (Agglomerative Clustering).
* **Frontend Web Dashboard:** Semantic HTML5, Vanilla CSS3 (Custom properties, grid layouts, glassmorphic backdrop-filters, custom touch media-queries), ES6+ JavaScript.
* **Data Integration:** Built-in JS database module (`cows_data.js`) which allows direct, zero-CORS local loading without needing a running server.

---

## 💻 Running the Portal Locally

Because the database is loaded as a JavaScript module (`cows_data.js`), **you do not need a running web server to open the interface!**

### Method 1: Double-Click (Zero Setup)
Simply navigate to your project folder and double-click `index.html` to open it in your browser (`file:///` protocol). The portal will load completely and work flawlessly!

### Method 2: Python HTTP Server
To serve it over a local address (e.g., to view on mobile or local network):
```bash
# In the project directory, run:
python -m http.server 8000
```
Then visit: `http://localhost:8000`

---

## 🌐 How to Deploy the Interface (Step-by-Step)

Since this is a high-performance static website, you can host and share it globally **100% for free**! Here are the best deployment options:

### Option 2: GitHub Pages (Free & Automatic)
This is the easiest option since your repository is on GitHub.
1. Push your code to your GitHub repository: `https://github.com/ahsitab/Cow_Similarity_Identify.git` (see Git instructions below).
2. Go to your repository page on GitHub.
3. Click on the **Settings** tab (gear icon at the top).
4. On the left sidebar, click on **Pages** (under the "Code and automation" section).
5. Under **Build and deployment** -> **Branch**, select `main` (or `master`) and click **Save**.
6. Refresh the page after 1 minute. GitHub will display a live URL like: `https://ahsitab.github.io/Cow_Similarity_Identify/`
7. Your site is live! Any time you push changes to GitHub, the site updates automatically.

### Option 2: Vercel (Free, Super-Fast & Sleek)
Vercel is a premium hosting provider for web applications with a global CDN.
1. Go to [vercel.com](https://vercel.com) and sign up for a free "Hobby" account using your GitHub account.
2. Click **Add New Project**.
3. Import your `Cow_Similarity_Identify` repository.
4. Click **Deploy** (no configurations or build steps are needed, as Vercel automatically detects it as a static site).
5. Vercel will give you a stunning custom URL (e.g. `cow-similarity-identify.vercel.app`) with an automatic SSL certificate.

### Option 3: Netlify (Free & Drag-and-Drop)
Netlify allows instant deployment either from Git or by dragging the folder.
1. Go to [netlify.com](https://netlify.com) and log in.
2. Either connect your GitHub repo and select it for automatic deploys, OR:
3. Drag the folder containing `index.html`, `index.css`, `cows_data.js`, and the `images/` directory directly into the Netlify Dashboard upload box.
4. Your site will deploy in less than 5 seconds!

---

## 📁 Repository Structure
```
├── images/                  # Organized folder for renamed images
│   ├── 2601(1).jpg          
│   ├── 2601(2).jpg
│   └── ...
├── backup_original/         # Local backup of original WhatsApp source images (Git ignored)
├── index.html               # Main dashboard webpage
├── index.css                # Premium glassmorphism styles
├── cows_data.js             # JavaScript database module powering the frontend
├── cows_db.json             # Structured JSON database file for API consumption
└── README.md                # Project documentation
```
