<p align="center"><img src="https://raw.githubusercontent.com/go-widgets/brand/main/social/go-widgets.png" alt="go-widgets" width="640"></p>

<h1 align="center">go-widgets</h1>
<p align="center">Pure-Go widget toolkits, byte-buffer first. No cgo, no JS, no DOM — the same widget code paints a framebuffer, a terminal, a browser canvas or a real native window.</p>
<p align="center">
  <img src="https://img.shields.io/badge/Go-1.26-00ADD8?style=flat-square&logo=go&logoColor=white">
  <img src="https://img.shields.io/badge/license-BSD--3--Clause-0A6E96?style=flat-square">
  <a href="https://go-widgets.github.io/"><img src="https://img.shields.io/badge/landing-go--widgets.github.io-0079A8?style=flat-square"></a>
  <a href="https://go-widgets.github.io/docs/"><img src="https://img.shields.io/badge/docs-mkdocs--material-0079A8?style=flat-square"></a>
</p>

## The toolkit, and what draws it

A widget set that owns its pixels: the same widget code reaches a framebuffer, a terminal cell grid, a browser canvas or an SVG.

| Repo | What it is |
| --- | --- |
| [`toolkit`](https://github.com/go-widgets/toolkit) | Pure-Go widget toolkit for wasmdesk native apps (RGBA-buffer renderer, themed, no JS/DOM) |
| [`painter`](https://github.com/go-widgets/painter) | Prototype: pluggable Painter interface — same widget code renders into a pixel buffer (WUI/GUI) or a terminal cell grid (TUI) or SVG. |
| [`skin`](https://github.com/go-widgets/skin) | Declarative theme + layout + interaction-state engine for go-widgets/toolkit (the Edje analogue): parts, per-state visuals and signal-driven transitions in a… |
| [`svg`](https://github.com/go-widgets/svg) | Pure-Go widget helper: turn any toolkit RGBA render into a portable SVG (base64 PNG inside a scaling wrapper). |
| [`tui`](https://github.com/go-widgets/tui) | Pure-Go terminal-cell widget toolkit: ~34 cell-native widgets + interactive tui.App (raw mode, alt-screen, focus), syntax-highlighted TextEditor. Same… |
| [`webcanvas`](https://github.com/go-widgets/webcanvas) | Pure-Go (CGO=0) browser harness for go-widgets: blit an RGBA framebuffer into a <canvas> and route DOM pointer and keyboard events into a widget scene |

## Where an application runs

One program, several hosts. Each back-end answers the same contract, so an app does not learn which one it got.

| Repo | What it is |
| --- | --- |
| [`window`](https://github.com/go-widgets/window) | Pure-Go, CGO-free windowing: **six** interchangeable back-ends behind one `Open`/`Run` — X11, Wayland, macOS Cocoa, Windows Win32, Android and wasmbox |
| [`application`](https://github.com/go-widgets/application) | Cross-platform application lifecycle for go-widgets: window run loop + system tray + ready hook, CGO-free |
| [`desktop`](https://github.com/go-widgets/desktop) | Native pure-Go desktop-shell demo composing the go-freedesktop + go-widgets stack (dock, launcher, app menu, MIME open-with, file grid, notifications). |
| [`android`](https://github.com/go-widgets/android) | Pure-Go, CGO-free Android back-end for go-widgets: a real APK whose whole UI is painted by a CGO_ENABLED=0 Go process. |
| [`tray`](https://github.com/go-widgets/tray) | Cross-platform system-tray (menu-bar) widget for go-widgets: menus, submenus, checkboxes — CGO=0 (purego/syscall/DBus backends) |

## MVVM, and the analysers that keep it

State lives in observables and reaches widgets through bindings — and two analysers make that mandatory rather than advisory.

| Repo | What it is |
| --- | --- |
| [`mvvm`](https://github.com/go-widgets/mvvm) | Dependency-free MVVM layer for the go-widgets ecosystem: Observable, Command, ObservableList + backend-agnostic bindings |
| [`mvvmtk`](https://github.com/go-widgets/mvvmtk) | MVVM↔toolkit binding glue: wire go-widgets/mvvm observables & commands to go-widgets/toolkit widgets in one call |
| [`mvvmlint`](https://github.com/go-widgets/mvvmlint) | go/analysis analyzer that makes MVVM usage mandatory for go-widgets apps |
| [`bricolint`](https://github.com/go-widgets/bricolint) | go/analysis analyzer that guards the no-hand-drawn-UI rule: no painter primitives in app code, no per-frame throwaway widgets |

## Data, assets and demos

| Repo | What it is |
| --- | --- |
| [`data`](https://github.com/go-widgets/data) | Headless data spine for go-widgets: typed records + validation, sort/filter/group/page/aggregate, and a pluggable Memory/gRPC proxy with byte-identical views. |
| [`gallery`](https://github.com/go-widgets/gallery) | Wasm live demo of go-widgets/toolkit — every widget family rendered into a browser canvas. |
| [`isoicons`](https://github.com/go-widgets/isoicons) | Reusable isometric icon packs (cloudnative PNG + AWS SVG) for the go-widgets/toolkit isometric-diagram widget. Pure Go, CGO=0, wasm-clean. |
| [`app-template`](https://github.com/go-widgets/app-template) | A minimal, MVVM-compliant go-widgets browser-wasm app template: state in go-widgets/mvvm, bound via go-widgets/mvvmtk, gated by go-widgets/mvvmlint. |

