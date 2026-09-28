# 📦 Components 元件目錄

## 動態元件

- `widget/Dynamic.astro`：顯示最新動態的側邊欄元件。
- `pages/dynamic/DynamicFeed.svelte`：負責動態 JSON 載入、搜尋、年份篩選和分頁。
- `pages/dynamic/DynamicGallery.astro`：動態圖片網格、輪播和燈箱。
- `pages/dynamic/DynamicInlineComments.astro`：單條動態的按需評論區。
- `pages/dynamic/DynamicItem.astro`：動態項目的伺服器端渲染元件。
- `pages/dynamic/DynamicItemTemplate.astro`：動態項目的客戶端渲染範本。

Firefly 專案中所有可重複使用元件的集中管理。元件按照功能和職責分類，提供清晰的架構與易於維護的程式碼組織。

## 📁 目錄結構

### 🏗️ layout/ - 頁面版面元件

負責整體頁面框架和版面結構。

- `CategoryBar.astro` - 分類列元件
- `ConfigCarrier.astro` - 配置載體元件
- `DropdownMenu.astro` - 下拉選單元件
- `Footer.astro` - 頁尾元件
- `Navbar.astro` - 導覽列元件
- `NavMenuPanel.astro` - 導覽選單面板
- `PostCard.astro` - 文章卡片元件
- `PostMeta.astro` - 文章中繼資料元件
- `PostPage.astro` - 文章頁面版面元件
- `SideBar.astro` - 側邊欄元件

### 🎮 controls/ - 導覽與互動控制項

頁面導覽與使用者互動功能元件。

**導覽控制項**
- `BackToComment.astro` - 返回評論區按鈕
- `BackToHome.astro` - 返回首頁按鈕
- `BackToTop.astro` - 返回頂部按鈕
- `FloatingControls.astro` - 右下角浮動控制項容器
- `FloatingTOC.astro` - 浮動目錄元件
- `ScrollDownIndicator.astro` - 向下捲動指示器
- `ArchivePanel.astro` - 封存面板元件

**互動元件**
- `DisplaySettings.svelte` - 顯示設定元件
- `DisplaySettingsIntegrated.svelte` - 整合顯示設定元件
- `LayoutSwitchButton.svelte` - 版面切換按鈕
- `LightDarkSwitch.svelte` - 主題切換元件
- `Search.svelte` - 搜尋功能元件
- `WallpaperSwitch.svelte` - 桌布模式切換元件

### 🔧 common/ - 公共可重複使用元件

通用 UI 與工具元件，支援跨專案重複使用。

- `ButtonLink.astro` - 連結按鈕
- `ButtonTag.astro` - 標籤按鈕
- `DropdownItem.astro` / `.svelte` - 下拉選項
- `DropdownPanel.astro` / `.svelte` - 下拉面板容器
- `FloatingButton.astro` - 浮動按鈕基礎元件
- `Icon.svelte` - 圖示元件
- `WidgetLayout.astro` - 小工具版面容器
- `CoverImage.astro` - 封面圖元件
- `ImageWrapper.astro` - 圖片包裝器
- `Markdown.astro` - Markdown 內容樣式包裝器
- `PioMessageBox.astro` - 訊息框元件
- `Timeline.astro` / `TimelineItem.astro` - MDX 時間線元件
- `Steps.astro` / `StepItem.astro` / `Badge.astro` - MDX 內容元件

### 🧩 widget/ - 小工具

側邊欄中使用的各種功能小工具：廣告、公告、行事曆、分類、音樂播放器、個人資料、目錄、站點資訊、統計、Spine 看板娘與標籤元件。

### ✨ features/ - 全域功能特效元件

包含加密內容、Live2D、音樂播放器、櫻花特效、Spine 看板娘與打字機動畫等元件。

### 📃 pages/ - 頁面專用元件

特定頁面使用的元件，不用於其他頁面，包含進階搜尋、番組、相簿等元件。

### 💬 comment/ - 評論系統元件

第三方評論系統整合元件：Artalk、Disqus、Giscus、Twikoo 與 Waline。

### 📊 analytics/ - 資料統計元件

Google Analytics、51la、Microsoft Clarity 與 Umami 整合元件。

### 🔧 misc/ - 雜項工具元件

授權資訊、推薦文章與分享海報等輔助元件。
