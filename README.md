# PdfCraft multi-PDF viewer mode

A "viewer mode" for [PdfCraft](https://github.com/storytold/pdfcraft): a stripped-down, browser-like window with only a tab strip and the page area, for reading several PDFs side by side in tabs.

PdfCraft has no plugin system, so this ships as a source patch.

## Status: works, tested in the headless UI harness (17 Nov 2026)

- **Turn on:** the eye button in the title bar, View ▸ Viewer mode, or Ctrl+E (⌘E on macOS). **Turn off:** the crossed-out eye in the strip, Ctrl+E or Esc.
- **Tabs:** click to switch; close with the ×, a middle click, Ctrl+W or the right-click menu (unsaved changes ask first); Ctrl+Tab / Ctrl+Shift+Tab step through them.
- **Pages:** Page Up/Down, Home/End, arrows and the wheel work as usual.
- It is one registered command (`view.viewer_mode`), so it is in the palette and the shortcuts list too.
- Four UI tests in `crates/ui-egui/tests/it/viewer_mode.rs` pass. Not yet tried by hand in a real window.

## Apply

Made against PdfCraft `storytold/pdfcraft` at commit `a499493` (workspace version 0.21.1).

```bash
git clone https://github.com/storytold/pdfcraft
cd pdfcraft
git checkout a499493
git apply /path/to/patches/0001-viewer-mode.patch
cargo check -p pdfcraft-ui-egui
```

`cargo build --release -p pdfcraft` and the four viewer-mode tests pass (17 Nov 2026).

## License

MIT, see `LICENSE`. PdfCraft itself is MIT OR Apache-2.0.
