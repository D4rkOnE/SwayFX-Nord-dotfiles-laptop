# Welcome to the dotfiles of my Nord themed SwayFX Archlinux setup
By now you probably figured out I like playing around with different window managers and wayland compositors.  

The file config.tar.gz contains the entire contents of ~/.config including the Sway config, Waybar config, GTK3 and GTK4 config, Alacritty config, Rofi config etc.

## Nord theme for Neovim
Install neovim first, then install LazyVim: ```git clone https://github.com/LazyVim/starter ~/.config/nvim```.  The file ~/.config/nvim/init.lua should contain:
```-- bootstrap lazy.nvim, LazyVim and your plugins
require("config.lazy")
```
Create a file ~/.config/nvim/lua/config/config.lazy with the following content:
```
require("lazy").setup({
  {"nvim-treesitter/nvim-treesitter", branch = 'master', lazy = false, build = ":TSUpdate"}
})
```
Finally creata a file ~/.config/nvim/lua/plugins/colorscheme.lua with the following content:
```
return {
  { "shaunsingh/nord.nvim" },

  {
    "LazyVim/LazyVim",
    opts = {
      colorscheme = "nord",
    },
  },
}
```

## Nord theme for vim
Install vim first.  Then create a file ~/.vimrc with the following content:
```
call plug#begin()
Plug 'arcticicestudio/nord-vim'
call plug#end()

colorscheme nord
```

![Clean screenshot](https://github.com/D4rkOnE/SwayFX-Nord-dotfiles-laptop/blob/main/clean.png)

![Busy](https://github.com/D4rkOnE/SwayFX-Nord-dotfiles-laptop/blob/main/busy.png)

![Busy rofi](https://github.com/D4rkOnE/SwayFX-Nord-dotfiles-laptop/blob/main/busy_rofi.png)
