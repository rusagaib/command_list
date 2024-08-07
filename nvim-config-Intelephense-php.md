## SETUP nvim-lspconfig php intelephense

## Prerequisite

1. **Check Node.js Version**:
   Ensure that you are using a recent version of Node.js. Intelephense requires Node.js version 12 or higher.

   ```sh
   node --version
   ```

   If your Node.js version is below 12, you need to update it.

2. **Update Node.js**:
   If you need to update Node.js, you can do so using a version manager like `nvm` (Node Version Manager):

   Install nvm if you haven't already
   ```sh
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash
   ```

   Restart your terminal or source nvm script
   ```sh
   source ~/.nvm/nvm.sh
   ```

   Install the latest version of Node.js or specific Node.js

   latest:
   ```sh
   nvm install node
   ```

   specific (plz use Node.js v14+):
   ```sh
   nvm install v22.6.0
   ```

   Use the Node.js version: 
   ```sh 
   nvm use v22.6.0
   ```
   
   List all Node.js version
   ```sh
   nvm list
   ```

   Verify the Node.js version
   ```sh
   node --version
   ```

4. **Reinstall Intelephense**:
   Remove existing Intelephense:

   ```sh
   rm -rf ~/.local/share/nvim/mason/packages/intelephense
   rm -f ~/.local/state/nvim/lsp.log
   ```
   
   After updating Node.js, reinstall Intelephense using Mason:

   ```sh
   nvim
   :MasonInstall intelephense
   ```
5. **Locate Mason's Installation Directory**:
   Mason installs LSP servers under `~/.local/share/nvim/mason` by default. To find the path to the `intelephense` binary, navigate to this directory:

   ```sh
   cd ~/.local/share/nvim/mason/bin
   ```

6. **List Installed Binaries**:
   List the binaries in the directory to see if `intelephense` is present:

   ```sh
   ls -l
   ```

   You should see `intelephense` in the list of binaries.

7. **Check Executable Path**:
   Verify the path to the `intelephense` binary:

   ```sh
   which intelephense
   ```

   This command should return a path similar to:

   ```
   /home/yourusername/.local/share/nvim/mason/bin/intelephense
   ```

8. **Add Mason Bin Directory to `$PATH`**:
   Ensure that Mason's bin directory is included in your `$PATH`. Add the following line to your shell configuration file (e.g., `~/.bashrc`, `~/.zshrc`, etc.):

   ```sh
   export PATH="$HOME/.local/share/nvim/mason/bin:$PATH"
   ```

   Reload your shell configuration:

   ```sh
   source ~/.bashrc   # or ~/.zshrc
   ```

9. **Verify Executable**:
   Verify that `intelephense` is executable:

   ```sh
   intelephense --version
   ```

   This should display the version of Intelephense, confirming it is correctly installed and executable.

10. **Check LSP Configuration**:
   Ensure that your Neovim LSP configuration points to the correct `intelephense` binary. Here is an example configuration for `intelephense` with `nvim-lspconfig`:

     * it's lil messy code but it's work tho _(:3_|)_ : [./lua/plugins/lsp.lua](https://github.com/rusagaib/dotfiles/blob/main/nvim/lua/plugins/lsp.lua)
     * or for the complete: [my-nvim-config](https://github.com/rusagaib/dotfiles/blob/main/nvim/)

By following these steps, you should be able to ensure that the `intelephense` LSP is correctly installed, executable, and configured to work with Neovim.


