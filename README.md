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

Made against PdfCraft `storytold/pdfcraft` at commit `bad6ac7` (workspace version 0.21.1, 18 Nov 2026).

```bash
git clone https://github.com/storytold/pdfcraft
cd pdfcraft
git checkout bad6ac7
git apply /path/to/patches/0001-viewer-mode.patch
cargo check -p pdfcraft-ui-egui
```

The four viewer-mode tests pass on that commit (`cargo test -p pdfcraft-ui-egui --test it viewer_mode`, 18 Nov 2026). On a newer PdfCraft the patch may need small changes; the first one to expect is the Esc handling in `crates/ui-egui/src/app/keys.rs`.

## License

Dual-licensed, like PdfCraft itself: **MIT OR Apache-2.0**, at your option. See [`LICENSE-MIT`](LICENSE-MIT) and [`LICENSE-APACHE`](LICENSE-APACHE). Copyright (c) 2026 LudaLunizz.

This is an unofficial patch. It is not made, endorsed or supported by the PdfCraft maintainers; PdfCraft is theirs and keeps its own licence (MIT OR Apache-2.0). Problems in PdfCraft itself belong in [storytold/pdfcraft](https://github.com/storytold/pdfcraft); see [SECURITY.md](SECURITY.md) and [CONTRIBUTING.md](CONTRIBUTING.md) for this repository.
