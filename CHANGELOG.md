# Changelog

Notes all versions and their respective changes.

## [0.4.1] - 2026-11-02

### Added

none

### Changes
- additional author infos
- `become: true` was missing for the handlers
- filename for the `munin-node.conf` file was missing when creating the config file from the template
- hints for installation cause role isn't published via ansible-galaxy
- updated supported version infos

## [0.4.0] - 2026-10-21

### Added
- CHANGELOG.md

### Changed
- author information
- additional metadata info for galaxy
- handler naming: `Restart munin-node` instead of `restart munin-node` in notifies and handlers differed from each other
- extended info in README.md for variable `munin_node_plugins`