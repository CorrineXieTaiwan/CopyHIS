# 護理紀錄快捷器

## 功能特色

這是一個專為護理人員設計的護理紀錄生成工具，支援多種護理紀錄格式：

- 一般護理紀錄
- 護理計畫評值
- 手術護理紀錄
- 急診入院紀錄
- 單位轉入摘要

## 術語對照表管理

### 外部 JSON 檔案更新功能

系統現在支援透過外部 JSON 檔案來更新術語對照表，讓您可以輕鬆維護和更新醫療術語轉換規則。

#### 檔案結構

術語對照表儲存在 `medical_terms_mapping.json` 檔案中，格式如下：

```json
{
  "version": "1.0",
  "lastUpdated": "2025-01-27",
  "description": "醫療術語轉換對照表",
  "mappings": {
    "原始術語": "轉換後縮寫",
    "Blood gas analysis_動脈血氣體分析(送檢驗科執行)": "ABG",
    "Chest PA": "CXR",
    "Urine routine examination": "U/A"
  }
}
```

#### 如何更新術語對照表

1. **直接編輯 JSON 檔案**：
   - 開啟 `medical_terms_mapping.json`
   - 在 `mappings` 物件中新增或修改術語對照
   - 儲存檔案並重新部署到 GitHub

2. **透過系統設定頁面**：
   - 進入系統設定（需要密碼：0988374168）
   - 使用「匯出對照表」功能下載目前的設定
   - 編輯 JSON 檔案後使用「匯入對照表」功能

#### 部署到 GitHub 後的使用方式

當您將專案部署到 GitHub Pages 後：

1. **自動載入**：系統會在啟動時自動從 `medical_terms_mapping.json` 載入最新的術語對照表
2. **即時更新**：修改 JSON 檔案並推送到 GitHub 後，用戶重新整理頁面即可看到更新
3. **備用機制**：如果無法載入外部檔案，系統會自動使用內建的預設對照表

#### 如何測試上傳是否成功

1. **視覺確認**：
   - 頁面載入時會顯示右上角的綠色成功訊息
   - 訊息包含版本、更新時間和條目數量

2. **功能測試**：
   - 進入系統設定頁面查看對照表
   - 在急診入院紀錄中測試術語轉換功能
   - 檢查新增的測試項目是否出現

3. **開發者工具確認**：
   - 按 F12 開啟開發者工具
   - 查看 Console 中的載入訊息
   - 確認顯示「✅ 已從外部檔案載入 X 條術語對照」

4. **測試步驟**：
   - 將 `test_medical_terms_mapping.json` 重新命名為 `medical_terms_mapping.json`
   - 推送到 GitHub
   - 重新整理網頁
   - 檢查是否出現測試項目「【測試項目】新增測試術語」

#### 自定義對照表

- 用戶可以在系統設定中新增個人化的術語對照
- 自定義對照表會儲存在瀏覽器的 localStorage 中
- 自定義對照表會與外部載入的對照表合併使用

#### 檔案格式範例

```json
{
  "version": "1.0",
  "lastUpdated": "2025-01-27",
  "description": "醫療術語轉換對照表",
  "mappings": {
    "Blood gas analysis_靜脈血氣體分析(送檢驗科執行)": "VBG",
    "Blood gas analysis_動脈血氣體分析(送檢驗科執行)": "ABG",
    "Lactic Acid (lactate)": "Lactate",
    "Procalcitonin(PCT)": "PCT",
    "Sputum Culture + Sputum Routine aerobic culture": "Sputum C+R",
    "抗原快篩 - 新型冠狀病毒抗原檢測SARS-CoV-2 Ag test": "COVID-19(_)",
    "Chest PA": "CXR",
    "E.K.G.(左)(限病房執行)": "EKG",
    "Urine routine examination": "U/A",
    "(on Foley)留置導尿 Urinal indwelling catheterlization(病房專用)": "On Foley"
  }
}
```

## 使用說明

### 一般護理紀錄
1. 填寫病人基本資料（意識狀態、生命徵象等）
2. 設定氧氣系統參數
3. 新增滴注中藥物
4. 貼上管路資訊
5. 點擊「生成紀錄」按鈕

### 急診入院紀錄
1. 填寫病人基本資料和生命徵象
2. 貼上急診醫囑檢查處置
3. 點擊「生成紀錄」按鈕

### 系統設定
- 密碼：0988374168
- 可管理術語對照表
- 支援匯入/匯出功能

## 技術特色

- 響應式設計，支援各種螢幕尺寸
- 現代化 UI 設計，使用毛玻璃效果
- 本地儲存支援，保護用戶隱私
- 外部 JSON 檔案載入，便於維護更新

## 開發者

- 開發者：CorrineXie
- 版本：V1.2.0
- 更新日期：2025.07.05

## 授權

本專案僅供醫療專業人員使用，請遵守相關醫療法規和隱私保護規定。 