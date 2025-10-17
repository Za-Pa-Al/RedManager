# RedManager

<p align="center">
    <a alt="total downloads">
        <img src="https://img.shields.io/github/downloads/Za-Pa-Al/RedManager/total" /></a>
    <a href="https://github.com/Za-Pa-Al/SaberFactory/releases" alt="latest version">
        <img src="https://img.shields.io/github/v/tag/ToniMacaroni/RedManager?label=version" /></a>
</p>

---

The RedManager is a general tool for installing/uninstalling/updating different features of the [RedLoader](https://github.com/ToniMacaroni/RedLoader) ecosystem as well as general Sons of the Forest modding features.

**:arrow_forward:[Original RedManager from ToniMacaroni](https://github.com/ToniMacaroni/RedManager):arrow_backward:**  
# Installation
Download RedModManager.exe and place the .exe in a folder OTHER then directly in "Sons Of The Forest\".
If placed next to file "Sons Of The Forest\SonsOfTheForest.exe" and subsequently next to folder "Sons Of The Forest\_Redloader", the .dlls in "Sons Of The Forest\_Redloader\" will likely cause a startup crash due to .NET conflicts.

For example you can safely place RedModManager.exe in "Sons Of The Forest\RedModManager\".

# Summary of Changes

## Overview

Enhancements to the RedModManager Tauri/Svelte application.

**User-Facing Improvements**

- **Visual Status System**: Immediate mod status recognition through color coding
- **Responsive Layout**: Optimal card display across all window sizes
- **Fast Image Loading**: Cached thumbnails with optimization
- **Window Memory**: Application remembers user's preferred size/position

## Technical

**Key Changes by Category**

**🏗️ Backend Infrastructure (Rust/Tauri)**

**Files Modified:**

- [Cargo.toml](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - Added window state persistence plugin
- [main.rs](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - Major expansion with image caching system
- [tauri.conf.json](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - Window configuration and security updates

**Major Features Added:**

- **Window State Persistence**: Integrated [tauri-plugin-window-state v0.1](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) for remembering user window size/position
- **Advanced Image Caching System**: Comprehensive image optimization and caching with:
  - Smart server change detection (ETag/Last-Modified headers)
  - Automatic image optimization (WebP conversion, thumbnail generation)
  - 24-hour cache expiration with graceful fallbacks
  - Memory and disk cache management
- **Updated Window Configuration**: 1400x900 default size, 600px minimum width

**🎨 Frontend UI/UX Enhancements (Svelte)**

**Files Modified:**

- [ModCard.svelte](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - Complete redesign with conditional styling
- [StatusButton.svelte](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - Color-coded button system
- [Mods.svelte](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - Grid layout optimization and search improvements
- [App.svelte](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - TypeScript improvements

**Major Features Added:**

- **Responsive Grid System**: Auto-fit layout with 420px minimum columns, preventing card overlap
- **Color-Coded Status Indicators**:
  - Install/Update buttons: Blue background (#0f1e2e)
  - Uninstall buttons: Red background (#2d0a0a)
  - Card backgrounds: Green for enabled mods, red for disabled
- **Optimized Image Display**: 220x120px forced dimensions with proper container overflow handling
- **Enhanced Search Interface**: Aligned with grid padding, improved button groups

**📦 Development Infrastructure**

**Files Added:**

- [launch.json](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - Tauri development configuration
- [tasks.json](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - Build and cleanup tasks
- [cleanup.bat](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) & [cleanup.ps1](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - Process cleanup scripts
- [imageCache.ts](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - Frontend image cache management
- [CacheDebugPanel.svelte](vscode-file://vscode-app/c:/Users/Alex/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) - Development debugging tools

**Features Added:**

- **Automated Development Workflow**: VS Code tasks for building, running, and cleanup
- **Process Management**: Smart cleanup scripts for development server conflicts
- **Debug Tools**: Cache debugging panel with memory usage statistics

**🔧 Performance & Stability**

**Key Improvements:**

- **Grid Position Stability**: Unique keys (mod.mod_id) prevent position shifting during operations
- **Optimized Refresh Logic**: Proper mod status synchronization with initModList() calls
- **Memory Management**: Intelligent image caching with size limits and automatic cleanup
- **Network Optimization**: Progressive image loading and preloading for better UX