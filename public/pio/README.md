# Spine 看板娘功能使用指南

## 功能說明

此功能為部落格添加了一個可配置的 Spine 動畫看板娘，可以顯示在頁面的角落位置。

## 配置選項

在 `src/config.ts` 檔案中的 `spineModelConfig` 物件包含以下配置選項：

```typescript
export const spineModelConfig: SpineModelConfig = {
  enable: false, // 是否啟用看板娘（預設關閉）
  model: {
    path: "/pio/models/shizuku/shizuku.model.json", // 模型檔案路徑
    scale: 1.0, // 模型縮放比例
    x: 0, // X 軸偏移
    y: 0, // Y 軸偏移
  },
  position: {
    corner: "bottom-right", // 顯示位置: "bottom-left" | "bottom-right" | "top-left" | "top-right"
    offsetX: 20, // 距離邊緣的 X 軸偏移（像素）
    offsetY: 20, // 距離邊緣的 Y 軸偏移（像素）
  },
  size: {
    width: 280, // 容器寬度（像素）
    height: 400, // 容器高度（像素）
  },
  interactive: {
    enabled: true, // 是否啟用互動功能
    clickAnimation: "tap_body", // 點擊時播放的動畫名稱
    idleAnimations: ["idle"], // 待機動畫列表
    idleInterval: 10000, // 待機動畫切換間隔（毫秒）
  },
  responsive: {
    hideOnMobile: true, // 是否在行動端隱藏
    mobileBreakpoint: 768, // 行動端斷點（像素）
  },
  zIndex: 1000, // CSS 層級
  opacity: 1.0, // 透明度（0.0-1.0）
};
```

## 檔案結構要求

要使用此功能，您需要準備以下檔案：

### 1. Spine 執行時庫

將 Spine 執行時 JavaScript 檔案放置在：
- `public/pio/static/spine-player.js`

您可以從以下來源取得：
- [Spine 官方執行時](http://esotericsoftware.com/spine-runtimes)
- [spine-ts 執行時](https://github.com/EsotericSoftware/spine-runtimes/tree/4.1/spine-ts)

### 2. Spine 模型檔案

將您的 Spine 模型檔案放置在：
- `public/pio/models/[模型名稱]/`

每個模型需要包含以下檔案：
- `[模型名稱].json` - Spine 骨骼資料檔案
- `[模型名稱].atlas` - 紋理圖集檔案
- `[模型名稱].png` - 紋理圖像檔案

例如，對於預設的 shizuku 模型：
- `public/pio/models/shizuku/shizuku.json`
- `public/pio/models/shizuku/shizuku.atlas`
- `public/pio/models/shizuku/shizuku.png`

## 啟用步驟

1. **準備 Spine 檔案**：將必要的檔案按照上述結構放置在 `public/pio/` 目錄中

2. **修改配置**：在 `src/config.ts` 中將 `spineModelConfig.enable` 設定為 `true`

3. **自訂設定**：根據您的需求調整其他配置選項

4. **測試功能**：重新建置並啟動專案，查看看板娘是否正常顯示

## 動畫配置

### 點擊動畫

設定 `clickAnimation` 為您模型中存在的動畫名稱，使用者點擊看板娘時會播放此動畫。

### 待機動畫

在 `idleAnimations` 陣列中添加多個動畫名稱，系統會按照設定的間隔隨機播放這些動畫。

### 常見動畫名稱參考

- `idle` - 待機動畫
- `tap_body` - 點擊身體
- `tap_head` - 點擊頭部
- `shake` - 搖擺動畫
- `flick_head` - 輕拍頭部

（具體動畫名稱取決於您的 Spine 模型檔案）

## 響應式設計

- 預設在行動端隱藏看板娘以提高性能
- 可以透過 `hideOnMobile` 和 `mobileBreakpoint` 配置響應式行為
- 支援視窗大小變化時的動態顯示／隱藏

## 故障排除

### 看板娘不顯示

1. 檢查 `enable` 是否設定為 `true`
2. 確認模型檔案路徑是否正確
3. 檢查瀏覽器主控台是否有錯誤訊息
4. 驗證 Spine 執行時檔案是否正確載入

### 動畫不播放

1. 檢查動畫名稱是否與模型檔案中的動畫符合
2. 確認模型檔案是否包含所需的動畫資料
3. 查看瀏覽器主控台的錯誤訊息

### 位置或大小問題

1. 調整 `position.offsetX` 和 `position.offsetY` 來微調位置
2. 修改 `size.width` 和 `size.height` 來調整容器大小
3. 使用 `model.scale` 來縮放模型本身

## 注意事項

- Spine 模型檔案可能較大，建議優化檔案大小以提高載入速度
- 在行動端預設隱藏以節省頻寬和提高性能
- 確保您有使用 Spine 模型的適當授權
- 某些瀏覽器可能需要使用者互動後才能播放動畫

## 取得 Spine 模型

您可以從以下渠道取得或製作 Spine 模型：
- [Spine 官方網站](http://esotericsoftware.com/)
- 各種開源 Live2D／Spine 模型資源
- 自製或委託製作

請確保您有合法使用權限的模型檔案。
