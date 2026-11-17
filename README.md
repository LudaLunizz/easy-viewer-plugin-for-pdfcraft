# PdfCraft multi-PDF viewer mode

A "viewer mode" for [PdfCraft](https://github.com/storytold/pdfcraft): a stripped-down, browser-like window with only a tab strip and the page area, for reading several PDFs side by side in tabs.

PdfCraft has no plugin system, so this ships as a source patch.

## Status: work in progress, not usable yet

This is the first version, imported as it was. It compiles, but it has not been run in the app and **nothing switches viewer mode on yet**:

- Done: a `ViewerMode` state, a `viewer_tab_strip` (home, open, one tab per open PDF, "Exit Viewer"), and a render path in `app.rs` that shows only the strip and the page area.
- Missing: a button or shortcut that sets `viewer_mode.enabled = true` (`toggle_viewer_mode` exists but nothing calls it), tab close buttons, page and tab keyboard shortcuts, and any UI test.
- Needs cleaning: `viewer_mode.rs` is not declared as a module (the state type is duplicated in `state.rs`); the patch adds a Discord link button to the strip and a `webbrowser` dependency for it; `crates/ui-egui/Cargo.toml` also gains a block of unrelated dependencies under the wasm target.

## Apply

Made against PdfCraft `storytold/pdfcraft` at commit `a499493` (workspace version 0.21.1).

```bash
git clone https://github.com/storytold/pdfcraft
cd pdfcraft
git checkout a499493
git apply /path/to/patches/0001-viewer-mode.patch
cargo check -p pdfcraft-ui-egui
```

`cargo check -p pdfcraft-ui-egui` passes with one unused-variable warning (checked 17 Nov 2026).

## License

MIT, see `LICENSE`. PdfCraft itself is MIT OR Apache-2.0.
