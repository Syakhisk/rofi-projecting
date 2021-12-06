# Projecting

Launch or focus to frequently used programs in a project.

## Dependencies

Python (using pip)
* pydymenu
* pyyaml
* brotab

Linux (using package manager)
* wmctrl

## Usage
Create a yaml file (ended with .yml) in the ~/.config/projecting/ directory.

Example project:
```yaml
programs:
  Github:
    name: Google
    browser:
      url: https://github.com

  Tmux:
    name: TMUX
    commands:
      - kitty -e tmux

  Database:
    class: "jetbrains-datagrip"
    commands: 
      - "datagrip"
```

`name` is the title/name of the project, use `xprop` to determine the window title.  
`class` is the class name of the window, use `xprop` to determine the window class.  
you can use either `name` or `class` to specify the window.  

when there are no window matching the `name` or `class`, the program will be launched using the `commands` specified.

then run:
```bash
$ projecting
```

Ultimately you will bind `projecting` to a keybind then launch it from there.


