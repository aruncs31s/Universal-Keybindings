# Universal-Keybindings

All of my keybindings set to universal from i3 to mate
[Neovim](neovim.md)

## Universal

Mod -> `super` or `windows key` , mod4 in the case of `i3` and `alt` in the case of `tmux` and `neovim`
| Combination | Use | Used By |
| ----------- | ------- | ------- |
| Mod + w | Item2.1 | -- |
| Item1.2 | Item2.2 | -- |

## Neovim

### Telescope

```lua
  vim.api.nvim_set_keymap("n", "<A-b>", ":Telescope buffers<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<A-w>", ":Telescope live_grep<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<A-f>", ":Telescope current_buffer_fuzzy_find<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<A-o>", ":Telescope oldfiles<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<A-d>", ":Telescope find_files<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<A-z>", ":Telescope zoxide list<CR>", { noremap = true, silent = true }),
```

### Obsidian

```lua
  vim.api.nvim_set_keymap("n", "<Leader>of", ":ObsidianSearch<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<Leader>ol", ":ObsidianFollowLink<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<Leader>oo", ":ObsidianOpen<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<Leader>op", ":ObsidianPasteImg<CR>", { noremap = true, silent = true }),
```

### Navigation

```lua
  vim.api.nvim_set_keymap("v", "<A-h>", ":bp<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("v", "<A-l>", ":bn<CR>", { noremap = true, silent = true }),
```

### Quick Fix

```lua
  vim.api.nvim_set_keymap("n", "<Leader>qn", ":cnext<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<Leader>qq", ":cclose<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<Leader>qo", ":copen<CR>", { noremap = true, silent = true }),
  vim.api.nvim_set_keymap("n", "<Leader>qp", ":cprevious<CR>", { noremap = true, silent = true }),
```

## Tmux

```bash
# Zoom selected pane

bind -n M-f resize-pane -Z
# Open Clock
bind -n M-t clock-mode

# Rotate window
bind -n M-r rotate-window

## Splitting Windows
bind -n M-v splitw
bind -n M-g splitp -h
bind -n M-V split-window -f -l 10

# Window chooser

bind -n M-w choose-window

# reload the config
bind C-r source ~/.tmux.conf

# Create New Window
bind -n M-c neww

# Create New Session
bind -n M-x new-session

### open obsidian with default file
bind -n M-n display-popup -E "nvim ~/Notes/Public/Linux/Linux_Quick_Notes.md"

bind -n M-N display-popup -E "nvim $(fzf)"

# Switch to fav session
# bind -n M-o new-session -A -s Obsidian
# bind -n M-T new-session -A -s Git
# bind -n M-t new-session -A -s Term



# Toggle the Status bar
bind -n M-u set -g status off
bind -n M-U set -g status on


# bind h select-pane -L
# bind j select-pane -D
# bind k select-pane -U
# bind l select-pane -R
#

# Use Alt-arrow keys without prefix key to switch panes
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D

bind -n M-h select-pane -L
bind -n M-l select-pane -R
bind -n M-k select-pane -U
bind -n M-j select-pane -D

# swap panes

bind -n M-J swap-pane -D
bind -n M-K swap-pane -U


# Shift arrow to switch windows
bind -n S-Left  previous-window
bind -n S-Right next-window

# Shift Alt vim keys to switch windows
bind -n M-H previous-window
bind -n M-L next-window

### i3 Like Window Switching

bind -n M-1 select-window -t 1
bind -n M-2 select-window -t 2
bind -n M-3 select-window -t 3
bind -n M-4 select-window -t 4
bind -n M-5 select-window -t 5
bind -n M-6 select-window -t 6
bind -n M-7 select-window -t 7
bind -n M-8 select-window -t 8
bind -n M-9 select-window -t 9
bind -n M-0 select-window -t 10

# Tmux fzf
bind -n M-d run-shell "/home/aruncs/.tmux/plugins/tmux-fzf/main.sh"
bind -n M-s run-shell "/home/aruncs/.tmux/plugins/tmux-fzf/scripts/session.sh switch"

# bind -n M-f run "fzf-tmux"

TMUX_FZF_LAUNCH_KEY="C-f"


# set vi-mode
set-window-option -g mode-keys vi
# keybindings
bind-key -T copy-mode-vi v send-keys -X begin-selection
bind-key -T copy-mode-vi C-v send-keys -X rectangle-toggle
bind-key -T copy-mode-vi y send-keys -X copy-selection-and-cancel


## match the working directory of new pane to current one
bind '"' split-window -v -c "#{pane_current_path}"
bind % split-window -h -c "#{pane_current_path}"
```

# i3

[source](https://archcraft.io/)

```bash
bindsym Control+$ALT+t exec --no-startup-id "xfce4-terminal --drop-down"
bindsym $MOD+F1 exec --no-startup-id "alacritty -e ranger"
bindsym Shift+F1 exec --no-startup-id "xfce4-terminal --drop-down"

bindsym --release $MOD+p 		exec --no-startup-id "xfce4-terminal --drop-down"


bindsym $MOD+Shift+z layout stacking
## Set tabbed layout
bindsym $MOD+Shift+x layout tabbed
## Set default layout
bindsym $MOD+Shift+c layout default
## Toggle between stacking/tabbed/split:
bindsym $ALT+Control+space layout toggle
## Toggle between horizontal/vertical:
bindsym $MOD+Shift+v layout toggle split

bindsym $MOD+Shift+h move left
bindsym $MOD+Shift+j move down
bindsym $MOD+Shift+k move up
bindsym $MOD+Shift+l move right
bindsym $MOD+h focus left
bindsym $MOD+j focus down
bindsym $MOD+k focus up
bindsym $MOD+l focus right
## -- Terminal --
bindsym $MOD+Return 			exec --no-startup-id $terminal
bindsym $MOD+Shift+Return 		exec --no-startup-id $terminal  --float
bindsym $MOD+$ALT+Return 		exec --no-startup-id $terminal --full

## -- GUI Apps --
bindsym $MOD+Shift+f      exec --no-startup-id $file_manager
bindsym $MOD+Shift+e 			exec --no-startup-id "$alacritty -e nvim"
# bindsym $MOD+Shift+w 			exec --no-startup-id $web_browser
bindsym $MOD+n			exec --no-startup-id "alacritty --config-file ~/.config/i3/alacritty/alacritty.toml -e nvim +'Telescope oldfiles' "
bindsym $MOD+t   exec --no-startup-id "alacritty --config-file ~/.config/i3/alacritty/alacritty.toml -e nvim ~/Notes/Tasks/Task.md "
bindsym $MOD+o exec--no-startup-id "alacritty --config-file ~/.config/i3/alacritty/alacritty.toml -e nvim ~/Notes/Public  +Oil "
bindsym $MOD+Shift+r			exec --no-startup-id "alacritty --config-file ~/.config/i3/alacritty/alacritty.toml -e ranger"
## -- CLI Apps --
bindsym $ALT+Control+v 			exec --no-startup-id "$alacritty -e vim"
bindsym $ALT+Control+r 			exec --no-startup-id "$alacritty -e ranger"
bindsym $ALT+Control+h 			exec --no-startup-id "$alacritty -e htop"
bindsym $ALT+Control+m 			exec --no-startup-id $music_player

## -- Rofi Applets --
bindsym $MOD+Shift+d exec --no-startup-id $rofi_applets/rofi_files
bindsym $MOD+Shift+b          exec --no-startup-id /usr/share/archcraft/dwm/scripts/rofi_bluetooth
# bindsym $MOD+d          exec --no-startup-id "dmenu_run"
bindsym $MOD+Shift+n 					exec --no-startup-id $rofi_applets/network_menu
bindsym $MOD+x 					exec --no-startup-id $rofi_applets/rofi_powermenu
bindsym $MOD+w 					exec --no-startup-id $rofi_applets/rofi_windows
bindsym $ALT+Tab 					exec --no-startup-id $rofi_applets/rofi_windows
bindsym $MOD+q 		exec --no-startup-id $rofi_applets/rofi_windowcd
bindsym $MOD+m 					exec --no-startup-id $rofi_applets/rofi_music
bindsym $MOD+r 					exec --no-startup-id $rofi_applets/rofi_asroot
bindsym $MOD+s 					exec --no-startup-id $rofi_applets/rofi_screenshot
bindsym $MOD+Shift+s    exec --no-startup-id $rofi_applets/i3_screenshot --area

## -- Function keys --

bindsym XF86RFKill exec --no-startup-id "systemctl hibernate"

bindsym XF86MonBrightnessUp 	exec --no-startup-id "$brightness --inc"
bindsym XF86MonBrightnessDown 	exec --no-startup-id "$brightness --dec"
bindsym XF86AudioRaiseVolume 	exec --no-startup-id "$volume --inc"
bindsym XF86AudioLowerVolume 	exec --no-startup-id "$volume --dec"
bindsym XF86AudioMute 			exec --no-startup-id "$volume --toggle"
bindsym XF86AudioMicMute 		exec --no-startup-id "$volume --toggle-mic"
bindsym XF86AudioNext 			exec --no-startup-id "mpc next"
bindsym XF86AudioPrev 			exec --no-startup-id "mpc prev"
bindsym XF86AudioPlay 			exec --no-startup-id "mpc toggle"
bindsym XF86AudioStop 			exec --no-startup-id "mpc stop"

## -- Screenshots --
bindsym Print 					exec --no-startup-id "$screenshot --now"
bindsym Control+Print 			exec --no-startup-id "$screenshot --in5"
bindsym Shift+Print 			exec --no-startup-id "$screenshot --in10"
bindsym Control+Shift+Print 	exec --no-startup-id "$screenshot --win"
bindsym $MOD+Print 				exec --no-startup-id "$screenshot --area"


## -- Misc --
# bindsym --release $MOD+p 		exec --no-startup-id $color_picker
bindsym $ALT+Control+l 			exec --no-startup-id "betterlockscreen --suspend"

##-- WM Specific -------------------------

## Kill focused window
##
bindsym $MOD+c kill

#------

## Send Notification
##
set $send-notify exec --no-startup-id dunstify -u low -h string:x-dunst-stack-tag:i3config

## Splitting containers
##
## split in horizontal orientation
bindsym $MOD+g split horizontal
## split in vertical orientation
bindsym $MOD+v split vertical
## toggle split


## Toggle fullscreen
bindsym $MOD+f fullscreen toggle
## Toggle floating/tiling
bindsym $MOD+space floating toggle


## Focusing containers
##
## Sets focus to the nearest container in the given direction.
bindsym $MOD+Left focus left
bindsym $MOD+Down focus down
bindsym $MOD+Up focus up
bindsym $MOD+Right focus right
## Sets focus to the parent container of the current container.
bindsym $MOD+Shift+a focus child
## The opposite of `focus parent`, sets the focus to the last focused child container.
bindsym $MOD+a focus parent
## Automatically sets focus to the adjacent container.
bindsym $MOD+Tab focus next
bindsym $MOD+Shift+Tab focus left
## Toggles focus between floating/tiling containers.
#
bindsym $MOD+Shift+space focus mode_toggle

#------

## Moving containers
##
## move focused window in the given direction.
bindsym $MOD+Shift+Left move left
bindsym $MOD+Shift+Down move down
bindsym $MOD+Shift+Up move up
bindsym $MOD+Shift+Right move right
## Move floating container to the center of all outputs (floating only)
bindsym $MOD+$ALT+c move absolute position center
## Move container to the current position of the cursor (floating only)
bindsym $MOD+$ALT+p move position mouse

#------

## Resizing containers/windows
##
bindsym $MOD+Control+h resize shrink width 10 px or 10 ppt
bindsym $MOD+Control+k resize grow height 10 px or 10 ppt
bindsym $MOD+Control+j resize shrink height 10 px or 10 ppt
bindsym $MOD+Control+l resize grow width 10 px or 10 ppt

#------

## Sticky floating windows (floating only)
##
bindsym $MOD+Shift+o sticky toggle

#------

## Changing border style
##
bindsym $MOD+y border toggle

#------

## Scratchpad
## Make the currently focused window a scratchpad
bindsym $MOD+minus move scratchpad
## Show the first scratchpad window
bindsym $MOD+Shift+minus scratchpad show
bindsym $MOD+z scratchpad show



#------

## restart i3 inplace (preserves your layout/session, can be used to upgrade i3)
bindsym Control+Shift+r restart
## reload the configuration file

#------

## Changing (named) workspaces/moving to workspaces
##
## Define names for default workspaces for which we configure key bindings later on.
## We use variables to avoid repeating the names in multiple places.
set $ws1 "1"
set $ws2 "2"
set $ws3 "3"
set $ws4 "4"
set $ws5 "5"
set $ws6 "6"
set $ws7 "7"
set $ws8 "8"
set $ws9 "9"
set $ws10 "10"

## switch to workspace
bindsym $MOD+1 workspace number $ws1
bindsym $MOD+2 workspace number $ws2
bindsym $MOD+3 workspace number $ws3
bindsym $MOD+4 workspace number $ws4
bindsym $MOD+5 workspace number $ws5
bindsym $MOD+6 workspace number $ws6
bindsym $MOD+7 workspace number $ws7
bindsym $MOD+8 workspace number $ws8
bindsym $MOD+9 workspace number $ws9
bindsym $MOD+0 workspace number $ws10

## move focused container to workspace
bindsym $MOD+Shift+1 move container to workspace number $ws1
bindsym $MOD+Shift+2 move container to workspace number $ws2
bindsym $MOD+Shift+3 move container to workspace number $ws3
bindsym $MOD+Shift+4 move container to workspace number $ws4
bindsym $MOD+Shift+5 move container to workspace number $ws5
bindsym $MOD+Shift+6 move container to workspace number $ws6
bindsym $MOD+Shift+7 move container to workspace number $ws7
bindsym $MOD+Shift+8 move container to workspace number $ws8
bindsym $MOD+Shift+9 move container to workspace number $ws9
bindsym $MOD+Shift+0 move container to workspace number $ws10

## move a container to the next/previous workspace
bindsym $MOD+Control+Right "move container to workspace next, workspace next"
bindsym $MOD+Control+Left "move container to workspace prev, workspace prev"

## switch between the current and the previously focused one
bindsym $MOD+plus workspace back_and_forth
bindsym $MOD+b "move container to workspace back_and_forth, workspace back_and_forth"
```
