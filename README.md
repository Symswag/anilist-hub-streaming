# 🟠🔵🔴 AniList - Streaming Hub

[![Version](https://img.shields.io/badge/version-3.7.1-blue.svg)](https://github.com/Symswag/)
[![Platform](https://img.shields.io/badge/platform-Anilist-blue.svg)](https://anilist.co/)

A minimalist and robust UserScript for **AniList** that adds a dedicated "Where to watch?" section directly into the anime sidebar.

It automatically detects if an anime is available on your favorite streaming platforms to display a direct launch button. If no direct link is found, it intelligently generates a search button based on the official title of the anime.

---

## ✨ Features

* 🧩 **Seamless Integration:** Cleanly blends into AniList's native design, positioned stably right above the *Rankings* block.
* 🔗 **Smart Detection:** Scans the sidebar on the fly. If a direct streaming link exists (via MAL Sync or AniList), the button highlights and takes you straight to the episode.
* 🔍 **Fallback Auto-Search:** No direct link? The button dynamically generates a redirection to the platform's search engine using the correct anime title.
* 🚦 **Visual Indicators:**
    * `🔗` + Brighter background = Direct link detected.
    * `🔍` + Standard background = Automatic search fallback.
* 🚀 **SPA Compatible:** Perfectly handles AniList's internal navigation (Single Page Application) without requiring manual page refreshes.
* ⚙️ **Highly Customizable:** Easily add or reorder your own favorite websites by editing a single configuration array.

---

## 🛠️ Default Configuration

The script is pre-configured to sort and display platforms in the following order:
1.  🟠 **Crunchyroll** (Direct Link or Search)
2.  🔵 **ADN** (Search only)
3.  🔴 **Netflix** (Direct Link or Search)
4.  🟢 **Disney+** (Direct Link or Search)
5.  ⚪ **VoirAnime** (Search only)
6.  ⚫ **Anime-sama** (Search only)

---

## 📦 Installation

### Prerequisites
You need a userscript manager installed on your browser:
* [Tampermonkey](https://www.tampermonkey.net/) (Recommended)
* [Violentmonkey](https://violentmonkey.github.io/)

### Method 1: One-Click Install (Recommended)
> ⚠️ **Note:** For this method to work seamlessly, make sure your script file ends with `.user.js` (e.g., `anilist-streaming-hub.user.js`).

1. Click on your script file here on GitHub.
2. Click the **Raw** button at the top right of the code block.
3. Your userscript manager (Tampermonkey) will automatically open and offer to install the script. Click **Install**.

### Method 2: Manual Install
1. Open your userscript manager dashboard.
2. Create a **New Script**.
3. Copy the entire code from the script file in this repository and paste it over the default template.
4. Save the script (`Ctrl + S` or `Cmd + S`).

Now, simply navigate to any anime page on [AniList](https://anilist.co/) to see the hub!

---

## 🔧 Customization

You can easily add your own websites or alter the priority order. Open the script and modify the `STREAMING_CONFIG` array at the top of the file:

```javascript
const STREAMING_CONFIG = [
    {
        name: 'Website Name',
        color: '#HexColor', // Left border color accent (e.g., #ff6600)
        icon: '🎬',        // Emoji of your choice
        keywords: ['mywebsite'], // Keywords to detect a direct link on the page (leave empty [] for search-only)
        searchUrl: '[https://mywebsite.com/search?query=](https://mywebsite.com/search?query=)' // The site's search query URL
    }
];