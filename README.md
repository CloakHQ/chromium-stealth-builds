# CloakHQ — Chromium Stealth Builds

Pre-built stealth Chromium binaries with source-level fingerprint patches. Linux x64 and macOS arm64. Used by [cloakbrowser](https://github.com/CloakHQ/cloakbrowser) — auto-downloaded on first launch.

## Downloads

See [Releases](https://github.com/CloakHQ/chromium-stealth-builds/releases) for binary downloads.

## What's included

Each release contains a complete Chromium build with 16 fingerprint patches compiled at the C++ source level:

- Canvas, WebGL, audio fingerprint modification
- Font enumeration, hardware concurrency, client rects
- GPU vendor/renderer spoofing
- WebDriver flag disabled
- Headless detection bypassed
- TLS fingerprint matches real Chrome

## Usage

These binaries are designed to work with [cloakbrowser](https://github.com/CloakHQ/cloakbrowser):

```bash
pip install cloakbrowser
```

The binary is automatically downloaded on first use. For manual use with Playwright:

```python
from playwright.sync_api import sync_playwright

pw = sync_playwright().start()
browser = pw.chromium.launch(
    executable_path="/path/to/chrome",
    args=["--fingerprint=98765", "--fingerprint-platform=windows"]
)
```

## Platforms

| Platform | Status |
|----------|--------|
| Linux x64 | Available |
| macOS arm64 | Coming soon |
| macOS x64 | Coming soon |
| Windows | Planned |

## License

All Rights Reserved. These binaries are provided for use with CloakHQ products. Redistribution is not permitted without written consent.
