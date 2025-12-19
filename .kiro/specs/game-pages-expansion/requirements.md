# Requirements Document

## Introduction

This specification covers the expansion of the mergeinfinity.com game website with four new game pages. Each game requires a dedicated HTML page with embedded gameplay, comprehensive game guides, and SEO-optimized content. The expansion follows the existing site architecture while maintaining consistent design patterns and Cloudflare Pages deployment requirements.

## Glossary

- **Embed File**: A minimal HTML document (.embed extension) that loads external game content via iframe, triggered by user interaction
- **Game Page**: A full HTML page containing the game embed, navigation, game guides, and related content
- **Keyword Density**: The percentage of target keyword occurrences relative to total word count (target: 2-5%)
- **Related Keywords Section**: A footer area displaying links to related game pages
- **Game Sidebar**: Navigation thumbnails surrounding the main game area for quick game switching

## Requirements

### Requirement 1

**User Story:** As a player, I want to access Idle Pop Merge game on a dedicated page, so that I can play the game and learn strategies.

#### Acceptance Criteria

1. WHEN a user navigates to /idle-pop-merge THEN the System SHALL display a game page with embedded Idle Pop Merge gameplay
2. WHEN the game embed loads THEN the System SHALL use the embed URL https://html5.gamedistribution.com/1ae5b8b1590c4119bb5163d98b51be2c/?gd_sdk_referrer_url=https://gamedistribution.com/games/idle-pop-merge/
3. WHEN the page renders THEN the System SHALL display the game image from images/13/idle-pop-merge.jpg
4. WHEN the page loads THEN the System SHALL include meta title and description containing "Idle Pop Merge"
5. WHEN the content section renders THEN the System SHALL display beginner guide, advanced strategy, equipment guide, and character analysis sections

### Requirement 2

**User Story:** As a player, I want to access Cute Kitty Merge game on a dedicated page, so that I can play the game and learn strategies.

#### Acceptance Criteria

1. WHEN a user navigates to /cute-kitty-merge THEN the System SHALL display a game page with embedded Cute Kitty Merge gameplay
2. WHEN the game embed loads THEN the System SHALL use the embed URL https://html5.gamedistribution.com/701576d8cb014f90a0612b091a556c64/?gd_sdk_referrer_url=https://gamedistribution.com/games/cute-kitty-merge/
3. WHEN the page renders THEN the System SHALL display the game image from images/13/cute-kitty-merge.jpg
4. WHEN the page loads THEN the System SHALL include meta title and description containing "Cute Kitty Merge"
5. WHEN the content section renders THEN the System SHALL display beginner guide, advanced strategy, equipment guide, and character analysis sections

### Requirement 3

**User Story:** As a player, I want to access Brainrot Merge 1 game on a dedicated page, so that I can play the game and learn strategies.

#### Acceptance Criteria

1. WHEN a user navigates to /brainrot-merge-1 THEN the System SHALL display a game page with embedded Brainrot Merge 1 gameplay
2. WHEN the game embed loads THEN the System SHALL use the embed URL https://html5.gamedistribution.com/86689ca50c4d4239b7df5e20b45b6976/?gd_sdk_referrer_url=https://gamedistribution.com/games/brainrot-merge-1/
3. WHEN the page renders THEN the System SHALL display the game image from images/13/brainrot-merge-1.jpg
4. WHEN the page loads THEN the System SHALL include meta title and description containing "Brainrot Merge 1"
5. WHEN the content section renders THEN the System SHALL display beginner guide, advanced strategy, equipment guide, and character analysis sections

### Requirement 4

**User Story:** As a player, I want to access Brainrot Boing Boing Merge game on a dedicated page, so that I can play the game and learn strategies.

#### Acceptance Criteria

1. WHEN a user navigates to /brainrot-boing-boing-merge THEN the System SHALL display a game page with embedded Brainrot Boing Boing Merge gameplay
2. WHEN the game embed loads THEN the System SHALL use the embed URL https://html5.gamedistribution.com/31a8ddc1eef34b94a4347cd324970878/?gd_sdk_referrer_url=https://gamedistribution.com/games/brainrot-boing-boing-merge/
3. WHEN the page renders THEN the System SHALL display the game image from images/13/brainrot-boing-boing-merge.jpg
4. WHEN the page loads THEN the System SHALL include meta title and description containing "Brainrot Boing Boing Merge"
5. WHEN the content section renders THEN the System SHALL display beginner guide, advanced strategy, equipment guide, and character analysis sections

### Requirement 5

**User Story:** As a content creator, I want game content to follow SEO best practices, so that pages rank well in search engines.

#### Acceptance Criteria

1. WHEN content is written THEN the System SHALL maintain keyword density between 2% and 5%
2. WHEN a paragraph is written THEN the System SHALL limit keyword occurrences to 3 or fewer per paragraph
3. WHEN meta tags are created THEN the System SHALL include the game name in title and description
4. WHEN Open Graph tags are added THEN the System SHALL include og:title, og:description, og:image, and og:url
5. WHEN content is authored THEN the System SHALL use natural language without AI-generated patterns or bulk keyword replacement

### Requirement 6

**User Story:** As a developer, I want embed files to follow the established pattern, so that games load consistently across all pages.

#### Acceptance Criteria

1. WHEN an embed file is created THEN the System SHALL use inline onclick with async function pattern
2. WHEN the play button is clicked THEN the System SHALL load the game iframe dynamically
3. WHEN the embed file is accessed directly THEN the System SHALL display a play button before loading the game
4. WHEN robots crawl the site THEN the System SHALL block /*.embed paths via robots.txt

### Requirement 7

**User Story:** As a site administrator, I want the homepage updated with new game links, so that visitors can discover new content.

#### Acceptance Criteria

1. WHEN the homepage loads THEN the System SHALL display game thumbnails in left sidebar (6 slots) and right sidebar (6 slots)
2. WHEN the left sidebar renders THEN the System SHALL display Merge Infinity, Merge Infinity Lite, Idle Pop Merge, Cute Kitty Merge, Brainrot Merge 1, and Brainrot Boing Boing Merge with corresponding images and links
3. WHEN the right sidebar renders THEN the System SHALL display the same six games (Merge Infinity, Merge Infinity Lite, Idle Pop Merge, Cute Kitty Merge, Brainrot Merge 1, Brainrot Boing Boing Merge) with corresponding images and links
4. WHEN the Related Games section renders THEN the System SHALL include links to all six games
5. WHEN game thumbnails are clicked THEN the System SHALL navigate to the corresponding game page without .html suffix

### Requirement 12

**User Story:** As a player, I want each game page to display quick-switch thumbnails around the game area, so that I can easily navigate between different games.

#### Acceptance Criteria

1. WHEN a game page loads THEN the System SHALL display left sidebar with 6 game thumbnail slots
2. WHEN a game page loads THEN the System SHALL display right sidebar with 6 game thumbnail slots
3. WHEN thumbnails render THEN the System SHALL display game images from images/13/ directory for new games
4. WHEN the current game thumbnail renders THEN the System SHALL apply active styling to indicate current page
5. WHEN a thumbnail is clicked THEN the System SHALL navigate to that game's page
6. WHEN empty slots exist THEN the System SHALL display placeholder styling with "Coming Soon" indicator

### Requirement 8

**User Story:** As a site administrator, I want the sitemap updated with new pages, so that search engines can index all content.

#### Acceptance Criteria

1. WHEN sitemap.xml is updated THEN the System SHALL include URLs for all four new game pages without .html suffix
2. WHEN sitemap entries are added THEN the System SHALL set lastmod to the current date
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
