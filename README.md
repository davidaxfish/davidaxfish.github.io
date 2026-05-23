# 飲食矩陣 — 部署指南

## 檔案結構

```
diet-matrix/
├── index.html      ← 前端（不需修改）
├── data.json       ← 後端資料庫（這裡更新食材）
└── README.md
```

## 部署到 GitHub Pages（零成本）

1. 建立新 repo（e.g. `diet-matrix`）
2. 上傳兩個檔案：`index.html` + `data.json`
3. Settings → Pages → Source: main branch / root
4. 網址：`https://你的帳號.github.io/diet-matrix/`

## 更新食材資料

只需編輯 `data.json`，前端自動讀取最新版本。  
無需改任何 HTML 或 JavaScript。

### 新增蛋白質食材範例
```json
{
  "id": "salmon",
  "name": "鮭魚(自煮)",
  "icon": "🐟",
  "time": 50,
  "sat": 85,
  "cost": 25,
  "protein": 20.2,
  "cal": 210,
  "prep": 15,
  "instant": false,
  "nocool": false,
  "plant": false,
  "satLevel": "很高",
  "note": "Omega-3 高，營養密度頂級。"
}
```

### 新增纖維食材範例
```json
{
  "id": "kale",
  "name": "羽衣甘藍",
  "icon": "🥬",
  "time": 35,
  "sat": 80,
  "cost": 50,
  "fiber": 3.6,
  "cal": 33,
  "prep": 5,
  "instant": false,
  "nocool": false,
  "highsat": true,
  "satLevel": "高",
  "note": "營養密度極高的葉菜類。"
}
```

## 待辦（下一版）

- [ ] 乳清蛋白品牌比較子表格（待資料收集後加入 `whey_brands` 欄位）
- [ ] 食材卡路里/蛋白質資料來源標注
- [ ] 使用者偏好記憶（localStorage）
- [ ] LINE LIFF 整合

## 欄位說明

### 蛋白質欄位
| 欄位 | 說明 |
|------|------|
| time | 時間效率 PR (0-100)，越高越省時 |
| sat | 飽足感 PR (0-100) |
| cost | 金錢成本 PR (0-100)，越高越便宜 |
| protein | 每份蛋白質(g) |
| cal | 每份熱量(kcal) |
| prep | 預處理時間(分鐘) |
| instant | 可即食 true/false |
| nocool | 免冷藏 true/false |
| plant | 植物性 true/false |
| isRange | 數值為範圍（如乳清蛋白）|
| subItems | 料理方式變體陣列（如雞蛋）|

### 纖維欄位
蛋白質欄位的 `protein` → `fiber`，`plant` → `highsat`
