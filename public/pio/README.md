# Spine 看板娘功能使用指南

## 功能說明

此功能為部落格新增可配置的 Spine 動畫看板娘，可以顯示在頁面角落。

## 配置選項

`src/config.ts` 檔案中的 `spineModelConfig` 物件包含以下配置選項：

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
    corner: "bottom-right", // 顯示位置
    offsetX: 20, // 距離邊緣的 X 軸偏移（像素）
    offsetY: 20, // 距離邊緣的 Y 軸偏移（像素）
  },
  size: { width: 280, height: 400 }, // 容器尺寸（像素）
  interactive: {
    enabled: true, // 是否啟用互動功能
    clickAnimation: "tap_body", // 點擊時播放的動畫名稱
    idleAnimations: ["idle"], // 待機動畫列表
    idleInterval: 10000, // 待機動畫切換間隔（毫秒）
  },
  responsive: {
    hideOnMobile: true, // 是否在行動裝置上隱藏
    mobileBreakpoint: 768, // 行動裝置斷點（像素）
  },
  zIndex: 1000, // CSS 層級
  opacity: 1.0, // 透明度（0.0-1.0）
};
```

## 檔案結構要求

使用此功能需要準備以下檔案：

### 1. Spine 執行時期函式庫

將 Spine 執行時期 JavaScript 檔案放置於 `public/pio/static/spine-player.js`。

### 2. Spine 模型檔案

將模型檔案放置於 `public/pio/models/[模型名稱]/`，每個模型需要包含 JSON、atlas 和 PNG 檔案。

## 啟用步驟

1. 將必要的 Spine 檔案放入 `public/pio/` 目錄。
2. 在 `src/config.ts` 中將 `spineModelConfig.enable` 設定為 `true`。
3. 依需求調整其他配置選項。
4. 重新建置並啟動專案，確認看板娘是否正常顯示。

## 動畫配置

- 將 `clickAnimation` 設定為模型中存在的動畫名稱。
- 在 `idleAnimations` 陣列中加入動畫名稱，系統會按指定間隔隨機播放。
- 常見動畫：`idle`（待機）、`tap_body`（點擊身體）、`tap_head`（點擊頭部）、`shake`（搖擺）、`flick_head`（輕拍頭部）。

## 響應式設計

- 預設在行動裝置上隱藏看板娘以提升效能。
- 可透過 `hideOnMobile` 和 `mobileBreakpoint` 配置響應式行為。
- 支援視窗大小變更時動態顯示或隱藏。

## 故障排除

### 看板娘不顯示

1. 檢查 `enable` 是否設定為 `true`。
2. 確認模型檔案路徑是否正確。
3. 檢查瀏覽器主控台是否有錯誤訊息。
4. 確認 Spine 執行時期檔案是否正確載入。

### 動畫不播放

1. 檢查動畫名稱是否與模型檔案中的動畫相符。
2. 確認模型檔案包含所需的動畫資料。
3. 查看瀏覽器主控台的錯誤訊息。

## 注意事項

- Spine 模型檔案可能較大，建議最佳化檔案大小。
- 行動裝置預設隱藏以節省頻寬並提升載入速度。
- 確保擁有使用 Spine 模型的適當授權。
