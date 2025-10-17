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

### Commits since 1.1.9

- 73fd304 chore(release): bump version to v1.2.1 and update changelog (alexanderzazworka-sketch, 2025-10-17)
- b18fddc Include project layout diagram in README (Za-Pa-Al, 2025-10-17)
- af35197 Updated Badges (Za-Pa-Al, 2025-10-17)
- a16179e New Version. Tried circumventing .NET conflicts. (alexanderzazworka-sketch, 2025-10-17)
- e8338e0 Color Coding, Window adjustments. Image caching. (alexanderzazworka-sketch, 2025-10-16)
- 1734efa lazy load image and api update (Julian Kittel, 2025-02-10)

