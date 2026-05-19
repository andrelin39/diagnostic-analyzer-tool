# 醫學診斷指標分析工具
**Diagnostic Test Accuracy Analyzer**

一個純前端、免安裝的醫學診斷指標互動分析工具，可直接在瀏覽器中執行，無需後端伺服器。

🔗 **線上使用**：[GitHub Pages](https://andrelin39.github.io/diagnostic-analyzer-tool/)

---

## 功能

- 上傳資料檔案（支援 `.csv` / `.tsv` / `.xlsx` / `.xls`）
- 自訂金標準（Reference Standard）與測試工具（Index Test）欄位
- 彈性設定陽性值條件（支援多值）
- 自動產生 **2×2 列聯表**
- 計算八項診斷指標：

| 指標 | 說明 |
|------|------|
| Sensitivity | 敏感度 |
| Specificity | 特異度 |
| PPV | 陽性預測值 |
| NPV | 陰性預測值 |
| Accuracy | 整體準確率 |
| LR+ | 陽性似然比 |
| LR− | 陰性似然比 |
| Cohen's κ | 一致性係數（含 Landis & Koch 等級判讀） |

- **分組比較分析**：可選一個或多個分組變數（如醫師、判讀方式），自動計算所有組合的診斷指標
- 一鍵複製結果 / 列印 PDF

---

## 資料格式

第一列須為欄位標頭，每列一筆記錄。

**CSV 範例：**
```
id,reference,diagnosis,doctor,method
1,positive,positive,Dr.A,CT
2,negative,negative,Dr.B,MRI
3,positive,negative,Dr.A,MRI
```

**欄位值**可以是任何字串（`1/0`、`yes/no`、`陽性/陰性` 均可），上傳後在介面中點選哪個值算「陽性」即可。

---

## 使用方式

### 線上版（推薦）
直接開啟 GitHub Pages 連結，無需安裝任何套件。

### 本機版
下載 `index.html`，用任何瀏覽器開啟即可（需連網以載入 SheetJS 函式庫支援 Excel 格式）。

---

## 技術

- 純 HTML / CSS / JavaScript，無框架依賴
- Excel 解析：[SheetJS](https://sheetjs.com/)（CDN 載入）
- 字型：Google Fonts（DM Sans、DM Mono、Instrument Serif）

---

## 參考文獻

- Landis JR & Koch GG (1977). The measurement of observer agreement for categorical data. *Biometrics*, 33(1), 159–174.
