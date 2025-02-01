# Zix/UI

[English]() · [中文](/docs/index.html?file=docs/Zix/UI/zh-cn.md)

## Class UI
### `__init__`
#### Explanation
Initialize the UI.

#### Parameters
- `config`: `str`. It is used to configure the window and will call the function `config_ui`. Please refer to the attachment for the syntax.
- `split`: `str`. The delimiter for configuration, with a default value of `;`.
- `pack_mode`: `str`. It is used to set the packing function for this window.

#### Attachment
Syntax of `config`: Based on all configurable parameters of `tk.Tk()`. Use `function(...)` for configuration. By default, it is separated by semicolons and can be modified.
Example:
```python
from UI import UI
UI_config = """
title("UI")
geometry("400x300")
"""
UI_root = UI(config, '\n')
```

### config_ui
#### Explanation
Except for `pack_mode`, the entire usage is the same as that of `__init__`. You can directly refer to the documentation of `__init__`.

### mainloop
#### Explanation
The main loop to display the window.

### add
#### Explanation
Used to add `tkinter` controls.

#### Parameters
- `name`: `str`. The name of this control is very important as it will be required for future retrieval.
- `sth`: `object`. The control itself.
- `config`: `str`. It can configure the parameters of the control during packing. Please refer to the attachment for the format.

#### Attachment
Format of `config`: It has the same format as a function call but without parentheses.
Example:
```python
from UI import UI
import tkinter as tk
UI_config = """
title("UI")
geometry("400x300")
"""
UI_root = UI(config, '\n')
UI_root.add("button", tk.Button(UI_root.root, text="button"), "padx=10, pady=15")
```

### pack_all
#### Explanation
Pack all controls according to the configuration of each control.

### pack
#### Explanation
Pack a specified control and new configuration can be set.

#### Parameters
- `name`: `str`. Used to obtain the control stored in the `control` dictionary.
- `config`: `str`. Re - set the configuration, which will be stored in `control`. The format can be seen in the `add` method. 