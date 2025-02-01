# Zix/UI

[English](/docs/index.html?file=docs/Zix/UI/en.md) · [中文]()

## Class UI
### `__init__`
#### 解释
初始化UI。

#### 参数
- `config`: `str`，用于配置窗口，会调用函数`config_ui`，语法请见附件。
- `split`: `str`，配置的分隔符，默认为`;`。
- `pack_mode`: `str`，用于设置这个窗口用什么函数来打包。

#### 附件
config语法：根据`tk.Tk()`的所有可配置参数，使用`function(...)`来配置，默认用分号隔开，可修改。
举例：
```python
from UI import UI
UI_config = """
title("UI")
geometry("400x300")
"""
UI_root = UI(config, '\n')
```

### config_ui
#### 解释
整个用法除`pack_mode`外，都和`__init__`相同，可直接看`__init__`的文档。

### mainloop
#### 解释
主循环，显示窗口。

### add
#### 解释
可添加`tkinter`控件进入。

#### 参数
- `name`: `str`，此控件的命名，很重要，以后获取都需要这个。
- `sth`: `object`，这个控件本体。
- `config`: `str`，可以配置在打包时控件的参数，格式见附件。

#### 附件
config格式：直接和函数调用一样的格式，不需要括号。
举例：
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
#### 解释
打包所有控件，按照每个控件自带的配置。

### pack
#### 解释
打包指定控件，可以新制定配置。

#### 参数
- `name`: `str`，通过这个获取你在`control`字典中存储的控件。
- `config`: `str`，重新制定配置，会存储进`control`当中，格式可见`add`中。 