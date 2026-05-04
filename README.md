# CBT Thought Record PWA

Offline-first Progressive Web App buat ngisi CBT thought record (Trigger → Thoughts → Feelings → Behaviours).

## Cara Pakai (Quick Start)

### Option 1: Buka langsung di browser
1. Extract semua file ke 1 folder
2. Buka `index.html` di Chrome/Safari
3. Bisa langsung dipake (data tersimpan di localStorage browser)

⚠️ Note: Service worker & "Install to Home Screen" cuma jalan kalau di-serve via HTTPS atau localhost.

### Option 2: Install as PWA (recommended)
Deploy ke hosting gratis biar bisa di-install di home screen iPhone/Android:

**Pakai GitHub Pages (gratis, paling gampang):**
```bash
# 1. Bikin repo baru di GitHub
# 2. Upload semua file (index.html, manifest.json, sw.js, icon-*.png)
# 3. Settings → Pages → Source: main branch → Save
# 4. Buka URL: https://[username].github.io/[repo-name]/
```

**Pakai Netlify Drop (paling cepet):**
1. Buka https://app.netlify.com/drop
2. Drag folder ini
3. Done — dapet URL HTTPS

**Pakai local server (buat testing):**
```bash
cd cbt-app
python3 -m http.server 8000
# Buka http://localhost:8000
```

### Install ke Home Screen
- **iPhone (Safari):** Buka URL → Share button → "Add to Home Screen"
- **Android (Chrome):** Buka URL → Menu (3 dot) → "Install app" / "Add to Home Screen"

Setelah di-install, app jalan offline sepenuhnya.

## Fitur

✅ Hybrid mode — guided step-by-step (bisa skip) atau full form sekaligus  
✅ Auto-save draft (localStorage) — gak ilang kalau accidentally close  
✅ History list dengan search  
✅ Edit & delete entries  
✅ Mood rating 1–10  
✅ Tags (work, family, sleep, dll) + custom tags  
✅ Date/time stamp otomatis  
✅ Export single entry atau ALL entries jadi PDF (lewat browser print)  
✅ JSON backup download  
✅ 100% offline — gak ada server, gak ada tracking  

## Cara Export PDF
- **Single entry:** Tap entry di History → 📄 PDF
- **All entries:** History tab → "📄 Export All (PDF)"
- Browser bakal buka print dialog → pilih "Save as PDF" → share PDF-nya

## Backup Data
History tab → "⬇️ Backup" — download `.json` file. Kalau ganti device, copy file ini & import manually (atau di future version bisa ditambah import button).

## Tech
- Vanilla JS + HTML + CSS (no framework, no build step)
- localStorage untuk persistence
- Service Worker untuk offline caching
- Print-to-PDF lewat browser native (gak butuh library)

## Files
- `index.html` — main app (semua logic ada di sini)
- `manifest.json` — PWA manifest
- `sw.js` — service worker
- `icon-192.png` / `icon-512.png` — app icons
