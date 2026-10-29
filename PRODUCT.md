# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

使用者本人與旅伴（人數待定），紐西蘭旅行（日期待定）。兩種情境：出發前在電腦上排行程；旅途中用手機單手查「現在去哪、怎麼去、幾點到」。紐西蘭郊區網路常不穩，頁面要能離線開。

## Product Purpose

把整趟紐西蘭旅程（行程、交通、口袋名單、記帳、出發前檢查、緊急聯絡）編成一份單一 HTML 手冊，部署在 GitHub Pages。改行程只改 trip.json。

## Positioning

只屬於這趟旅程的口袋刊物，不是訂票 App、不是待辦清單。

## Operating Context

- 資料：`trip.json`。
- 版面：`template/itinerary.html.j2` + `render.py`（從首爾手冊複製，導航改 Google 地圖、記帳改紐幣）。
- 頁內功能：換日、今日模式（紐西蘭時間）、交通分頁、口袋名單、NZ$ 記帳（localStorage）、出發前清單、緊急聯絡彈窗、深色切換、`?edit=1` 編輯器。

## Brand Commitments

- 2026-10-29：使用者指定 https://langgenius.co.jp/ 的風格，封面要「這種大山」（滿版雪山照）。
- 字級要克制（首爾版時使用者說過大字標題手機會爆版）。

## Product Principles

1. 任何時刻掃一眼就能回答「現在去哪、怎麼去、幾點到」。
2. 資料與外觀分離：改版只動樣板，trip.json 不動。
3. 一份檔案就是全部：離線可讀。

## Accessibility & Inclusion

- 內文對比 ≥ 4.5:1；觸控目標 ≥ 44px；`prefers-reduced-motion` 提供無動畫版本；封面白字下有壓暗漸層。
