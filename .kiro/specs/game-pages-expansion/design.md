# Design Document

## Overview

This design document outlines the technical implementation for expanding mergeinfinity.com with three new merge game pages: Pet Merge, Fruit Jam Merge Puzzle Game, and Merge Fruit 2. The expansion follows the existing site architecture, reusing CSS styles and page templates while adding game-specific content and embed files.

## Architecture

The website follows a static site architecture deployed on Cloudflare Pages:

```
mergeinfinity.com/
├── index.html                           # Homepage (updated with new games)
├── pet-merge.html                       # New game page
├── pet-merge.embed                      # New embed file
├── fruit-jam-merge-puzzle-game.html     # New game page
├── fruit-jam-merge-puzzle-game.embed    # New embed file
├── merge-fruit-2.html                   # New game page
├── merge-fruit-2.embed                  # New embed file
├── css/style.css                        # Shared styles (existing)
├── images/13/                           # Game images directory
│   ├── pet-merge.jpg                    # New game image
│   ├── fruit-jam-merge-puzzle-game.jpg  # New game image
│   └── merge-fruit-2.jpg                # New game image
├── sitemap.xml                          # Updated sitemap
└── robots.txt                           # Already configured
```

## Components and Interfaces

### 1. Embed File Component

Each game requires an embed file (.embed) that:
- Displays a play button with game cover image on initial load
- Uses inline onclick pattern (matching existing implementation)
- Dynamically creates iframe when user clicks play
- Loads game from GameDistribution CDN

Template structure (following existing brainrot-merge-1.embed pattern):
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <meta name="robots" content="noindex, nofollow, noodp, noydir">
  <title>{Game Name}</title>
  <style>/* Inline styles for play button and wrapper */</style>
</head>
<body>
  <div class="game-wrapper" id="wrapper">
    <img src="images/13/{game-slug}.jpg" alt="{Game Name}" class="game-cover">
    <button class="play-btn" id="playBtn">▶ Play {Game Name}</button>
  </div>
  <script>
    document.getElementById('playBtn').onclick = function() {
      var wrapper = document.getElementById('wrapper');
      wrapper.innerHTML = '<div class="loading">Loading game...</div>';
      var iframe = document.createElement('iframe');
      iframe.className = 'game-frame';
      iframe.src = '{EMBED_URL}';
      iframe.allowFullscreen = true;
      iframe.allow = 'fullscreen';
      wrapper.innerHTML = '';
      wrapper.appendChild(iframe);
    };
  </script>
</body>
</html>
```

### 2. Game Page Component

Each HTML page follows the existing template (brainrot-merge-1.html pattern) with:
- Header with logo and navigation
- Game section with sidebar thumbnails (left + right)
- Main game container with iframe loading .embed file
- Game toolbar (fullscreen, share buttons)
- Content sections (About, Beginner Guide, Advanced Strategy, Equipment, Characters)
- Related Keywords section with links to Pet Merge, Fruit Jam Merge Puzzle Game, Merge Fruit 2
- Footer with Baidu Analytics (ID: 287aac72def1576b17d97ca57316c6d7)

### 3. Game Sidebar Component

The sidebar displays game thumbnails for quick navigation:

Games to include in sidebars:
1. Merge Infinity (/)
2. Merge Infinity Lite (/merge-infinity-lite)
3. Idle Pop Merge (/idle-pop-merge)
4. Cute Kitty Merge (/cute-kitty-merge)
5. Brainrot Merge 1 (/brainrot-merge-1)
6. Brainrot Boing Boing Merge (/brainrot-boing-boing-merge)
7. Pet Merge (/pet-merge) - NEW
8. Fruit Jam Merge Puzzle Game (/fruit-jam-merge-puzzle-game) - NEW
9. Merge Fruit 2 (/merge-fruit-2) - NEW

Thumbnail structure:
```html
<a href="/game-slug" class="game-thumb" title="Game Name">
  <img src="/images/13/game-image.jpg" alt="Game Name" class="thumb-img">
  <span class="thumb-name">Short Name</span>
</a>
```

## Data Models

### New Game Configuration
```javascript
const newGames = [
  {
    name: "Pet Merge",
    slug: "/pet-merge",
    embedUrl: "https://html5.gamedistribution.com/31a8ddc1eef34b94a4347cd324970878/?gd_sdk_referrer_url=https://gamedistribution.com/games/pet-merge/",
    image: "/images/13/pet-merge.jpg",
    shortName: "Pet Merge"
  },
  {
    name: "Fruit Jam Merge Puzzle Game",
    slug: "/fruit-jam-merge-puzzle-game",
    embedUrl: "https://html5.gamedistribution.com/d1dde7ae11fa4cf7a6c08126c9118f09/?gd_sdk_referrer_url=https://gamedistribution.com/games/fruit-jam-merge-puzzle-game/",
    image: "/images/13/fruit-jam-merge-puzzle-game.jpg",
    shortName: "Fruit Jam"
  },
  {
    name: "Merge Fruit 2",
    slug: "/merge-fruit-2",
    embedUrl: "https://html5.gamedistribution.com/3cb2c3b36dca4446b037be38ddc12379/?gd_sdk_referrer_url=https://gamedistribution.com/games/merge-fruit-2/",
    image: "/images/13/merge-fruit-2.jpg",
    shortName: "Merge Fruit 2"
  }
];
```

## Content Writing Guidelines

### SEO Requirements
- Keyword density: 2-5% (calculated as keyword occurrences / total words)
- Maximum 3 keyword occurrences per paragraph
- Natural language flow, no AI-generated patterns
- No bulk keyword replacement

### Content Sections for Each Game Page
1. **About Section** - Game overview and unique features
2. **Beginner's Guide** - Entry-level tutorial with basic mechanics
3. **Advanced Strategies** - Tips for experienced players
4. **Equipment/Items Guide** - In-game items and their uses
5. **Characters/Collections** - Character tiers and progression



## Correctness Properties

*A property is a characteristic or behavior that should hold true across all valid executions of a system-essentially, a formal statement about what the system should do. Properties serve as the bridge between human-readable specifications and machine-verifiable correctness guarantees.*

Based on the prework analysis, the following properties can be verified:

Property 1: Meta Tag Game Name Inclusion
*For any* game page HTML file, the meta title tag and meta description tag SHALL contain the game's name.
**Validates: Requirements 1.4, 2.4, 3.4, 4.3**

Property 2: Keyword Density Compliance
*For any* game page content, the keyword density SHALL be between 2% and 5%.
**Validates: Requirements 4.1**

Property 3: Per-Paragraph Keyword Limit
*For any* paragraph in game page content, the keyword occurrences SHALL be 3 or fewer.
**Validates: Requirements 4.2**

Property 4: Open Graph Tags Presence
*For any* game page HTML file, the document SHALL contain og:title, og:description, og:image, and og:url meta tags.
**Validates: Requirements 4.4**

Property 5: Embed File Pattern Compliance
*For any* embed file (.embed), the document SHALL contain an inline onclick handler that creates an iframe element.
**Validates: Requirements 5.1**

Property 6: Internal Link Format Compliance
*For any* internal link (href attribute pointing to site pages), the URL SHALL NOT contain .html suffix.
**Validates: Requirements 6.3, 11.1, 11.2, 11.3**

Property 7: Sitemap URL Format
*For any* URL in sitemap.xml, the path SHALL NOT contain .html suffix and homepage SHALL use /.
**Validates: Requirements 8.1, 8.4**

Property 8: Analytics Script Presence
*For any* game page HTML file, the document SHALL contain Baidu Analytics script with tracking ID 287aac72def1576b17d97ca57316c6d7.
**Validates: Requirements 10.1, 10.2**

## Error Handling

- Missing game images: Display placeholder or fallback to logo.svg
- Failed embed load: Show error message with retry button
- Invalid URLs: Redirect to homepage

## Testing Strategy

### Unit Tests
- Verify embed file structure contains play button and onclick handler
- Verify HTML pages contain required meta tags
- Verify sitemap contains all new URLs
- Verify robots.txt blocks .embed files

### Manual Testing
- Visual verification of responsive layout
- Game loading and playability
- Cross-browser compatibility
- Keyword density verification using word count tools
