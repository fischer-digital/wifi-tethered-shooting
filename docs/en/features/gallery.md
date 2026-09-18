# Gallery & Ratings

## Live Gallery

The app's gallery shows all photos received from your camera in a fast, optimized grid view.

### How It Works

1. Your camera sends a photo via FTP
2. The app detects the new file automatically (polling every 1–5 seconds)
3. A thumbnail is generated and displayed in the grid
4. Tap any photo for full-screen view with details

### Auto-Sync

| Mode | Polling Interval | Behavior |
|---|---|---|
| Live (default) | 1 second | New photos appear almost instantly |
| Browse | 5 seconds | Less frequent checks, better for reviewing |

When a new photo arrives in Live mode, it's automatically shown in full-screen view.

## Grid View

### Performance Optimizations

- **Virtual scrolling** – Only visible photos are rendered
- **Smart caching** – Thumbnails are cached in a local database for instant reload
- **Placeholder images** – Tiny placeholders shown while thumbnails load
- **Lazy loading** – Images load as they enter the viewport

### Photo Information

Each photo card shows:
- Thumbnail image
- Star rating (when "Show file info" is enabled)
- Tap to view full-screen

## Full-Screen View

Tap any photo to open it in full-screen mode:

- **EXIF data** – Camera model, lens, aperture, shutter speed, ISO, orientation
- **Star rating** – Rate photos from 1–5 stars
- **Swipe navigation** – Browse through photos

## Star Ratings

Rate your photos from ⭐ to ⭐⭐⭐⭐⭐ directly in the app.

- Ratings are stored locally in the app's database
- Useful for quick culling during a shoot
- Filter and sort by rating

## Sorting

Photos are sorted with the **newest first** by default. When a new photo arrives during a live shoot, it appears at the top of the grid.

## File Storage

| Property | Value |
|---|---|
| Storage location | `/storage/emulated/0/ShootingStudio/` |
| File naming | Uses original camera filename |
| Cache | SQLite database for thumbnails, EXIF, ratings |
| Cache cleanup | Automatic LRU eviction (>10,000 entries) |

## Thumbnail Generation

Thumbnails are generated natively for speed:

- **Resolution:** 500px (longest edge)
- **Rotation:** Automatic based on EXIF orientation (all 8 orientations supported)
- **Format:** JPEG
- **Storage:** Local SQLite database