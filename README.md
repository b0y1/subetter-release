# Subetter

用影片字幕与音轨学习外语。

## 下载

请在 [Releases](https://github.com/b0y1/subetter-release/releases) 下载对应系统的安装包。

- Windows：x64，Windows 10 22H2；下载 `.exe` 安装程序。
- macOS：macOS 15 及以上，Intel 与 Apple Silicon 通用；下载 Universal `.dmg`。

更新应用会保留已有任务和影片数据。安装包目前未进行 Windows 代码签名或 Apple 公证。

## 通过 Homebrew 安装（macOS）

如果你使用 [Homebrew](https://brew.sh)，可以直接用一行命令安装 macOS 版 Subetter——与上面的 Universal `.dmg` 是**同一个安装包**，只是改由 Homebrew 下载、安装与管理：

```bash
brew install --cask b0y1/taps/subetter
```

安装后 Subetter 位于 `/Applications/Subetter.app`。

### 注意事项

- **先信任 tap（Homebrew 7 起）**：非官方 tap 的 cask 需先被信任才会加载。用上面的完整名字安装时 Homebrew 会自动记下信任，通常无需额外操作；若想用短名字（`brew install --cask subetter`）或希望 `brew outdated` / `brew upgrade` 不报错，先信任一次：

  ```bash
  brew trust --tap b0y1/taps
  ```

  撤销：`brew untrust --tap b0y1/taps`。若看到 `Refusing to load cask b0y1/taps/subetter from untrusted tap b0y1/taps.`，执行上面的 `brew trust` 即可。

- **未做 Apple 公证**：安装时会自动去掉隔离标记，一般可直接打开。若仍提示「已损坏」，手动执行一次：

  ```bash
  xattr -dr com.apple.quarantine /Applications/Subetter.app
  ```

- **更新与卸载**：

  ```bash
  brew upgrade --cask subetter            # 升级到新版本
  brew uninstall --cask subetter          # 仅卸载 App
  brew uninstall --cask --zap subetter    # 连应用数据一起清理（见下）
  ```

- **应用数据位置**：`~/Library/Application Support/app.subetter.desktop`。用 `--zap` 卸载会一并清理该目录及偏好设置、缓存与日志；普通卸载只删 App，保留你的任务与影片数据。

本仓库仅用于分发安装包与版本说明。
