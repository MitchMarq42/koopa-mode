# koopa-mode
An Emacs major mode for Microsoft PowerShell


## Prerequisites

### `company-mode`

`koopa-mode` uses [`company-mode`](https://company-mode.github.io/manual/Getting-Started.html) for autocompletion. To install `company-mode`, use the following command in Emacs:

```
M-x package-install RET company RET
```


## Installation

### Manual

Currently, `koopa-mode` has to be manually installed.

To install, first clone the repo.

```bash
git clone https://github.com/sch0lars/koopa-mode.git
```

Then, add the following to your `init.el`:

```emacs-lisp
(add-to-list 'load-path "/path/to/koopa-mode")
(require 'koopa-mode)
```

## File Associations

To automatically associate PowerShell files with `koopa-mode`, add the following to your `init.el`:

```emacs-lisp
(add-to-list 'auto-mode-alist '("\\.ps1\\'" . koopa-mode))
```

## Keybindings

| Command                           | Keybinding | Description                                      |
|-----------------------------------|------------|--------------------------------------------------|
| `koopa-run-powershell`            | `C-c C-p`  | Spawns a PowerShell process in a new buffer      |
| `koopa-send-line-to-powershell`   | `C-c C-c`  | Send the current line to the PowerShell process  |
| `koopa-send-buffer-to-powershell` | `C-c C-b`  | Send the entire buffer to the PowerShell process |
| `koopa-trigger-company-complete`  | `C-<tab>`  | Triggers the `company` autocomplete              |

## Demo

![Demo of koopa-mode](screenshots/koopa-mode-demo.GIF "Demo of koopa-mode")

## Known Issues

- On Windows, autocompletion adds whitespace at the end the cmdlet
  - In the meantime, a workaround is to autocomplete using `TAB` and then pressing `C-g`
- Nested indentation is buggy

## License

[MIT](https://choosealicense.com/licenses/mit/)
