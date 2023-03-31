---
layout: default
---

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://vshymanskyy.github.io/StandWithUkraine)
[![Русский корабль, иди на хуй!](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/RussianWarship.svg)](https://vshymanskyy.github.io/StandWithUkraine)

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/banner2-direct.svg)](https://vshymanskyy.github.io/StandWithUkraine/)

## FAR.js

Good old Windows **F**ile and **AR**chive Manager
([FAR](https://en.wikipedia.org/wiki/Far_Manager)) app built with:
[Scala.js](https://www.scala-js.org/),
[React.js](https://reactjs.org/),
[react-blessed](https://github.com/Yomguithereal/react-blessed),
[blessed](https://github.com/chjj/blessed)

Runs on [Node.js](https://nodejs.org/), thus cross-platform:
* `Mac OS X` (primary support in [iTerm2](https://iterm2.com/) and [WezTerm](https://wezfurlong.org/wezterm/))
* `Windows` (primary support in [WezTerm](https://wezfurlong.org/wezterm/) and [Windows Terminal](https://docs.microsoft.com/en-us/windows/terminal/))
* `Linux` (primary support in [WezTerm](https://wezfurlong.org/wezterm/))

## Install

To install (or upgrade) it on your computer use the following command:

``` bash
$ npm i -g farjs-app
```

then you can run the application from your favorite terminal:

``` bash
$ farjs
```

![Screenshots](https://raw.githubusercontent.com/farjs/farjs/main/docs/images/screenshots.png)

## Documentation

### Modules

- [File Browser](#file-browser)
- [File Viewer](#file-viewer)
- [Dev Tools](#dev-tools)
    - [Logs](#logs)
    - [Inputs](#inputs)
    - [Colors](#colors)

### Other

- Developing
    - See [develop.md](https://github.com/farjs/farjs/blob/main/develop.md)
- [FAQ](#faq)
    - [Key Bindings](#key-bindings)

## File Browser

Main application window that consists of two similar panels.
Each panel displays list of files and directories. You can perform
different operations:

* **Navigation** within panels:
    * Items **selection** - `Shift + Up/Down/Left/Right/PageUp/PageDown/Home/End`
      * Select/Deselect group with `Alt + S`/`Alt + D`
    * **Go back** to the parent folder - `Ctrl + PageUp`
    * **Go into** a folder - `Ctrl + PageDown` / `Return`

* **Drive** selection popup
  (see [Key Bindings](#key-bindings) for how to re-map it to `Alt + F1/F2`)
    * Show it on the **left** panel - `Alt + L`
    * Show it on the **right** panel - `Alt + R`

* **Open item** in default application - `Alt + O`
  (see [Key Bindings](#key-bindings) for how to re-map it to `Shift + Return`)
* **Copy Path** of current item into **Clipboard** - `Ctrl + C`
  (in iTerm2 only)
* **Folder shortcuts** - `Ctrl + D`
* **Folders history** - `Alt + F12`
* **Swap** the panels - `Ctrl + U`
* **Quick View** of current item on in-active panel - `Ctrl + Q`
* Show **Quick Search** box - `Ctrl + S`
* **Refresh** active panel - `Ctrl + R`
* **View item(s)** - `F3`
    * Opens focused file in the internal [File Viewer](#file-viewer)
    * Scans selected folder(s)/file(s) and calculates size(s)
* **Copy item(s)** - `F5`
* **Copy current item inplace** - `Shift + F5`
* **Rename/Move item(s)** - `F6`
* **Rename/Move current item inplace** - `Shift + F6`
* **Create folder** (with intermediate sub-folders) - `F7`
* **Add files to archive (ZIP)** - `Shift + F7`
* **Delete item(s)** - `F8`
* **Main menu** - `F9`

## File Viewer

Built-in internal text file viewer.

* **Wrap/Unwrap** text - `F2`
* **Move view column** - `Left/Right`
* **Select Encoding** - `F8`

## Dev Tools

Use `F12` to show/hide DEV tools components on the right side.
Press `F12` again to switch between the components.

### Logs

Shows all the intercepted `console.log` and `console.error` messages,
since the app itself is rendered to the console.

### Inputs

Shows input keys sequences.

### Colors

Shows possible colors with their `hex` codes for current terminal/theme.

## FAQ

### Key Bindings

* Why supported key combination doesn't work or trigger another
  action in my terminal?
    - Some key combinations (especially `Alt+`) have to be manually re-mapped
      in your terminal settings to **send** supported **escape sequences**
      or **hex codes**.
      For example, you can re-map:
        - | Key | Supported Key | Escape Sequence ^[ ... | Hex Codes |
          | --- |-----------------------| --- | --- |
          | `Alt + F1` | `Alt + L` | `l`                   | |
          | `Alt + F2` | `Alt + R` | `r`                   | |
          | `Alt + F12` | `Alt + H` | `h`                   | |
          | `Shift + Return` | `Alt + O` | `o`                   | |
          | `CMD + PageDown` | `Ctrl + PageDown` | `[6^`                 | |
          | `CMD + PageUp` | `Ctrl + PageUp` | `[5^`                 | |
          | `CMD + R` | `Ctrl + R` |                       | `0x12` |
          | `CMD + F3` | `Ctrl + F3` | `[13;5~`              | |
          | `CMD + F4` | `Ctrl + F4` | `[14;5~`              | |
          | `CMD + F12` | `Ctrl + F12` | `[24;5~`              | |
          | `CMD + Up` | `Ctrl + Up` | `[1;5A`               | |
          | `CMD + Down` | `Ctrl + Down` | `[1;5B`               | |
    - In [iTerm2](https://iterm2.com/), when you go to
    `Preferences -> Keys` and press `+`, it looks like this:
        - ![Keys Re Mapping](https://raw.githubusercontent.com/farjs/farjs/main/docs/images/keys_re_mapping.png)
        - You can `Import` ALL supported keys re-mappings using
        [FAR.js iTerm2 Preset](https://raw.githubusercontent.com/farjs/farjs.github.io/main/data/farjs.itermkeymap)
    - In [Windows Terminal](https://docs.microsoft.com/en-us/windows/terminal/)
      you can use [sendInput action](https://docs.microsoft.com/en-us/windows/terminal/customize-settings/actions#send-input)
      (in `settings.json`):
      ```json
      {
        "actions": [
  
            { "command": { "action": "sendInput", "input": "\u001bl" }, "keys": "alt+f1" },
            { "command": { "action": "sendInput", "input": "\u001br" }, "keys": "alt+f2" },
            { "command": { "action": "sendInput", "input": "\u001bh" }, "keys": "alt+f12" },
            { "command": { "action": "sendInput", "input": "\u001bo" }, "keys": "shift+enter" }
    
        ]
      }
      ```

### Archive Support

* Why on my platform I get: _Command not found (`unzip`/`zip`) error_?
    - Indeed, on `Windows`, for example, they aren't pre-installed.
      You can download them from [here](http://stahlworks.com/dev/index.php?tool=zipunzip),
      for example, and then store them in local folder that
      is listed in the `PATH` environment variable.

### Network Shared Folders

* How can I open network shared folders on `Mac OS X`?
    - On `Mac OS X` you can first mount shared folder on local drive
      by using _Connect to Server_ feature in Finder,
      see details [here](https://superuser.com/a/375250/477240).
      Then you should be able to select it in the **Drive** selection
      popup in FAR.js.

### Mouse Support

* Why on `Windows` platform `mouse` doesn't work?
    - Indeed, on `Windows` mouse may not work,
      please, check [this thread/issue](https://github.com/microsoft/terminal/issues/376#issuecomment-973178777)
      for more details.

### Unicode Support

* Why on `Linux`/`Ubuntu` I get `???` instead of
  double border characters?
    - You have to set `LANG=en_US.UTF-8` environment
      variable globally, or via command line:
      ```bash
      LANG=en_US.UTF-8 farjs
      ```
