# 班表 work-schedule

給長輩用的手機班表網頁（PWA），可以加到 Android 手機桌面當 App 用。

- 大字、一天一行，今天會用黃色標出來
- 兩個地點分開顯示（第一處 A・B 班、第二處 C・D 班）
- 平常鎖定，按「開始修改」才能改；改錯可以「復原」
- 放大字體、使用說明、新手教學、一步一步的操作教學
- 沒有網路也能打開（Service Worker 快取）

## 檔案

| 檔案 | 用途 |
| --- | --- |
| `index.html` | 整個網頁（HTML + CSS + JS 都在裡面） |
| `manifest.webmanifest` | PWA 設定：名稱、圖示、顏色 |
| `sw.js` | 離線快取 |
| `icons/` | App 圖示（一般、maskable、Apple） |
| `favicon.svg` | 瀏覽器分頁圖示 |

## 發佈

使用 GitHub Pages：Settings → Pages → Source 選 `Deploy from a branch`，Branch 選 `main` / `/ (root)`。

網址會是 `https://d0u0b.github.io/work-schedule/`。

## 更新版本

修改 `index.html` 後，把 `sw.js` 裡的 `VERSION` 加一（例如 `v1` → `v2`），手機下次連網打開就會拿到新版。

## 資料

班表資料存在手機瀏覽器的 localStorage，只在那支手機上，不會上傳。換手機或清除瀏覽器資料會不見。

## 測試日期

網址最後加 `#test-2026-12-05`，可以假裝今天是那一天。
