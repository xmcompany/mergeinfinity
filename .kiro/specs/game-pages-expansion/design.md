# Design Document

## Overview

This design document outlines the technical implementation for expanding mergeinfinity.com with four new merge game pages. The expansion follows the existing site architecture, reusing CSS styles and page templates while adding game-specific content and embed files.

## Architecture

The website follows a static site architecture deployed on Cloudflare Pages:

```
mergeinfinity.com/
├── index.html                    # Homepage (updated)
├── merge-infinity.embed          # Existing embed
├── merge-infinity-lite.html      # Existing page
├── idle-pop-merge.html           # New game page
├── idle-pop-merge.embed          # New embed file
├── cute-kitty-merge.html         # New game page
├── cute-kitty-merge.embed        # New embed file
├── brainrot-merge-1.html         # New game page
├── brainrot-merge-1.embed        # New embed file
├── brainrot-boing-boing-merge.html    # New game page
├── brainrot-boing-boing-merge.embed   # New embed file
├── css/style.css                 # Shared styles
├── images/13/                    # New game images
├── sitemap.xml                   # Updated sitemap
└── robots.txt                    # Already configured
```

## Components and Interfaces

### 1. Embed File Component

Each game requires an embed file (.embed) that:
- Displays a play button on initial load
- Uses inline onclick with async pattern (matching existing implementation)
- Dynamically creates iframe when user clicks play
- Loads game from GameDistribution CDN

Template structure:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <meta name="robots" content="noindex, nofollow">
  <title>{Game Name}</title>
  <style>/* Inline styles for play button and wrapper */</style>
</head>
<body>
  <div class="game-wrapper" id="wrapper">
    <button class="play-btn" id="playBtn">▶ Play {Game Name}</button>
  </div>
  <script>
    document.getElementById('playBtn').onclick = function() {
      // Load game iframe dynamically
    };
  </script>
</body>
</html>
```

### 2. Game Page Component

Each HTML page follows the existing template with:
- Header with logo and navigation
- Game section with sidebar thumbnails (6 left + 6 right)
- Main game container with iframe loading .embed file
- Game toolbar (fullscreen, share buttons)
- Content sections (About, Beginner Guide, Advanced Strategy, Equipment, Characters)
- Related Keywords section
- Footer with analytics

### 3. Game Sidebar Component

The sidebar displays 12 game thumbnails (6 per side):

Left Sidebar:
1. Merge Infinity (/)
2. Merge Infinity Lite (/merge-infinity-lite)
3. Idle Pop Merge (/idle-pop-merge)
4. Cute Kitty Merge (/cute-kitty-merge)
5. Brainrot Merge 1 (/brainrot-merge-1)
6. Brainrot Boing Boing Merge (/brainrot-boing-boing-merge)

Right Sidebar:
1-6. Same games repeated for accessibility

Thumbnail structure:
```html
<a href="/game-slug" class="game-thumb" title="Game Name">
  <img src="/images/13/game-image.jpg" alt="Game Name" class="thumb-img">
  <span class="thumb-name">Game Name</span>
</a>
```

## Data Models

### Game Configuration
```javascript
const games = [
  {
    name: "Merge Infinity",
    slug: "/",
    embedUrl: null, // Uses existing embed
    image: "/images/logo.svg",
    icon: "∞"
  },
  {
    name: "Merge Infinity Lite", 
    slug: "/merge-infinity-lite",
    embedUrl: null,
    image: "/images/logo.svg",
    icon: "∞"
  },
  {
    name: "Idle Pop Merge",
    slug: "/idle-pop-merge",
    embedUrl: "https://html5.gamedistribution.com/1ae5b8b1590c4119bb5163d98b51be2c/...",
    image: "/images/13/idle-pop-merge.jpg"
  },
  {
    name: "Cute Kitty Merge",
    slug: "/cute-kitty-merge", 
    embedUrl: "https://html5.gamedistribution.com/701576d8cb014f90a0612b091a556c64/...",
    image: "/images/13/cute-kitty-merge.jpg"
  },
  {
    name: "Brainrot Merge 1",
    slug: "/brainrot-merge-1",
    embedUrl: "https://html5.gamedistribution.com/86689ca50c4d4239b7df5e20b45b6976/...",
    image: "/images/13/brainrot-merge-1.jpg"
  },
  {
    name: "Brainrot Boing Boing Merge",
    slug: "/brainrot-boing-boing-merge",
    embedUrl: "https://html5.gamedistribution.com/31a8ddc1eef34b94a4347cd324970878/...",
    image: "/images/13/brainrot-boing-boing-merge.jpg"
  }
];
```



## Correctness Properties

*A property is a characteristic or behavior that should hold true across all valid executions of a system-essentially, a formal statement about what the system should do. Properties serve as the bridge between human-readable specifications and machine-verifiable correctness guarantees.*

Based on the prework analysis, the following properties can be verified:

Property 1: Meta Tag Game Name Inclusion
*For any* game page, the meta title and meta description tags SHALL contain the game's name.
**Validates: Requirements 1.4, 2.4, 3.4, 4.4, 5.3**

Property 2: Keyword Density Compliance
*For any* game page content, the keyword density SHALL be between 2% and 5%.
**Validates: Requirements 5.1**

Property 3: Per-Paragraph Keyword Limit
*For any* paragraph in game page content, the keyword occurrences SHALL be 3 or fewer.
**Validates: Requirements 5.2**

Property 4: Internal Link Format Compliance
*For any* internal link (href attribute pointing to site pages), the URL SHALL NOT contain .html suffix.
**Validates: Requirements 11.1, 11.2**

Property 5: Sitemap URL Format
*For any* URL in sitemap.xml, the path SHALL NOT contain .html suffix and homepage SHALL use /.
**Validates: Requirements 8.1, 8.4**

Property 6: Analytics Script Presence
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

### Property-Based Tests
- Use fast-check library for JavaScript property testing
- Test keyword density calculation across generated content
- Test link format validation across all href attributes
- Test meta tag content extraction and validation

### Manual Testing
- Visual verification of responsive layout
- Game loading and playability
- Cross-browser compatibility
