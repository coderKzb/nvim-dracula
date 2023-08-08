![preview](./screenshot/preview.png)

## Features
- Beautiful UI
- Better replace
- Better search
- Better comment
- Better format
- LSP (Language server)
  - html/js/css
  - vue
  - c/c++
  - python
  - rust
  - go
  - java
  - lua
  - shell
- Code snappet
- Outline
- File browser
- Markdown preview
- Git integration
- Tmux integration
- Toogle terminal
- ...

## Requirements
- Neovim >= 0.5.0
- [ripgrep](https://github.com/BurntSushi/ripgrep)
- [fzf](https://github.com/junegunn/fzf)
- xclip(optional)

## Install
```sh
git clone https://github.com/Wjinlei/nvim.git ~/.config/nvim
```
### After Installation, You Need To
  - Python3 install `pynvim`
  - Nodejs install `neovim`
  - Install Nerd font
  - Do `:checkhealth`

## Keymap
### File browser
  - Open file browser `tt`
### Markdown preview
  - Open preview in default browser `<C-c>m` 
### Better comment
  - Comment current `gcc`
  - Comment select area `gc`
### Outline
  - Outline `C-m`
  - Outline next `C-j`
  - Outline prev `C-k`
### Better search
  - Search file `ff`
  - Search string `fs`
  - Search project file `fp`
  - Search git file `fg`
  - Search history file `fh`
  - Search buffer `bb`
  - Hop search `.` & `,`
### Better replace
  - Search and replace `fr`
  - Search and replace current word `fw`
### Git integration
  - Folding of unchanged text `gf`
  - Goto next hunk `gn`
  - Goto prev hunk `gp`
  - Git status `gs`
### LSP
> You must install a language server `<LEADER>lsp`
  - Goto prev diagnostic `<A-i>`
  - Goto next diagnostic `<A-n>`
  - Code action `<C-a>`
  - Goto definition `gd`
  - Goto implementation `gi`
  - Goto declaration `gt`
  - Format `<LEADER>f`
  - Smart rename `rn`
### Other
  - Toggle terminal `C-\`
  - Startup time `<C-c>s`
  - Sudo write `<LEADER>w`
  - Sudo read `<LEADER>r`
  - PackerInstall `<C-x>i`
  - PackerSync `<C-x>u`
  - PackerCompile `<C-x>x`

### Tmux integration 
Must be in `.tmux.conf `Add the following configuration to conf

<details>
  <summary>Click to expand</summary>

```sh
is_vim="ps -o state= -o comm= -t '#{pane_tty}' | grep -iqE '^[^TXZ ]+ +(\\S+\\/)?g?(view|n?vim?x?)(diff)?$'"

bind-key -n 'M-h' if-shell "$is_vim" 'send-keys M-h' { if -F '#{pane_at_left}' '' 'select-pane -L' }
bind-key -n 'M-j' if-shell "$is_vim" 'send-keys M-j' { if -F '#{pane_at_bottom}' '' 'select-pane -D' }
bind-key -n 'M-k' if-shell "$is_vim" 'send-keys M-k' { if -F '#{pane_at_top}' '' 'select-pane -U' }
bind-key -n 'M-l' if-shell "$is_vim" 'send-keys M-l' { if -F '#{pane_at_right}' '' 'select-pane -R' }

bind-key -T copy-mode-vi 'M-h' if -F '#{pane_at_left}' '' 'select-pane -L'
bind-key -T copy-mode-vi 'M-j' if -F '#{pane_at_bottom}' '' 'select-pane -D'
bind-key -T copy-mode-vi 'M-k' if -F '#{pane_at_top}' '' 'select-pane -U'
bind-key -T copy-mode-vi 'M-l' if -F '#{pane_at_right}' '' 'select-pane -R'

bind -n 'Left' if-shell "$is_vim" 'send-keys Left' 'resize-pane -L 1'
bind -n 'Down' if-shell "$is_vim" 'send-keys Down' 'resize-pane -D 1'
bind -n 'Up' if-shell "$is_vim" 'send-keys Up' 'resize-pane -U 1'
bind -n 'Right' if-shell "$is_vim" 'send-keys Right' 'resize-pane -R 1'

bind-key -T copy-mode-vi Left resize-pane -L 1
bind-key -T copy-mode-vi Down resize-pane -D 1
bind-key -T copy-mode-vi Up resize-pane -U 1
bind-key -T copy-mode-vi Right resize-pane -R 1
```

</details>

## Preview
Vue
![Vue](./screenshot/preview_000.png)
Rust
![Rust](./screenshot/preview_001.png)
Go
![Go](./screenshot/preview_002.png)
Shell
![Shell](./screenshot/preview_003.png)

## FAQ
1. 没有代码补全提示?
> 请确认是否安装对应语言的`lsp`服务器，使用`<LEADER>lsp`呼出面板安装即可。

2. 一些图标显示`?`号
> nerd fonts 字体问题，nerd fonts 3.0版本以上，移动了一些符号，导致某些图标显示不正常<br/>
升级到 nerd fonts 3.0 版本以上即可，写本文时，我用的版本是`3.0.2`

## Thanks to the authors of the following projects
- [ayamir](https://github.com/ayamir/nvimdots)
- [seagle0128](https://github.com/seagle0128/.emacs.d)
