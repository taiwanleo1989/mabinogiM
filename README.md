# 瑪奇 Mobile 新手冒險指南

《瑪奇 Mobile（마비노기 모바일 / Mabinogi Mobile）》新手友善攻略網站。
全球資料蒐集（韓國一手資料為主），做成像遊戲的單頁攻略站，可安裝為手機 App（PWA）。

## 專案結構
```
mabinogi-mobile/
├── site/                     ← 可部署的 App（GitHub Pages 部署此資料夾）
│   ├── index.html            ← 攻略網站（fetch 讀取 game-data.json）
│   ├── game-data.json        ← ⭐ 單一資料源（更新攻略只改這個檔）
│   ├── manifest.webmanifest  ← PWA 設定
│   └── icon.svg
├── data/
│   ├── sources.md            ← 全球資料來源清單
│   └── README.md             ← 架構說明
└── .github/workflows/deploy.yml  ← push 到 main 自動部署到 GitHub Pages
```

## 本機預覽
資料改用 fetch 讀取，**不能直接雙擊 index.html**，請透過伺服器開：
```bash
cd site
python -m http.server 8080
# 瀏覽器開 http://localhost:8080
```

## 更新攻略
只改 `site/game-data.json`，然後：
```bash
git add -A && git commit -m "更新攻略內容" && git push
```
GitHub Actions 會自動重新部署，網站與（未來的）App 資料一致。

## 收集回饋
在 `site/game-data.json` 的 `meta.feedbackUrl` 貼上 Google 表單／Tally 網址，
右下角就會出現「💬 回饋」按鈕；留空則隱藏。

## 資料來源
見 [data/sources.md](data/sources.md)。職業強度／Tier 屬社群人氣與版本評價，會隨賽季調整。
台港尚無官方在地版，內容以韓國版為準。

## 授權與聲明
本站為非官方新手攻略資訊整理。《瑪奇 Mobile》為 Nexon / devCAT Studio 所有。
