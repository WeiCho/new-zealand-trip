# 紐西蘭旅程手冊

日期、人數、住宿都還沒定（`trip.json` 目前是 5 天空殼，日期 2027-01-01 起是佔位）。
線上：<https://weicho.github.io/new-zealand-trip/>（**public repo**）。使用者常從手機 Claude App 下指令，回覆用繁體中文、簡短。

## 流程

1. 開工先 `git pull`。
2. 只改 `trip.json`（唯一的資料來源）。要動樣板才碰 `template/`、`render.py`，樣板以本 repo 為準。
3. 驗證：`pip install "jinja2>=3.1"`，`python render.py .`，沒有錯誤、看一下「⚠ 排太緊」警告並回報。產出的 `行程表.html`、`index.html` 等在 `.gitignore`，不要 commit。
4. **改完就 commit & push，不用問。** push 被拒就 `git pull --rebase` 再推。
5. push 後 `deploy.yml` 自動渲染部署，約 1–2 分鐘上線。回報時說改了哪一天、哪幾站。

## 資料規則

- **不寫訂位代號、保單號、護照號碼等個資**（repo 是 public）。
- 每天 `theme` 只寫地區，不寫長串店名。
- 每天第一站是住宿（type「住宿」、「從住處出發」），最後一站「回住處」；抵達日第一站是機場，回國日以航班結束。
- `transit[].at` 是「從哪一站出發」的時間，不是目的地。改了站的時間，要一起檢查前後的 transit `at` 與 `next_transit`。
- 一天景點／購物別超過 3 個（render.py 會警告）。
- 每站要有 `map_query`（英文地名或地址，用來開 Google 地圖的藍色 G）；航班、搭車中不放。
- 彈窗只放 1–2 句 `note`、停留 `duration`、營業 `booking.hours`、下一站 `next_transit`；不加官網或其他連結。
- 重要景點與餐廳加 `photo`（img／alt／credit），用該地本身的照片，credit 標拍攝者與來源。
- 金額用紐幣（NZ$），`trip.fx.rate` = 1 紐幣幾台幣。

## 設計

看 `DESIGN.md`：langgenius.co.jp 的語法；字不要大、畫面乾淨、iPhone 優先。
