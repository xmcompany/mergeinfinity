# Requirements Document

## Introduction

This specification covers the expansion of the mergeinfinity.com game website with three new game pages: Pet Merge, Fruit Jam Merge Puzzle Game, and Merge Fruit 2. Each game requires a dedicated HTML page with embedded gameplay, comprehensive game guides, and SEO-optimized content. The expansion follows the existing site architecture while maintaining consistent design patterns and Cloudflare Pages deployment requirements.

## Glossary

- **Embed File**: A minimal HTML document (.embed extension) that loads external game content via iframe, triggered by user interaction
- **Game Page**: A full HTML page containing the game embed, navigation, game guides, and related content
- **Keyword Density**: The percentage of target keyword occurrences relative to total word count (target: 2-5%)
- **Related Keywords Section**: A footer area displaying links to related game pages
- **Game Sidebar**: Navigation thumbnails surrounding the main game area for quick game switching

## Requirements

### Requirement 1

**User Story:** As a player, I want to access Pet Merge game on a dedicated page, so that I can play the game and learn strategies.

#### Acceptance Criteria

1. WHEN a user navigates to /pet-merge THEN the System SHALL display a game page with embedded Pet Merge gameplay
2. WHEN the game embed loads THEN the System SHALL use the embed URL https://html5.gamedistribution.com/31a8ddc1eef34b94a4347cd324970878/?gd_sdk_referrer_url=https://gamedistribution.com/games/pet-merge/
3. WHEN the page renders THEN the System SHALL display the game image from images/13/pet-merge.jpg
4. WHEN the page loads THEN the System SHALL include meta title and description containing "Pet Merge"
5. WHEN the content section renders THEN the System SHALL display beginner guide, advanced strategy, equipment guide, and character analysis sections

### Requirement 2

**User Story:** As a player, I want to access Fruit Jam Merge Puzzle Game on a dedicated page, so that I can play the game and learn strategies.

#### Acceptance Criteria

1. WHEN a user navigates to /fruit-jam-merge-puzzle-game THEN the System SHALL display a game page with embedded Fruit Jam Merge Puzzle Game gameplay
2. WHEN the game embed loads THEN the System SHALL use the embed URL https://html5.gamedistribution.com/d1dde7ae11fa4cf7a6c08126c9118f09/?gd_sdk_referrer_url=https://gamedistribution.com/games/fruit-jam-merge-puzzle-game/
3. WHEN the page renders THEN the System SHALL display the game image from images/13/fruit-jam-merge-puzzle-game.jpg
4. WHEN the page loads THEN the System SHALL include meta title and description containing "Fruit Jam Merge Puzzle Game"
5. WHEN the content section renders THEN the System SHALL display beginner guide, advanced strategy, equipment guide, and character analysis sections

### Requirement 3

**User Story:** As a player, I want to access Merge Fruit 2 game on a dedicated page, so that I can play the game and learn strategies.

#### Acceptance Criteria

1. WHEN a user navigates to /merge-fruit-2 THEN the System SHALL display a game page with embedded Merge Fruit 2 gameplay
2. WHEN the game embed loads THEN the System SHALL use the embed URL https://html5.gamedistribution.com/3cb2c3b36dca4446b037be38ddc12379/?gd_sdk_referrer_url=https://gamedistribution.com/games/merge-fruit-2/
3. WHEN the page renders THEN the System SHALL display the game image from images/13/merge-fruit-2.jpg
4. WHEN the page loads THEN the System SHALL include meta title and description containing "Merge Fruit 2"
5. WHEN the content section renders THEN the System SHALL display beginner guide, advanced strategy, equipment guide, and character analysis sections

### Requirement 4

**User Story:** As a content creator, I want game content to follow SEO best practices, so that pages rank well in search engines.

#### Acceptance Criteria

1. WHEN content is written THEN the System SHALL maintain keyword density between 2% and 5%
2. WHEN a paragraph is written THEN the System SHALL limit keyword occurrences to 3 or fewer per paragraph
3. WHEN meta tags are created THEN the System SHALL include the game name in title and description
4. WHEN Open Graph tags are added THEN the System SHALL include og:title, og:description, og:image, and og:url
5. WHEN content is authored THEN the System SHALL use natural language without AI-generated patterns or bulk keyword replacement

### Requirement 5

**User Story:** As a developer, I want embed files to follow the established pattern, so that games load consistently across all pages.

#### Acceptance Criteria

1. WHEN an embed file is created THEN the System SHALL use inline onclick with async function pattern
2. WHEN the play button is clicked THEN the System SHALL load the game iframe dynamically
3. WHEN the embed file is accessed directly THEN the System SHALL display a play button before loading the game
4. WHEN robots crawl the site THEN the System SHALL block /*.embed paths via robots.txt

### Requirement 6

**User Story:** As a site administrator, I want the homepage and game pages updated with new game links, so that visitors can discover new content.

#### Acceptance Criteria

1. WHEN the homepage loads THEN the System SHALL display game thumbnails including the three new games (Pet Merge, Fruit Jam Merge Puzzle Game, Merge Fruit 2)
2. WHEN the Related Games section renders THEN the System SHALL include links to all games including the three new ones
3. WHEN game thumbnails are clicked THEN the System SHALL navigate to the corresponding game page without .html suffix

### Requirement 7

**User Story:** As a player, I want each game page to display quick-switch thumbnails around the game area, so that I can easily navigate between different games.

#### Acceptance Criteria

1. WHEN a game page loads THEN the System SHALL display left sidebar with game thumbnail slots
2. WHEN a game page loads THEN the System SHALL display right sidebar with game thumbnail slots
3. WHEN thumbnails render THEN the System SHALL display game images from images/13/ directory for new games
4. WHEN the current game thumbnail renders THEN the System SHALL apply active styling to indicate current page
5. WHEN a thumbnail is clicked THEN the System SHALL navigate to that game's page

### Requirement 8

**User Story:** As a site administrator, I want the sitemap updated with new pages, so that search engines can index all content.

#### Acceptance Criteria

1. WHEN sitemap.xml is updated THEN the System SHALL include URLs for all three new game pages without .html suffix
2. WHEN sitemap entries are added THEN the System SHALL set lastmod to the current date (2025-12-21)
3. WHEN the homepage entry exists THEN the System SHALL update its lastmod to the current date
4. WHEN URLs are formatted THEN the System SHALL use / for homepage instead of /index.html

### Requirement 9

**User Story:** As a player on mobile, I want game pages to be responsive, so that I can play comfortably on any device.

#### Acceptance Criteria

1. WHEN the page loads on mobile THEN the System SHALL adapt layout for smaller screens
2. WHEN touch interactions occur THEN the System SHALL provide touch-friendly button sizes (minimum 44x44px)
3. WHEN the game container renders THEN the System SHALL maintain proper aspect ratio across screen sizes

### Requirement 10

**User Story:** As a site administrator, I want all pages to include analytics tracking, so that visitor behavior can be monitored.

#### Acceptance Criteria

1. WHEN any game page loads THEN the System SHALL include Baidu Analytics script
2. WHEN the analytics script initializes THEN the System SHALL use tracking ID 287aac72def1576b17d97ca57316c6d7

### Requirement 11

**User Story:** As a developer, I want all internal links to follow Cloudflare Pages conventions, so that routing works correctly.

#### Acceptance Criteria

1. WHEN internal links are created THEN the System SHALL omit .html suffix from URLs
2. WHEN linking to homepage THEN the System SHALL use / instead of /index.html
3. WHEN the Related Keywords section renders THEN the System SHALL display links without .html suffix
