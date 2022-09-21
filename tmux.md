# TMUX Cheatsheet 

## Bash command
- List   session : **`tmux ls`**
- Attach session with id : **`tmux attach-session -t $id`** or **`tmux a -t $id`**
- Attach session with name : **`tmux a -t $name`**
- Attach last created session : **`tmux a`**
- Create session with name : **`tmux -new -s $name`** 
- Kill server / all sessions : **`tmux kill-server`**
- Kill session : **`tmux kill-session -t $name`**
- Reload tmux config file : **`tmux source ~/.tmux.conf`**

## Cursor movement
- Start of line : **`Ctrl+a`**
- End of line : **`Ctrl+e`**
- Previous word : **`Alt+b`**
- Next word : **`Alt+f`**


## Basic shortcut
- Each shortcut must be preceded by the prefix tmux. 
- Prefix tmux : **`Ctrl+b`** remap to **`Ctrl+Space`**

- Detach session : **`d`**
- Split horizontally : **`"`** remap to **`-`** 
- Split vertically : **`%`** remap to **`|`**
- Zoom in/out : **`z`**
- Same command on multiple panes : **`:setw synchronize-panes on/off`**

## Panes
- Change panes : **`ARROW`**
- Resizing panes : **`PREFIX(pressed)+ARROW`**
- Kill current pane : **`x`**
- Cycle through panes : **`o`**
- Cycle between previsous/current pane : **`;`**

## Tabs
- Create new tab : **`c`**
- Go to next tab : **`n`** remap to **`PageUp`**
- Go to previous tab : **`p`** remap to **`PageDown`**
- Name tab : **`,`**
- kill tab with all pane : **`&`**

## Plugins

### tmux-resurrect
- Save environment : **`Ctrl+s`**
- Reload last saved environment : **`Ctrl+r`**
- Restoring previously saved environment : 
    - **`cd ~/.tmux/resurrect/`**
    - **`ln -sf $file_name last`**
