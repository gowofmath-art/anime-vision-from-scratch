# Anime Vision from Scratch

> 從矩陣、卷積與特徵圖出發，理解電腦如何「看見」動畫畫面。

## 專案簡介

`anime-vision-from-scratch` 是一個以**動畫畫面分析**為主題的電腦視覺學習專案。

這個專案最初的構想，是希望建立一套能夠分析動畫畫面的系統，並逐步探索：

- 動畫圖片在電腦中如何表示
- 卷積（Convolution）如何從畫面中提取特徵
- 不同卷積核（Kernel）會產生什麼樣的特徵圖（Feature Map）
- 未來如何進一步進行動畫畫面分類、作品辨識與視覺相似度分析

目前專案仍處於基礎研究與原型實作階段，尚未完成完整的動畫辨識模型。  
現階段的重點不是直接套用現成深度學習模型，而是從底層的矩陣運算開始，理解卷積神經網路處理影像的基本原理。

## 專案特色

本專案收錄的 Notebook，主要是我在自學機器學習、深度學習與電腦視覺過程中，親自整理的學習筆記與實作紀錄。

其中包含：

- 以自己的理解整理機器學習與深度學習概念
- 從像素、矩陣與張量理解數位圖片
- 不依賴深度學習框架，親手實作卷積運算
- 將卷積核實際套用於動畫畫面
- 觀察不同 Kernel 所產生的 Feature Map

這些內容並不是完整的教科書，也不是已完成的商業系統，而是我從零開始理解相關概念時，留下的推導、思考與程式實驗。

## Notebook 說明

所有 Notebook 依照學習順序放置於 `notebooks/` 資料夾中。

### 1. `機器學習與深度學習.ipynb`

機器學習與深度學習的基礎學習筆記。

主要內容包括：

- 機器學習與深度學習的差異
- 人工特徵工程與自動特徵提取
- 訓練集、驗證集與測試集
- 泛化能力與過擬合
- Regularization、Dropout、Data Augmentation、Early Stopping
- 梯度下降與高維函數逼近的基本理解
- 對深度學習黑箱性質的個人思考

這一份 Notebook 主要記錄我如何從數學與模型訓練的角度，建立對機器學習的初步理解。

### 2. `卷積練習.ipynb`

從零手刻二維卷積運算。

主要內容包括：

- Kernel 在圖片矩陣上的滑動過程
- 局部矩陣與 Kernel 的對應相乘與加總
- Feature Map 的輸出尺寸
- 使用純 Python 四層迴圈實作卷積
- 使用串列推導式簡化程式
- 使用 NumPy 實作矩陣卷積
- Identity、Blur、Sobel、Laplacian、Sharpen、Emboss 等經典 Kernel
- Kernel 總和、對稱性與功能之間的關係
- Kernel 大小、感受野與計算成本

嚴格來說，Notebook 中實作的是深度學習常用的 Cross-Correlation（互相關），但在實務上通常仍被稱為 Convolution。

這一份 Notebook 是本專案目前最核心的底層實作之一。

### 3. `圖轉矩陣.ipynb`

從矩陣與張量的角度理解數位圖片。

主要內容包括：

- 灰階圖片與彩色圖片的矩陣表示
- RGB 與 RGBA 色彩通道
- 圖片作為三維張量的數學意義
- 圖片縮放與插值法
- 將動畫截圖轉換為 NumPy 陣列
- 灰階影像與 RGB 影像的卷積實驗
- Feature Map 數值的意義與視覺化方法


### 4. `特徵圖.ipynb`

將不同卷積核套用於動畫畫面，觀察產生的特徵圖。

主要內容包括：

- 將動畫圖片縮放並轉換為 RGB 陣列
- 建立三維 RGB Kernel
- 對三個色彩通道進行卷積
- 特徵值正規化
- 垂直邊緣與水平邊緣偵測
- Gaussian Blur、Sharpen、Emboss 等效果
- 比較同一張動畫畫面經過不同 Kernel 後的 Feature Map

這一份 Notebook 將前面建立的矩陣與卷積概念，實際應用到動畫畫面的視覺分析。

## 專案結構

```text
anime-vision-from-scratch/
│
├─ README.md
├─ .gitignore
│
└─ notebooks/
   ├─ 1.機器學習與深度學習.ipynb
   ├─ 2.圖轉矩陣.ipynb
   ├─ 3.卷積練習.ipynb
   └─ 4.特徵圖.ipynb
```

## 使用技術

目前 Notebook 主要使用：

- Python
- Jupyter Notebook
- NumPy
- Pillow
- Matplotlib

## 執行方式

1. Clone 此專案：

```bash
git clone https://github.com/<your-username>/anime-vision-from-scratch.git
cd anime-vision-from-scratch
```

2. 安裝基本套件：

```bash
pip install numpy pillow matplotlib jupyter
```

3. 啟動 Jupyter Notebook：

```bash
jupyter notebook
```

部分 Notebook 需要自行準備圖片，並修改程式中的圖片路徑後才能重新執行。

## 圖片與著作權說明

本專案的研究主題涉及動畫畫面，但基於檔案容量與著作權考量，Repository 不提供大量原始動畫截圖或完整資料集。

部分 Notebook 可能保留先前執行時產生的輸出結果；若要重新執行影像相關程式，請自行準備合法取得的測試圖片，並修改對應的檔案路徑。

本專案中的動畫圖片僅用於個人學習、技術研究與非商業展示。

## 目前進度

目前已完成：

- [x] 機器學習與深度學習基礎概念整理
- [x] 圖片矩陣與 RGB 張量實驗
- [x] 純 Python／NumPy 手刻卷積
- [x] 經典 Kernel 實驗
- [x] 動畫畫面 Feature Map 視覺化
- [ ] 整理可重複使用的 Python 模組
- [ ] 建立動畫畫面資料處理流程
- [ ] 訓練第一個動畫畫面分類模型
- [ ] 實作視覺特徵向量與相似畫面搜尋
- [ ] 建立完整的動畫畫面分析系統

## 未來方向

未來希望在現有基礎上繼續發展：

1. 將 Notebook 中的卷積與圖片處理函式整理成獨立模組
2. 建立可重現的資料前處理流程
3. 使用 CNN 進行動畫作品或畫面分類
4. 利用特徵向量比較不同動畫畫面的相似程度
5. 探索動畫作品、製作公司或美術風格之間的視覺差異
6. 將分析結果整合成可操作的應用程式

## 專案定位

這不是一個已經完成的動畫辨識產品，而是一份持續發展中的學習型專案。

它記錄了我如何從：

> 圖片是一個矩陣  
> → Kernel 如何滑動與運算  
> → Feature Map 如何產生  
> → 電腦如何逐步提取畫面特徵

一步一步建立對電腦視覺與卷積神經網路的理解。

相比直接呼叫現成模型，我更希望先理解模型底層究竟做了什麼。  
這四份 Notebook，正是這段學習過程留下的第一階段成果。

---

**Current Stage：完成卷積與特徵圖的基礎實作，下一階段將朝動畫畫面分類與相似度分析發展。**
