# Description

A Qt5-compilable fork of [RTKLIB](https://github.com/tomojitakasu/RTKLIB) (**version**: `2.4.3 b31`).

> ⚠️ This repository is no longer maintained. For the latest version, please see [RTKLIB-Qt6](https://github.com/YuanxinPan/RTKLIB-Qt6).


## Build the Project

### Linux (Ubuntu/Debian)

Install dependencies:
```bash
sudo apt install -y build-essential qtbase5-dev qt5-qmake libqt5serialport5-dev qtcreator
```

> **Note:** `qtcreator` is optional — only install it if you want to use the IDE.

Build:
```bash
qmake RTKLib.pro && make -j
```

### macOS (≥ 14.0)

Install Qt5 via Homebrew:
```bash
brew install qt@5
```

Add Qt5 tools to your `PATH` (required since Homebrew does not link `qt@5` by default):
```bash
export PATH="$(brew --prefix qt@5)/bin:$PATH"
```

Then build:
```bash
qmake RTKLib.pro && make -j
```

### Windows

1. Install [Qt5](https://www.qt.io/download) and Qt Creator.
2. Open `RTKLib.pro` with Qt Creator.
3. Click **Build**.


## Known Issues

- **`rtkplot_qt`**: File dialogs may fail to open on Linux.
  - **Fix**: In `app/rtkplot_qt/plotmain.cpp`, comment out line 543 and uncomment line 542 to disable the native dialog.
- **`rtkplot_qt`**: Zooming may not work properly.

