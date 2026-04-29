# Changelog

All notable changes to Lumia Bridge are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Entries before the first release were reconstructed from internal development history.

## [2026.04] - 2026-04-29

_Static builds on the edge_

### Changed

- **app** — The interface ships as a static bundle served from an edge network, cutting load time and removing the runtime server

### Security

- **app** — Source maps are no longer published with the production build

## [2026.02] - 2026-02-22

_Self-hosted relaying, published as configuration_

### Added

- **deployment** — Deployment configuration and step-by-step documentation for running the validator and relayer that carry messages in and out of Lumia
- **deployment** — Core configuration for the Lumia Beam and BNB Smart Chain test networks
- **deployment** — Documentation of the paymaster setup covering how transfer fees are quoted and settled

## [2025.07] - 2025-07-07

_Hardened delivery and an upstream sync_

### Changed

- **app** — Synced with the upstream Hyperlane transfer interface, bringing multi-collateral transfer limits and message identifier parsing
- **app** — Networks that are not currently available no longer appear as selectable in the transfer form
- **app** — Token and route metadata is read from the public Hyperlane registry rather than a bundled copy

### Security

- **app** — Content Security Policy tightened and debug logging removed from the production build

## [2025.04] - 2025-04-18

_Display fixes and refreshed app assets_

### Changed

- **app** — Application icons, favicons, logo and background imagery have been refreshed
- **deployment** — The build and hosting pipeline has been reworked for more reliable releases

### Fixed

- **app** — Color values are now handled consistently across the interface, preventing incorrect or missing colors in several views
