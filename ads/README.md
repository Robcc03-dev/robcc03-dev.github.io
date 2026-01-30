# TagWriter4CFS Ad Banners

This folder hosts ad banners for the TagWriter4CFS macOS app.

## Files
- **ads.json** - The manifest that the app reads to get banner info
- **tetrofit-ad.png** - Your TetroFit game banner (replace with actual 300x250 image)

## How to Update Ads

### Change the TetroFit App Store link:
1. Edit `ads.json`
2. Replace `id123456789` with your actual App Store ID
3. Commit and push

### Add a new banner:
1. Upload your image (PNG/JPG, 300x250 recommended) to this folder
2. Edit `ads.json` to add a new entry in the `banners` array
3. Commit and push

### Example adding a second banner:
```json
{
  "refreshSeconds": 21600,
  "banners": [
    {
      "image": "https://robcc03-dev.github.io/ads/tetrofit-ad.png",
      "click": "https://apps.apple.com/app/tetrofit/id123456789",
      "alt": "Play TetroFit",
      "weight": 100,
      "active": true
    },
    {
      "image": "https://robcc03-dev.github.io/ads/sponsor-banner.png",
      "click": "https://sponsor-site.com",
      "alt": "Sponsor banner",
      "weight": 50,
      "active": true
    }
  ]
}
```

The app will randomly pick banners based on their weight (higher weight = shown more often).

## Manifest URL
The TagWriter4CFS app loads: `https://robcc03-dev.github.io/ads/ads.json`
