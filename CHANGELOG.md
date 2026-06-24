# Changelog

All notable changes to the Antigravity CLI Home Assistant Add-on will be documented in this file.

## [1.9.0] - 2026-06-24

### GrumpyTanker Dev Fork Rebrand & Stability Release

#### Features
- feat: Add text zoom buttons to mobile UI with font size display
- feat: Improve zoom UX — show text size, increase increment, fix scroll position after zoom
- feat: Auto-configure git credentials from `/data/.github_pat` on startup
- feat: Add automatic backend data restoration from homeassistant volume on startup

#### Fixes
- fix: Prevent scroll-to-top on zoom `fit()` and textarea focus
- fix: Only snap to bottom on resize if already near bottom; cap stabilize observer iterations
- fix: Rebrand sidebar to `Antigravity (GT Dev)`; use ports 62900/62901 to avoid upstream conflict
- fix: Change `panel_icon` from triangle to `mdi:brain`
- fix: Remove duplicate `panel_icon`; change slug to `antigravity_cli_dev` to prevent conflict with upstream add-on
- fix: Remove deprecated arch values (`armv7`, `armhf`, `i386`) from `config.yaml`
- fix: Use native xterm.js font scaling for sharper text rendering
- fix: Use native xterm.js `term.scrollToBottom()` API instead of DOM mutation to prevent viewport conflicts
- fix: Replace aggressive scroll observer with clean debounce pattern to prevent jumping
- fix: Eliminate initial load scroll jitter using synchronous MutationObserver
- fix: Stabilize initial load scroll and add delay to zoom scroll
- fix: Increase ttyd scrollback to prevent xterm layout corruption; protect zoom with `requestAnimationFrame`
- fix: Append ANSI reset sequence to history playback to prevent truncated logs hanging reconnects
- fix: Aggressively disable pull-to-refresh inside terminal iframe
- fix: Disable mobile browser pull-to-refresh to prevent accidental reloads

#### Chores
- chore: Rebrand addon metadata for GrumpyTanker dev fork
- chore: Bump version to 1.9.0

## [1.8.9] - 2026-06-19
- feat: Move Home and End to D-pad menu and sync lite version
- fix: Explicitly strip UTF-8 BOM from shell scripts
- fix: Remove BOM from scripts
- fix: Restore config name
- fix: Force LF line endings for Linux scripts to prevent Docker container crashes
- feat: Include lite version in repository
- fix: Use standard name for GitHub release
- docs: Update changelog for 1.8.9

## [1.8.8]
- feat: Fix mobile horizontal scroll, add D-pad context menu, and optimize layout
- Fix scroll observer and add PAGER=cat

## [1.8.6]
- Bump version to 1.8.6 in config.yaml

## [1.8.4]
- Bump version to 1.8.6: Restore dtach native scrolling, fix keyboard snap, fix menu auto-close
- docs: update wiki with new port architecture and chunked upload system
- fix: update import completion message to reflect automatic restart

## [1.8.3]
- fix: reduce backup upload chunk size to 10MB to comply with Home Assistant Ingress hard 16MB request body limit

## [1.8.2]
- docs: update changelog and bump version to 1.8.2
- feat: implement chunked upload (100MB) to bypass ingress limits
- fix: add proxy_request_buffering off and timeouts to nginx

## [1.8.1]
- fix: change default ports to rare range and remove max upload size limit for large backups
- docs: fix encoding issue with book emoji in README

## [1.8.0]
- chore: bump version to 1.8.0 to fix HA supervisor update detection
- docs: replace appended wiki with a link to WIKI.md in README
- style: add undo subtitle to ctrl+z button
- fix: prevent severe RAM exhaustion on file upload and download

## [1.7.8]
- chore: release v1.7.8 with Import/Export Backup tool
- docs: remove localdev references from changelog
- feat: implement automatic addon restart on successful backup restore
- feat: add Import/Export backup tool for agent memory and addon configs
- docs: use python script to generate full chronological changelog with all version tags
- docs: restore rich README.md and write exhaustive CHANGELOG.md
- style: use kbd badges for shortcut legend
- style: capitalize copy and paste shortcut labels
- style: reorder buttons to CtrlC, CtrlV, CtrlZ, /resume
- feat: remove F1-F5 and Ctrl+D, add /resume button
- fix: remove toggleContextMenu from right click

## [1.6.0]
- chore: release version 1.6.0 with backup system
- fix: hide progress bar during export as it is indeterminate
- feat: add progress bar and readable stream tracking for backup/restore modals
- chore: remove .ai_instructions from git tracking and update gitignore
- fix: resolve js ReferenceError preventing backup modal and append WIKI to README
- docs: add Wiki documentation for project architecture
- fix: fixed modal positioning and button styling
- fix: move modal to body root to fix layout bugs
- fix: add loading modal and fix button names
- fix: limit backup scope to .gemini folders
- fix: stream tar to avoid OOM and update button labels
- fix: add cache-busting headers for index.html

