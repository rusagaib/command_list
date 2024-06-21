## VScodeVim Configs 🔥

### 1. Install vscodevim [vscodevim.vim](https://github.com/VSCodeVim/Vim) or from Extension Installer inside VScode

### 2. Enable leader-keys:

  - ( insert mode ) -> `ctrl+shift+p` -> Preferences: Open User Settings (JSON) -> enter
  - Copy-Paste:
  
  ```
  // inside settings.json
  {
  ...
      // init file explorer with leaderKeys space
      "vim.leader": "<space>",
      "vim.normalModeKeyBindings": [
        // ...
        {
          "before": ["<leader>", "e"],
          "commands": ["workbench.view.explorer"],
        },
      ],
      // vim plugin clipboard
      "vim.useSystemClipboard": true,
      // yank highlight
      "vim.highlightedyank.enable": true,
      "vim.highlightedyank.color": "#a9dc7660",
      "vim.highlightedyank.duration": 250,
  }
  ```
  
  - save

### 3. Setting keybinding

  - ( insert mode ) -> `ctrl+shift+p` -> Preferences: Open Keyboard Shortcuts (JSON) -> enter
  - Copy-Paste:

  ```
  // inside keybindings.json
  [
  ...
      {
          "key": "space e",
          "command": "workbench.action.toggleSidebarVisibility",
          "when": "filesExplorerFocus && !inputFocus"
      },
      {
          "key": "a",
          "command": "explorer.newFile",
          "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
      },
      {
          "key": "f",
          "command": "explorer.newFolder",
          "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
      },
      {
          "key": "r",
          "command": "renameFile",
          "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
      },
      {
          "key": "x",
          "command": "filesExplorer.cut",
          "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
      },
      {
          "key": "y",
          "command": "filesExplorer.copy",
          "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !inputFocus"
      },
      {
          "key": "p",
          "command": "filesExplorer.paste",
          "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceReadonly && !inputFocus"
      },
  ]
  ```

### 4. You can add more additional keybind shortcut on `keybinding.json` 

### 5. Finish 🔥

### Source 🍺
- [10 VS Code Vim Tricks to Boost Your Productivity ⚡](https://dev.to/ansonh/10-vs-code-vim-tricks-to-boost-your-productivity-1b0n)

