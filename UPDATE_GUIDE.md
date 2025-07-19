# 術語對照表更新指南

## 🎯 快速更新流程

### 方法一：直接在 GitHub 上編輯（推薦）

1. **進入您的 GitHub Repository**
   - 開啟您的 GitHub 專案頁面
   - 找到 `medical_terms_mapping.json` 檔案

2. **編輯檔案**
   - 點擊檔案名稱進入檔案頁面
   - 點擊右上角的鉛筆圖示（Edit this file）
   - 修改 `mappings` 物件中的內容

3. **儲存變更**
   - 在頁面底部填寫 Commit 訊息，例如：「更新術語對照表」
   - 點擊「Commit changes」

4. **等待更新生效**
   - 等待 1-2 分鐘讓 GitHub Pages 重新部署
   - 重新整理您的網站頁面

### 方法二：上傳新檔案

1. **準備 JSON 檔案**
   - 在您的電腦上編輯 JSON 檔案
   - 確保檔案名稱為 `medical_terms_mapping.json`

2. **上傳到 GitHub**
   - 在 GitHub repository 中點擊「Add file」
   - 選擇「Upload files」
   - 拖拽或選擇您的 JSON 檔案
   - 點擊「Commit changes」

## 📝 檔案格式範例

### 基本格式
```json
{
  "version": "1.0",
  "lastUpdated": "2025-01-27T15:30:00.000Z",
  "description": "醫療術語轉換對照表",
  "mappings": {
    "原始術語": "轉換後縮寫"
  }
}
```

### 實際範例
```json
{
  "version": "1.1",
  "lastUpdated": "2025-01-27T15:30:00.000Z",
  "description": "醫療術語轉換對照表",
  "mappings": {
    "Blood gas analysis_動脈血氣體分析(送檢驗科執行)": "ABG",
    "Chest PA": "CXR",
    "Urine routine examination": "U/A",
    "【新增測試】": "TEST_NEW"
  }
}
```

## ✅ 如何確認更新成功

### 1. 視覺確認
- 重新整理網頁後，右上角會出現綠色成功訊息
- 訊息會顯示版本、更新時間和條目數量

### 2. 功能測試
- 進入系統設定頁面（密碼：0988374168）
- 查看對照表是否包含新的術語
- 在急診入院紀錄中測試術語轉換功能

### 3. 開發者工具確認
- 按 F12 開啟開發者工具
- 查看 Console 標籤
- 確認顯示「✅ 已從外部檔案載入 X 條術語對照」

## 🔧 常見問題

### Q: 為什麼更新後沒有立即生效？
A: GitHub Pages 需要 1-2 分鐘重新部署，請稍等後重新整理頁面。

### Q: 檔案格式錯誤怎麼辦？
A: 使用 JSON 驗證工具檢查格式，確保括號、逗號正確。

### Q: 如何新增術語對照？
A: 在 `mappings` 物件中新增新的鍵值對，例如：
```json
"新術語名稱": "新縮寫"
```

### Q: 如何刪除術語對照？
A: 從 `mappings` 物件中移除對應的鍵值對。

## 📋 更新檢查清單

- [ ] JSON 檔案格式正確
- [ ] 檔案名稱為 `medical_terms_mapping.json`
- [ ] 已推送到 GitHub
- [ ] 等待 1-2 分鐘讓 GitHub Pages 部署
- [ ] 重新整理網頁
- [ ] 檢查右上角成功訊息
- [ ] 測試功能是否正常

## 🚀 快速測試

1. 複製 `test_medical_terms_mapping.json` 的內容
2. 貼到 `medical_terms_mapping.json` 中
3. 推送到 GitHub
4. 重新整理網頁
5. 檢查是否出現測試項目「【測試項目】新增測試術語」 