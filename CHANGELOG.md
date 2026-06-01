# Changelog

All notable changes to the Antigravity CLI Home Assistant Add-on will be documented in this file.

## [1.7.7] (Current)
### Added
- MCP Integration with dynamically generated `mcp.json` for Home Assistant and Zigbee2MQTT.
- Added translation support for configuration UI hints.
- Added a new `/resume` macro button to quickly resume workflows.
- Implemented elegant keyboard shortcut badges (`<kbd>`) in the UI footer for `Ctrl+C`, `Ctrl+V`, and `Ctrl+Z`.
- Added new contextual menu for expanded keyboard shortcuts (Home, End, PgUp, PgDn).
- Added in-app update banner and one-click updater for CLI.
- Added MIT License and comprehensive liability disclaimer.

### Changed
- Improved context menu logic: Right-click now suppresses the Chrome context menu without triggering the visual grid menu, allowing native terminal apps to handle right-clicks properly.
- Reordered keyboard shortcuts in the UI to `Ctrl+C`, `Ctrl+V`, `Ctrl+Z`, and `/resume`.
- Refined and improved layout spacing for mobile devices.
- Replaced the upload button with a minimalist image icon.
- Changed the entire theme base to `#2b2b2b` for a cohesive aesthetic matching Google Chrome dark mode.
- Cleaned up footer borders and implemented true Chrome-like tabs.
- Disabled predictive text on the terminal textarea to fix duplicate keystrokes on mobile devices.

### Fixed
- Fixed bug causing the Chrome browser context menu to overlay and close the terminal menu.
- Restored `contextmenu` event listeners inside the `iframe` document.
- Fixed absolute GitHub raw URLs for logos in the UI.
- Fixed layout sizing issues and moved the mobile toolbar to the top header.
- Parsed ttyd JSON theme correctly to force absolute black terminal and match exact backgrounds.

## [1.7.4]
### Changed
- Reverted TERM to `xterm-256color` and added auto-restart loops to prevent the CLI from crashing/hanging.
- Re-architected Telegram Bridge: Completely removed fragmented output and splash screens using a synchronous expect mechanism.
- Improved ANSI parsing and buffering in the Telegram bridge for native plain text messages instead of markdown blocks.
- Spawns Telegram integration in a completely isolated CLI session.
- Switched back from `dtach` to `tmux` for proper persistent session state and reliable screen redraws.

### Fixed
- Fixed UTF-8 character encoding issues using the `locales` package and `.inputrc` configurations.
- Handled carriage return inputs and prompt-filtering in Telegram output gracefully.
- Passed `-a` to ttyd to enable URL arguments, fixing tab isolation.
- Simplified `attach.sh` (removed script/cat) and fixed scroll timing.
- Removed aggressive auto-scroll that was hiding the CLI splash on load.
- Resolved a SyntaxError causing a blank terminal on init.

## [1.4.0] (Stability Release)
### Added
- Dynamic Multi-Session Tabs UI allowing multiple concurrent terminal tabs with lazy session spawning.
- Added `/new`, `/mod`, and `/quota` macro buttons.
- Implemented intelligent DOM MutationObserver to hide resize banners and auto-reconnect WebSockets on disconnect.
- Added touch-to-scroll translation for mobile devices using a custom momentum physics engine independent of frame-rate (120Hz support).

### Changed
- Overhauled responsive design for mobile (vibecoding focused) with fluid flex layouts, hidden logos on narrow screens, and touch-optimized buttons.
- Transitioned upload button styling to the Antigravity brand blue-purple-red mesh gradient.
- Replaced Unicode arrows with consistent SVG icons.
- Unified arrow keys font family and size to prevent mobile rendering discrepancies.

### Fixed
- Resolved jumping to top bugs on mobile when the keyboard closes or the window resizes.
- Fixed momentum physics engine bugs by preventing `touchcancel` and using `window.requestAnimationFrame`.
- Fixed white screen issue by using passive event interceptors instead of `cloneNode`.
- Fixed Dockerfile references, NGINX duplicate daemon directive crashes, and Ingress 404s/WebSockets base path bugs.
- Fixed font family and theme to resolve block character gaps and forced `COLORTERM=truecolor`.
- Switched to `debian:12-slim` and later `ubuntu:22.04` base image to fix `ttyd` and `glibc` incompatibilities.

## [1.0.3] (Initial Release)
### Added
- Initial commit: Antigravity CLI Add-on.
- Integrated `ttyd` terminal exposed over Home Assistant Ingress.
- Mapped Home Assistant `/config` and `/share` volumes.
- Zmodem support for file upload.
- Mouse scrolling enabled in tmux.
- Custom UI wrapper to fix font rendering.
