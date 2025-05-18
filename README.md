# User-Specific "Open with IDE" Context Menu

This project provides a `.reg` file (`hkcu_open_ide.reg`) to add user-specific "Open with IDE" entries to the Windows Explorer right-click context menu. These entries will only be available for the current user.

The script adds context menu options for:
- **Folder Background:** Right-clicking in the empty space within a folder ("Open Current Folder in IDE").
- **Folders:** Right-clicking directly on a folder ("Open Folder in IDE").
- **Files:** Right-clicking on any file ("Open with IDE" - opens the file directly).

The examples in the `.reg` file use Visual Studio Code (`code` and `Code.exe`) but can be easily adapted for other IDEs.

![](https://github.com/spaansba/Quickly-Open-IDE/blob/main/static/example.gif)

## Prerequisites

1.  **Your Preferred IDE Installed:** Ensure your chosen IDE (e.g., Visual Studio Code) is installed on your system.
2.  **IDE in User's PATH:** Your IDE's command-line launcher (e.g., `code.exe` for VS Code) **must be** in your user's PATH environment variable for the scripts to work as intended. 
3.  **PowerShell:** Windows comes with PowerShell pre-installed.

## How to Use the `hkcu_open_ide_combined.reg` File

1.  **Download the .reg File:** Download the `hkcu_open_ide.reg` file in this repository.
2.  **Modify the file:**
    - Edit (dont left click open) the downloaded `hkcu_open_ide.reg` by right-clicking it and clicking "edit"
    - **Icon Path:**
      - The default icon path in the file is `"C:\\Users\\YOURUSERNAME\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe,0"`. **You MUST replace `YOURUSERNAME` with your actual Windows username.**
    - **Display Name:**
      - You can change the text that appears in the context menu by modifying the `@="..."` lines for each entry (e.g., `@="Open in My Favorite IDE"`).
3.  **Apply the `.reg` file:**
    - Double-click the modified `hkcu_open_ide.reg` file.
    - You will be asked to confirm that you want to add the information to the registry. Click "Yes".
4.  **Test It:** Right-click in a folder background, on a folder, or on a file in Windows Explorer.
5.  **Deleted it:** You can delete the `.reg` file ones it works.

## Troubleshooting

- **Entry Not Appearing / Icon Missing:**
  - **Replace `YOURUSERNAME`:** Double-check that you replaced `YOURUSERNAME` in the icon path(s) within the `.reg` file with your actual Windows username.
- **PowerShell Window Flashes Briefly:** The `-NoProfile -WindowStyle Hidden` options minimize this, but it can still occur on some systems.
