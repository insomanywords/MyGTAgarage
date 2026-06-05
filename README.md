# My GTA Garage 🚗💨

[![Version](https://img.shields.io/badge/version-1.66.12-blue.svg)](https://github.com/insomanywords/MyGTAgarage)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**My GTA Garage** is the ultimate, offline-first, Progressive Web App (PWA) designed for Grand Theft Auto Online car collectors. It provides a clean, fast, and feature-rich interface to track, organize, and manage your massive vehicle fleets across multiple characters. 

Built with zero backend requirements, your data lives securely in your browser and automatically syncs to your personal Google Drive. 



---

## ✨ Features

### 🏢 Comprehensive Vehicle Management
* **Add/Edit Vehicles:** Track your Make, Model, Garage, and Floor location.
* **Granular Details:** Assign exact Slot numbers, Plate types (Yankton, Liberty City, Panic, E-Cola, etc.), **Custom License Plate text overlay**, and Wheel types (Stock, F1, Benny's).
* **Status Tags:** Instantly visually flag vehicles as **Favorite**, **Weaponized**, **HSW**, **Drift**, or **Imani Tech**.
* **Financial Tracking:** Log the *LSCM Price* (Value) and *Sell Price* of your assets.
* **Custom Images:** Ditch the stock photos! Upload your own custom screenshots. They auto-sync securely to your Google Drive to save local storage.
* **Rapid Entry:** Use the **Duplicate/Copy** feature to clone identical builds, changing only the slot number for mass fleet entry.

### 🔄 Fleet Operations
* **Move Vehicles:** Effortlessly migrate cars between properties. The app auto-detects full garages and prompts you to select a vehicle to swap places with.
* **Auto-Organize Blueprint:** Calculate a mathematically perfect garage layout without forcefully overwriting your manual sort. It creates an interactive checklist that live-updates, showing you exactly where to move each car and marking them off as you go.
* **Swap Entire Garages:** Relocating? Instantly swap the entire contents of two different garages with a single click.
* **Sales Cooldown & Penalty Tracker:** Simulate selling a car. The app logs the transaction in your **Sales History**, starts the real-time 18-hour Daily Sell Limit cooldown timer, applies the $500k vehicle value cap, tracks the 7-day penalty multiplier for consecutive sales, and allows you to manually override the final sale price.

### 🗂️ Advanced Organization & Filtering
* **Dynamic Grouping:** Collapse or expand your collection grouped by Garage, Brand, Class, Drive Type, Wheels, Plates, Weaponized, or HSW status. 
* **State Preservation:** The app intelligently remembers which folders you have expanded, so you never lose your place while editing.
* **Real-Time Search:** Instantly filter your hundreds of cars by name, manufacturer, location, or custom notes.
* **Advanced Filter Matrix:** Combine multiple criteria (e.g., *Show me all Weaponized, F1-wheeled vehicles in my Agency*).
* **Floor Nicknames:** Assign custom names to specific garage levels (e.g., "JDM Floor", "Supercar Level").

### ☁️ Data Security & Cloud Sync
* **Offline-First PWA:** Install it on your phone or desktop. The app works flawlessly offline, reading and writing to your local browser storage.
* **Google Drive Sync:** Sign in to Google, and the app creates a private `My GTA Garage` folder in your Drive. Every change you make locally is instantly and silently auto-synced in the background. 
* **Settings Roaming:** Your UI accent colors, custom license plate defaults, and business location preferences roam with you across all your characters and devices.
* **Conflict Resolution:** Swapping between your phone and PC? The app detects sync conflicts and prompts you to keep your local data or download the latest cloud save.
* **Local Backups:** Manually export or import your raw `.json` database at any time.

### 📤 Sharing & Exporting
* **Public View-Only Mode:** Generate a time-stamped, read-only link to your garage. Share it with friends or the LS Car Meet community so they can browse your collection without modifying your data.
* **Vehicle Snapshots:** Generate a clean, styled image card of a specific vehicle to instantly share to Discord, Reddit, or Messages.
* **Deep Linking:** Share a public link that opens directly to a specific vehicle's detail card.
* **PDF Export:** Generate a professional, multi-page (or continuous digital) PDF catalog of your entire collection in either compact list or large detail format.
* **Gamertag Integration:** Personalize your public links, snapshots, and PDFs by displaying your specific Gamertag and Platform icon.

### 🗺️ Interactive Map & Properties
* **High-Res Los Santos Map:** Visualize your empire with a fully interactive map using data-mined engine coordinates.
* **Dynamic Locations:** Precisely map business properties like Nightclubs, Offices, and Agencies with sub-location support.
* **Cloud-Synced Pins:** Your property choices roam with your character data, ensuring your map is consistent across devices.

---

## 🚀 Installation & Usage

Because My GTA Garage is a client-side PWA, there is no server to configure or database to host. 

### Option 1: Use the Live App
Simply visit the live hosted version (if available) and click **"Add to Home Screen"** on your mobile device or desktop browser to install it as a native app.

### Option 2: Self-Hosting (GitHub Pages / Local)
1. Clone or download this repository.
2. Ensure all files (`index.html`, `manifest.json`, `sw.js`, `icon.svg`) are in the same root directory.
3. Serve the directory using any static web server (e.g., GitHub Pages, VS Code Live Server, or Python `http.server`).
4. **Note on Google Drive Sync:** If you self-host on a different domain, you will need to replace the `CLIENT_ID` in `index.html` with your own Google Cloud Console OAuth 2.0 Client ID, configured with your specific authorized JavaScript origins.

---

## ⚙️ How Google Drive Sync Works

My GTA Garage utilizes **Google Identity Services (GIS)** and the **Google Drive REST API v3**. 

1. When you authenticate, the app creates a structured folder tree in your Drive:
   `My GTA Garage / [Character Name] / database` and `../images`
2. It operates entirely via `fetch` and `gapi.client` requests, bypassing strict browser ITP/CORS blocking for cross-origin iframes.
3. **Session Management:** The app utilizes a dual-mode silent token refresh system. It proactively monitors token expiration and invisibly renews your session in the background, preventing annoying account-picker popups on mobile devices.

---

## 🛠️ Built With

* **Vanilla HTML / CSS / JavaScript:** Zero heavy frameworks (No React, Vue, or Angular) for maximum speed and minimal footprint.
* **Google Identity Services & Drive API:** For seamless, serverless cloud synchronization.
* **html2canvas:** For generating shareable vehicle snapshot images.
* **jsPDF:** For generating multi-page collection catalogs.
* **FontAwesome:** For UI iconography.

---

## 📝 Changelog

See the in-app **About > View Changelog** modal for a detailed history of updates and bug fixes, including the latest **v1.66.12** improvements.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

*Note: This application is a fan-made tool and is not affiliated with, endorsed, or sponsored by Rockstar Games or Take-Two Interactive.*
