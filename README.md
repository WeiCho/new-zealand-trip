# 紐西蘭旅程手冊

框架（`render.py`、`template/`、`_scripts.j2`、Actions）從首爾手冊（`WeiCho/seoul-trip`）複製，2026-10-29 另起；
外觀改成 langgenius.co.jp 的語法（滿版雪山封面、白底黑字、電光藍、直角），設計決定記在 `DESIGN.md`。
**樣板以本 repo 為準**，不要再從 seoul-trip 覆蓋回來。

- 資料：`trip.json` 是唯一來源，改完 push，`deploy.yml` 自動渲染部署。目前是空殼（日期、人數、行程都待補）。
- 導航：每站 `map_query` → 藍色 G 圓鈕開 Google 地圖（首爾版的 Naver `naver_query` 在這裡不用）。
- 記帳：紐幣 NZ$，可輸入小數；匯率是「1 紐幣 = 幾台幣」（`trip.fx.rate`，預設 19）。
- 天氣：`forecast.yml` 排程先關掉；日期定了以後要改 `scripts/update_forecast.py`（JMA MSM 不涵蓋紐西蘭、時區寫死 KST）再打開。
- 封面照：`template/_hero_image.j2`，Taranaki 火山（Pexels，Tyler Lastovich，https://www.pexels.com/photo/633198/），內嵌 WebP。
- 字型：英文 Inter Tight 內嵌在 `template/_latin_font.j2`（參考站的 Söhne 是付費字型）；中文用手機系統字。
