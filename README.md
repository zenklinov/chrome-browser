# Keep the Chrome Toolbar Bright

Chrome’s toolbar sometimes appears to “fade” (the tab strip and title bar look darker) when the window loses focus. This isn’t a Chrome bug—Windows (and macOS) intentionally lowers the frame contrast of windows that are **behind** the active one, and Chrome simply follows that rule.

If you’d rather keep the original bright color on every Chrome window, you have two options:

1. **Install a custom Chrome theme** that makes the active and inactive window colors identical. *(Fast & safe—recommended)*
2. **Modify Windows settings/registry** so inactive title bars stay the same color as active ones **and** turn off Windows “content adaptive brightness” so the entire display doesn’t dim.

## Option 1 — Create a Minimalist Theme

1. Create an empty folder and add a file named `manifest.json` with the contents below:

```json
{
  "manifest_version": 3,
  "version": "1.0.0",
  "name": "Always Bright Toolbar",
  "theme": {
    "colors": {
      "frame_inactive":  [222, 225, 230],
      "background_tab_inactive": [222, 225, 230]
    }
  }
}
```

`222, 225, 230` is Chrome’s default RGB value—replace these numbers with any color you like.

2. Open `chrome://extensions`, enable **Developer mode**, click **Load unpacked**, and select the folder you just created.

After the theme loads, unfocused Chrome windows will keep the same toolbar color as the active one—no more fading.

> **Note:** This method affects **Chrome only**; other applications will still dim according to the operating‑system rules.
