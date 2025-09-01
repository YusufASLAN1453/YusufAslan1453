# Create a neon SVG banner and a divider for Yusuf's GitHub README,
# plus a ready-to-use README.md that references them.

from pathlib import Path

assets_dir = Path("/mnt/data/yusuf_github_readme_assets")
assets_dir.mkdir(parents=True, exist_ok=True)

# Neon banner SVG
banner_svg = f"""<svg width="1200" height="360" viewBox="0 0 1200 360" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <radialGradient id="bg" cx="50%" cy="40%" r="80%">
      <stop offset="0%" stop-color="#0b0f1a"/>
      <stop offset="100%" stop-color="#02040a"/>
    </radialGradient>

    <filter id="glowCyan">
      <feGaussianBlur stdDeviation="4.5" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>

    <filter id="glowPink">
      <feGaussianBlur stdDeviation="5.5" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>

    <linearGradient id="wire" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#00e5ff"/>
      <stop offset="50%" stop-color="#9b5cff"/>
      <stop offset="100%" stop-color="#ff2ea6"/>
    </linearGradient>
  </defs>

  <rect width="1200" height="360" fill="url(#bg)"/>

  <!-- Neon wires -->
  <path d="M30 60 C 250 100, 400 20, 600 60 S 950 110, 1170 60" stroke="url(#wire)" stroke-width="6" fill="none" opacity="0.6" filter="url(#glowCyan)"/>
  <path d="M30 300 C 250 260, 400 340, 600 300 S 950 250, 1170 300" stroke="url(#wire)" stroke-width="6" fill="none" opacity="0.6" filter="url(#glowPink)"/>

  <!-- Title -->
  <g text-anchor="middle" transform="translate(600,170)">
    <text x="0" y="0" font-family="Poppins, Segoe UI, Arial" font-weight="800" font-size="78" fill="#00e5ff" filter="url(#glowCyan)">YUSUF ASLAN</text>
    <text x="0" y="62" font-family="Poppins, Segoe UI, Arial" font-weight="600" font-size="28" fill="#ff2ea6" filter="url(#glowPink)">Web Developer • Atlas Üniversitesi</text>
  </g>

  <!-- Small neon dots -->
  <g opacity="0.85">
    <circle cx="120" cy="120" r="3.5" fill="#00e5ff" filter="url(#glowCyan)"/>
    <circle cx="1080" cy="240" r="3.5" fill="#ff2ea6" filter="url(#glowPink)"/>
    <circle cx="940" cy="100" r="3.5" fill="#9b5cff" filter="url(#glowPink)"/>
    <circle cx="240" cy="270" r="3.5" fill="#9b5cff" filter="url(#glowCyan)"/>
  </g>
</svg>
"""
(assets_dir / "neon-banner.svg").write_text(banner_svg, encoding="utf-8")

# Neon divider SVG
divider_svg = """<svg width="1200" height="24" viewBox="0 0 1200 24" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="grad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#00e5ff"/>
      <stop offset="50%" stop-color="#9b5cff"/>
      <stop offset="100%" stop-color="#ff2ea6"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="2.2" result="blur"/>
      <feMerge>
        <feMergeNode in="blur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>
  <rect x="0" y="11" width="1200" height="2" fill="url(#grad)" filter="url(#glow)" opacity="0.9"/>
</svg>
"""
(assets_dir / "neon-divider.svg").write_text(divider_svg, encoding="utf-8")

# README template
readme_md = """<!-- Neon README by ChatGPT for Yusuf Aslan -->
<p align="center">
  <img src="./neon-banner.svg" alt="Yusuf Aslan — Web Developer" />
</p>

<p align="center">
  <a href="mailto:yusuf@example.com"><img src="https://img.shields.io/badge/iletişim-email-00e5ff?style=for-the-badge&labelColor=0b0f1a"></a>
  <img src="https://img.shields.io/badge/durum-aktif-ff2ea6?style=for-the-badge&labelColor=0b0f1a">
  <img src="https://komarev.com/ghpvc/?username=YOUR_USERNAME&style=for-the-badge&label=Profil%20G%C3%B6r%C3%BCnt%C3%BCleme&color=9b5cff"/>
</p>

<img src="./neon-divider.svg" alt="" />

### 🧠 Hakkımda (kısa kısa)
- Atlas Üniversitesi **Bilgisayar Programcılığı** öğrencisi.
- Odak: **Web geliştirme** (Frontend ağırlıklı), ufak otomasyonlar.
- Şu an: **JS derinleşme**, modern **React** ve **Node** temelleri.

<img src="./neon-divider.svg" alt="" />

### ⚒️ Teknolojiler
`HTML` • `CSS` • `JavaScript` • `C# (temel)` • `Python (otomasyon)` • `MySQL`  
Araçlar: `Git` • `GitHub` • `VS Code` • `Postman` • `Figma`

<img src="./neon-divider.svg" alt="" />

### 🚀 Web Projeleri (öne çıkanlar)
| Proje | Özet | Teknolojiler | Durum |
|---|---|---|---|
| **Neon Portfolyo** | Modern, tek sayfa portfolyo (responsive) | HTML, CSS, JS | ✅ |
| **FilmRadar** | API ile film/dizi arama + detay sayfası | JS, Fetch API | ✅ |
| **Hava360** | Şehir bazlı hava durumu + favoriler | JS, LocalStorage | ✅ |
| **MenuX** | Restoran menü & filtreleme | HTML, CSS, JS | ✅ |
| **ShopLite** | Sepet mantıklı mini e-ticaret demo | JS, LocalStorage | 🚧 |
| **ChatRoom** | Basit gerçek zamanlı sohbet | Node.js, Socket.io | 🚧 |
| **TaskBoard** | Kanban tarzı todo | JS, Drag&Drop API | ✅ |

> İpucu: Her repo README’sinde **gif veya ekran görüntüsü** kullan, kurulum adımlarını yaz.

<img src="./neon-divider.svg" alt="" />

### 📊 İstatistik
<p align="center">
  <img height="150" src="https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME&show_icons=true&theme=radical" />
  <img height="150" src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_USERNAME&layout=compact&theme=radical" />
</p>

<img src="./neon-divider.svg" alt="" />

### 📌 Hızlı Linkler
- 🔗 [Portfolyo (repo)](./) — (ekle)
- 🔗 [LinkedIn](https://linkedin.com/in/USERNAME) — (opsiyonel)
- 🔗 [Twitter/X](https://x.com/USERNAME) — (opsiyonel)

<img src="./neon-divider.svg" alt="" />

#### 🗒️ Not
Bu README’deki görsellerin çalışması için `neon-banner.svg` ve `neon-divider.svg` dosyalarını aynı dizinde tut.
"""

(assets_dir / "README.md").write_text(readme_md, encoding="utf-8")

print("Created:")
for f in assets_dir.iterdir():
    print("-", f)
