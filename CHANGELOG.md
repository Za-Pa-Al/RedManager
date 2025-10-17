- Added infinite scroll instead of pre-fetching all mods.
- Use sotf-mods api for searching with debounce.
- Added icons for navigation bar.
- UI overhaul.
- Fixed last updated indicator.
- Fixed image covers not showing.
- Fixed wrong image covers for mods after searching.

## v1.2.1 - 2025-10-17

- Align package and app versions (frontend `package.json` and `src-tauri/Cargo.toml`).
- Improve image caching: load from cache immediately and perform throttled background checks with limited concurrency.
