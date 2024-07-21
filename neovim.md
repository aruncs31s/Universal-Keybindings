# Neovim

## Telescope

```lua
  vim.api.nvim_set_keymap("n", "<A-b>", ":Telescope buffers<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<A-w>", ":Telescope live_grep<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<A-f>", ":Telescope current_buffer_fuzzy_find<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<A-o>", ":Telescope oldfiles<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<A-d>", ":Telescope find_files<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<A-z>", ":Telescope zoxide list<CR>", { noremap = true, silent = true }),
```
