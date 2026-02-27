# 🚀 ccp-test

在 VSCode / Visual Studio 開發 C++ 的測試專案。

## 🛠️ 如何執行 (How to Run)

這個專案是一個標準的 C++ 主控台應用程式，您可以選擇以下幾種方式執行：

### 1. 使用 Visual Studio (推薦) 💻
這是最簡單且穩定的方式：
1. 使用 Visual Studio 打開 `ConsoleApplication1.sln`。
2. 按下 **`Ctrl + F5`** (啟動但不偵錯) 或 **`F5`** (開始偵錯)。
3. 如果出現版本不相符的提示，請點擊「確定」進行專案重定目標 (Retarget)。

### 2. 使用 VSCode ⚡
1. 確保已安裝 **C/C++** 擴充功能與 **MSVC 編譯器**。
2. 在 VSCode 中開啟此資料夾。
3. 切換到「執行與偵錯」面板，選擇 **(Windows) Launch**。
    > 注意：VSCode 偵錯需要先確保 `x64/Debug/` 下已有編譯好的 `.exe`。

### 3. 使用命令列 (MSBuild) ⌨️
如果直接執行 `msbuild` 報錯，通常是因為路徑未設定或工具版本不符。

**解決步驟：**
1. **設定路徑** (僅限該視窗有效)：
   ```powershell
   $env:Path += ";D:\Program Files\Microsoft Visual Studio\18\Community\MSBuild\Current\Bin"
   ```
2. **編譯專案**：
   如果遇到 `MSB8020` (找不到 v143) 錯誤，請指定您電腦安裝的工具版本 (例如 `v145`)：
   ```powershell
   msbuild ConsoleApplication1.sln /p:Configuration=Debug /p:Platform=x64 /p:PlatformToolset=v145
   ```

**常見錯誤排查：**
*   **MSB8020**：代表專案設定的 Visual Studio 版本與您安裝的不符。請在 VS 中「右鍵點擊方案 > 重定方案目標」或在指令加入 `/p:PlatformToolset=v145`。
*   **無法辨識 msbuild**：請確認路徑是否正確加入，或使用 **Developer PowerShell**。

## 📂 專案結構
*   `ConsoleApplication1.cpp`: 程式主入口 (Hello World)。
*   `.sln` / `.vcxproj`: Visual Studio 專案與方案設定檔。
*   `.vscode/`: VSCode 編輯器設定 (Launch / Tasks)。

---
*Powered by Antigravity AI* 🪐
