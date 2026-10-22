# ALM 測試工具

讓 HP ALM 11 不再只能用 IE 操作：執行測試、上傳截圖、建立與追蹤議題，並產出 Excel 測試報告。

## 下載

到 [Releases](https://github.com/chungtsai/hp-alm/releases) 下載最新的 `ALM-Desktop-<版號>.zip`。

- 一般使用者請下載**正式版**（Latest）
- 標示為 **Pre-release** 的是測試版，供測試人員使用

## 安裝與使用

1. 把 ZIP 解壓縮到自己的資料夾，例如 `D:\tool\ALM-Desktop`
2. 執行 `ALM-Desktop.exe`
3. 在「連線設定」輸入公司的 ALM 網址並登入。勾選「記住」後，之後就不用再輸入
4. 第一次使用時，如果畫面上方出現「找不到 ALM OTA 元件」，請先登入一次，再按「安裝 OTA 元件」（需要系統管理員權限）

## 系統需求

- Windows 10 或 11
- 可以連到公司的 HP ALM 伺服器

## 更新

程式每次啟動都會檢查有沒有新版本。有新版時，畫面上方會出現提示，按「立即更新」，程式會自動下載、驗證、更新並重新啟動。

## 常見問題

**v1.0.0 啟動時出現「Failed to resolve Python.Runtime.Loader.Initialize」**

原因是 Windows 把下載的檔案標記為「來自網際網路」，舊版程式因此無法載入元件。請改用 v1.0.1 以後的版本（已自動處理這個問題）。如果要繼續使用 v1.0.0，請在 PowerShell 執行以下指令解除封鎖：

```powershell
Get-ChildItem "<解壓縮的資料夾>" -Recurse | Unblock-File
```

## 檔案驗證

每個版本都附有 `.sha256` 檔。可以在 PowerShell 執行下面的指令，確認下載的檔案沒有被修改過：

```powershell
Get-FileHash .\ALM-Desktop-<版號>.zip -Algorithm SHA256
```
