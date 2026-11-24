# SHOPNEXA ROBI HUB – Project Continuity & Deployment Guide

> **Live Domain:** `https://shopnexa-2.onrender.com/`  
> **Primary Brand:** `SHOPNEXA ROBI HUB – THE FUTURE OF SHOPPING`

---

## CRITICAL CONTINUITY RULES (FOR ALL FUTURE CHATS, REPOSITORIES & DEVELOPERS)

If this codebase is opened in a new chat, imported from a ZIP package, or pushed to a new GitHub repository:

1. **DO NOT REBUILD OR REPLACE THIS WEBSITE:**  
   Always preserve and continue updating **this exact SHOPNEXA ROBI HUB** application (`src/`, `server/`, `server.ts`, `public/`, `index.html`). Never overwrite it with a generic starter template.
2. **NO DEMO / PRE-SEEDED PRODUCTS:**  
   `server/db.ts` intentionally keeps the product catalog empty (`0` pre-seeded demo products, `0` pre-seeded category images). Only products uploaded by the store owner in the Admin Dashboard must appear on the storefront.
3. **PRESERVE GOOGLE SEARCH CONSOLE & SEO ASSETS:**  
   - Keep `<meta name="google-site-verification" content="iNIjZg67P6fK6as5coq-C_ejOFTji61G6Z1LEty3Eok" />` in `index.html`.
   - Keep `public/google34bbea4330855c4c.html`, `public/sitemap.xml`, `public/robots.txt`, and dynamic `/sitemap.xml` & `/robots.txt` routes in `server.ts`.
4. **PRESERVE CORE STORE FEATURES:**  
   - 100% Bilingual toggle (English `en` & Bengali `bn`) across storefront and Admin Dashboard.
   - Detailed Bangladesh & international delivery address checkout (Division, District, Thana/Upazila, Post Office, Village/Area & Landmark).
   - Live order tracking (`/?page=track`), direct `no-store` product publishing to Main Page, and SQLite `.db` Backup/Restore in Admin Settings.

---

## Pushing to a New GitHub Repository

1. Open **Admin Dashboard → Sign In GitHub & Push** (or **Settings → GitHub & Render One-Step Deploy Hub**).
2. Click **Download Clean GitHub ZIP** (excludes temporary `.db` files, `node_modules`, and local uploads so the repository stays clean).
3. Create a new repository on GitHub (`https://github.com/new`) or open your existing repository (`https://github.com/ronivv290-glitch/Shopnexa`).
4. Unzip the downloaded Clean ZIP locally and upload all files (`src/`, `server/`, `public/`, `server.ts`, `index.html`, `package.json`, `README.md`, `render.yaml`, etc.) to the `main` branch.

---

## Daily Data Safety (Database Backup & Restore)

- Before major deploys or at the end of daily updates, go to **Admin Dashboard → Settings → Download Database (.db)** to save a complete snapshot of your uploaded products, categories, orders, settings, and customer records.
- On Render, ensure `DATA_DIR` points to a persistent disk if configured, or restore anytime via **Settings → Restore Database (.db)**.
