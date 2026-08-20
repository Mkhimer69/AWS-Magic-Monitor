# Changelog

All notable changes to AWS Magic Monitor will be documented in this file.

The format is based on Keep a Changelog and follows Semantic Versioning principles.

---

## [3.0.0] 

### Added

- Real-time AWS Connect API interception.
- Live agent data collection from AWS Analytics dashboards.
- Automatic dashboard refresh whenever AWS data updates.
- Occupancy calculation by queue.
- Queue-based grouping using Routing Profiles.
- Available agents tracking.
- On Contact agents tracking.
- Agent duration tracking in HH:MM:SS format.
- Flag detection for:
  - Break > 16 minutes
  - Lunch > 31 minutes
  - Coaching > 31 minutes
  - Meeting > 31 minutes
  - Missed contacts > 1 second
  - After Contact Work > 6 minutes
- Routing Profile distribution view.
- CSV export functionality.
- Draggable dashboard window.
- Native browser-based dashboard resizing.
- Expandable/collapsible dashboard.
- Expandable Available section.
- Expandable On Contact section.
- Expandable Flags section.
- Expandable Routing Profiles section.
- Last Refresh timestamp.
- Longest On Contact indicator.
- Auto-expanded Flags section when violations exist.
- Modern dark-themed dashboard UI.
- Horizontal queue card layout.
- Automatic sorting by longest duration first.

### Changed

- Rebuilt UI from the original prototype.
- Improved dashboard readability.
- Increased table font sizes.
- Improved card spacing and visual hierarchy.
- Improved scrolling behavior.
- Simplified occupancy presentation.

### Fixed

- Multiple dashboard load protection using:
  - `window.magicMonitorLoaded`
- AWS refresh rendering issues.
- CSV encoding and export behavior.
- Queue card overflow issues.
- Dashboard drag behavior.
- Collapse/expand behavior.
- Queue aggregation accuracy.

---

## [2.2.0] 

### Added

- Refresh timestamp.
- Resizable monitor window.
- Improved card layout.
- Enhanced CSV export.

### Changed

- Redesigned header layout.
- Moved export button into header.
- Improved dark mode color palette.

### Fixed

- Dragging stability.
- Queue rendering consistency.

---

## [2.1.0] 

### Added

- Routing Profile distribution.
- Flags section.
- On Contact section.
- Available section.

### Changed

- Converted lists into expandable sections.
- Improved queue card organization.

---

## [2.0.0] 

### Added

- Complete UI redesign.
- Queue cards.
- Occupancy tracking.
- Queue grouping.
- Agent state tracking.
- CSV export.
- Draggable dashboard.

### Changed

- Replaced raw data view with queue-centric dashboard.

---

## [1.0.0] - Initial Release

### Added

- AWS API interception.
- Agent extraction.
- State extraction.
- Duration extraction.
- Routing Profile extraction.
- Active slot extraction.
- Capacity extraction.
- Basic dashboard rendering.

---

# Upcoming

## [3.1.0] Planned

### Planned Features

- Queue filter buttons.
- Queue search.
- Longest Available indicator.
- Agent count indicator.
- Queue statistics summary.
- Improved profile sorting.

---

## [3.2.0] Planned

### Planned Features

- Queue Health status:
  - 🟢 Healthy
  - 🟠 Watch
  - 🔴 Critical

- Occupancy thresholds.
- Available staffing thresholds.
- Queue risk indicators.

