# 📱 智慧食材管理與食譜推薦系統 (Smart Food Management System)

> 🚀 **專為解決現代人食材浪費痛點所設計的 Android 應用程式**，提供從食材記錄、效期追蹤到食譜建議的一站式解決方案。

---

## 📖 專案簡介 (Project Overview)

**FoodApp** 是一款基於 Android 原生開發 (Java) 的智慧食材管理系統。在現代快節奏的生活中，人們經常忘記冰箱中存放的食材，導致食物過期與浪費。本系統旨在透過數位化的方式，幫助使用者有效管理庫存食材，並在食材即將過期時主動發出提醒。

此外，系統整合了網頁端的食譜搜尋功能，當使用者不知道如何處理剩餘食材時，可直接在 App 內尋找料理靈感，達成「零剩食」的永續目標。

## ✨ 核心功能 (Key Features)

### 1. 🔐 完善的使用者系統 (User Authentication)
* **註冊與登入** (`LoginActivity`, `RegisterActivity`)：透過本地 SQLite 資料庫安全地管理使用者帳號，保障個人資料的隱私。
* **個人資料管理** (`ProfileActivity`)：提供專屬的個人頁面與客製化設定。

### 2. 🥦 食材庫存管理 (Inventory CRUD)
* **新增與編輯** (`AddFoodActivity`, `EditFoodActivity`)：使用者可詳細記錄食材名稱、數量、購買日期與保存期限。
* **分類與列表展示** (`FoodListActivity`, `MainActivity`)：透過 `RecyclerView` 與自訂 `FoodListAdapter`，搭配 Material Design 與 Flexbox 排版，提供直覺、流暢的視覺體驗。

### 3. ⏰ 智慧效期提醒系統 (Smart Expiry Alerts)
* **背景推播通知** (`ExpiryReceiver`, `AlertActivity`)：利用 Android 的 `BroadcastReceiver` 與 `AlarmManager`，在食材到期前自動觸發提醒通知，防止食物浪費。

### 4. 🍳 食譜整合推薦 (Recipe Integration)
* **內建食譜瀏覽** (`RecipeWebViewActivity`)：透過 WebView 內嵌網頁技術，讓使用者能快速搜尋與當前庫存食材相關的料理食譜，隨看隨煮。

---

## 🛠️ 技術架構與使用工具 (Tech Stack)

* **開發語言**：Java 11
* **開發環境**：Android Studio, API Level 24 (Min) to 35 (Target)
* **資料庫**：SQLite (內建關聯式資料庫，使用 `FoodDatabaseHelper` 與 `UserDatabaseHelper` 實作資料持久化)
* **UI/UX 設計**：
  * Android Material Design Components (MDC)
  * Flexbox Layout (支援彈性響應式排版)
  * ConstraintLayout (建構高效能複雜視圖)
* **系統核心組件**：
  * `Activity` (生命週期與 UI 控制)
  * `BroadcastReceiver` (實作系統級背景排程任務)
  * `WebView` (跨平台網頁內容整合)

---

## 🚀 專案結構 (Project Structure)

```text
com.example.foodapp
├── db/                   # SQLite 資料庫操作與封裝
│   ├── FoodDatabaseHelper.java
│   └── UserDatabaseHelper.java
├── model/
│   └── FoodItem.java     # 食材資料模型 (POJO)
├── adapter/
│   └── FoodListAdapter.java # 列表適配器
└── activity/             # 視圖控制器 (Activity)
    ├── MainActivity.java
    ├── LoginActivity.java
    ├── AddFoodActivity.java
    ├── ExpiryReceiver.java  # 背景廣播接收器
    └── ...
```

---

## 💻 本地建置與執行 (Build Instructions)

1. 確認已安裝 **Android Studio** 以及對應的 Android SDK (API 35)。
2. 將本專案 Clone 至本地：
   ```bash
   git clone https://github.com/renkai09/java.git
   ```
3. 使用 Android Studio 開啟專案資料夾。
4. 點擊 `Sync Project with Gradle Files` 確保依賴套件 (如 Flexbox, Material UI) 下載完成。
5. 點擊 `Run 'app'` 部署至 Android 模擬器或實體手機。

---

## 🔮 未來展望 (Future Work)

本專案未來預計擴展以下功能，以提供更全面的服務：
1. **雲端資料同步**：將 SQLite 升級為 Firebase Realtime Database 或串接 RESTful API，實現跨裝置資料同步。
2. **AI 食譜推薦**：串接 OpenAI API，根據庫存食材自動生成客製化創意料理。
3. **條碼/發票掃描**：整合相機辨識技術 (OCR/Barcode)，實現一鍵快速匯入食材資訊，減少手動輸入成本。

---
*此專案為研究所推甄/專題展示作品，展示了在行動應用程式開發、本地資料庫設計以及系統架構規劃上的實作能力。*
