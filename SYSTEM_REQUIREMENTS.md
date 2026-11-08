# Rafael system requirements

Rafael checks your hardware twice: **the installer** refuses PCs below the minimum and warns below the
recommended level, and **the app** turns off heavy features your PC can't handle and tells you why when you
try to switch one on. You can see what Rafael found under **Settings > General > This PC & Requirements**.

## Operating system

| | Supported |
|---|---|
| **Windows** | Windows 10 version 2004 (build 19041) or newer, or Windows 11. 64-bit (x64) only. |
| **macOS** | Not available yet. Planned minimum: macOS 12 Monterey. |
| **Linux** | Not supported. |

## Minimum and recommended

| | Minimum (installer blocks below this) | Recommended (all features on) |
|---|---|---|
| **CPU** | 2 cores | 4 cores / 8 threads or better |
| **RAM** | 4 GB | 8 GB (16 GB for a local AI model) |
| **Graphics** | Any (3D background turns off without a GPU) | Any GPU with DirectX 11 / WebGL 2; a dedicated card for local AI |
| **Disk** | 3 GB free | 5 GB free (speech models download on first use) |
| **Internet** | Needed: Rafael's AI runs on Google Gemini / OpenRouter | Stable broadband for Live voice |
| **Microphone** | Needed for voice | A headset or a mic with echo cancelling |

## Heavy features and what they need

Below these numbers the feature stays off and Rafael explains why.

| Feature | RAM | CPU cores | Graphics |
|---|---|---|---|
| 3D animated background | 6 GB | | any GPU |
| GESTURES hand-tracking board | 8 GB | 4 | any GPU, plus Google Chrome and a webcam |
| Economy voice (speech-to-text on your PC) | 6 GB | 4 | |
| Filipino speech-to-text on your PC | 8 GB | 4 | (falls back to the lighter English model) |
| Camera tracking (workout counter) | 8 GB | 4 | |
| Local AI model (Ollama / LM Studio on this PC) | 16 GB | 6 | dedicated graphics card |

Everything else (chat, Live voice, tools, business integrations, notes, reminders) runs on the minimum.

## A feature is off but my PC can handle it

Hardware detection can misread some PCs (for example virtual machines or very new graphics chips). To turn
the limits off, set `"hardware_checks": false` in `%LOCALAPPDATA%\RafaelAI\config\app_settings.json` and
restart Rafael. Heavy features may then run slowly.
