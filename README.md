# NLP 技術對比分析 (Traditional vs. Modern Methods)

本專案旨在比較傳統 NLP 方法（TF-IDF、規則式分類、統計式摘要）與現代生成式 AI 方法（GPT-4o）在語意相似度計算、文本分類與自動摘要任務上的效能差異。

## 📂 檔案結構

```text
114971025_hw2/
│
├── traditional_methods.ipynb   # Part A: 傳統方法實作 (TF-IDF, Rule-based)
├── modern_methods.ipynb        # Part B: 現代 AI 方法實作 (OpenAI API)
├── comparison.ipynb            # Part C: 比較分析主程式 (執行此檔以產出報告)
├── report.md                   # 完整分析報告 (含量化數據與質性分析)
├── results/                    # 程式執行後自動產出的結果資料夾
│    ├── tfidf_similarity_matrix.png   # TF-IDF 相似度矩陣圖
│    ├── classification_results.csv    # 分類結果明細
│    ├── summarization_comparison.txt  # 摘要結果對比文字檔
│    └── performance_metrics.json      # 效能指標原始數據
├── requirements.txt            # 專案依賴套件列表
├── README.md                   # 專案執行說明 (本檔案)
````
<br>
<br>

# 🛠️ 環境需求
本專案建議於 Google Colab 環境下執行。

## 1. 必要套件
主要依賴套件列於 requirements.txt 中：

jieba

openai

pandas

numpy

matplotlib

seaborn

scikit-learn

python-dotenv

## 2. OpenAI API 金鑰設定 (重要！)
由於 Part B (現代AI方法) 需要呼叫 OpenAI API，請務必在執行前設定 API Key：

在 Google Colab 左側選單點擊 「鑰匙」圖示 (Secrets)。

新增一個 Secret：

名稱 (Name): OPENAI_API_KEY

值 (Value): sk-...... (您的 OpenAI API Key)

啟用該 Secret 的 "Notebook access" 權限。

注意：程式碼中使用 from google.colab import userdata 來安全讀取金鑰，請勿直接將金鑰貼在程式碼中。

## 3. 中文字型
comparison.ipynb 程式碼內建自動下載 SimHei.ttf 字型的功能，以解決 matplotlib 繪圖時的中文亂碼問題，您無需手動安裝字型。

### 🚀 執行步驟
請依照以下順序執行程式：

上傳檔案：將所有 .ipynb 檔案上傳至 Google Colab 或 Google Drive 的同一個資料夾中。

開啟主程式：依序打開 traditional_methods.ipynb, modern_methods.ipynb, comparison.ipynb。

執行：點擊選單中的 「執行階段」 -> 「全部執行」 (Run all)。

說明： traditional_methods.ipynb為傳統作法，modern_methods.ipynb為現代AI作法，comparison.ipynb 為比較分析並生成結果。

### 📊 產出結果
執行完成後，results/ 資料夾內將自動生成以下檔案：

tfidf_similarity_matrix.png: 視覺化的 TF-IDF 文本相似度熱力圖。

classification_results.csv: 傳統方法的分類結果與匹配分數、 AI 方法的分類結果與信心度。

summarization_comparison.txt: 兩種方法生成的摘要文本對照。

performance_metrics.json: 兩種方法的效能指標原始數據
