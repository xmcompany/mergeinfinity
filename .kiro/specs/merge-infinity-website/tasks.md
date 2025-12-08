# Implementation Plan

- [x] 1. Set up project structure and configuration files

  - [x] 1.1 Create directory structure (css/, js/, images/)


    - Create folders for organizing assets
    - _Requirements: 6.3_
  - [x] 1.2 Create _headers file for Cloudflare Pages


    - Configure Content-Type for .embed files as "text/html; charset=utf-8"
    - Add X-Content-Type-Options: nosniff
    - _Requirements: 6.3, 6.4_

  - [x] 1.3 Write unit test for _headers file content

    - Verify correct Content-Type configuration
    - _Requirements: 6.3, 6.4_

- [x] 2. Create game embed file

  - [x] 2.1 Create merge-infinity.embed file


    - Implement minimal HTML document structure
    - Add play button with inline onclick async handler
    - Load game from https://gamea.azgame.io/merge-infinity/
    - Reference implementation pattern from citybrawl.cc
    - _Requirements: 1.1, 1.2, 1.3, 1.4_

  - [x] 2.2 Write unit test for embed file structure

    - Verify async onclick pattern exists
    - Verify game URL is correct
    - _Requirements: 1.2_

- [x] 3. Create main stylesheet

  - [x] 3.1 Implement CSS reset and base styles


    - Write CSS reset/normalize rules
    - Define CSS custom properties for colors and fonts
    - Set up game-appropriate color scheme
    - _Requirements: 8.1, 8.2, 9.1_

  - [x] 3.2 Implement layout and game container styles

    - Create responsive layout using flexbox/grid
    - Style game container with min-height 600px
    - Add iframe styling with fullscreen support
    - _Requirements: 1.3, 4.1_

  - [x] 3.3 Implement responsive breakpoints

    - Add mobile breakpoints for screen width adaptation
    - Handle portrait and landscape orientations
    - Ensure touch-friendly button sizes (min 44x44px)
    - _Requirements: 4.1, 4.2, 4.3_
  - [x] 3.4 Write property test for touch target sizes


    - **Property 5: Touch Target Size Compliance**
    - **Validates: Requirements 4.2**
  - [x] 3.5 Implement typography and content styles


    - Style headings, paragraphs, and lists
    - Create game description section styles
    - _Requirements: 8.2_

  - [x] 3.6 Implement navigation and header styles

    - Style header with logo placement
    - Create responsive navigation menu
    - _Requirements: 2.2_
  - [x] 3.7 Implement footer styles


    - Style footer with links and copyright
    - _Requirements: 7.1_


- [x] 4. Create main JavaScript file

  - [x] 4.1 Implement site functionality

    - Add mobile menu toggle functionality
    - Implement smooth scroll behavior
    - _Requirements: 9.2_


- [ ] 5. Create homepage HTML
  - [x] 5.1 Create index.html with document structure

    - Set up HTML5 document with proper doctype
    - Add meta charset and viewport tags
    - Link CSS stylesheet
    - _Requirements: 2.1_

  - [ ] 5.2 Implement SEO meta tags
    - Add title tag containing "Merge Infinity"
    - Add meta description highlighting game features
    - Add Open Graph tags (og:title, og:description, og:image, og:url)
    - Add Twitter Card tags (twitter:card, twitter:title, twitter:description, twitter:image)

    - _Requirements: 3.1, 3.2, 3.3, 3.4_
  - [x] 5.3 Write unit test for SEO meta tags

    - Verify all required meta tags exist
    - Verify title contains game name
    - _Requirements: 3.1, 3.2, 3.3, 3.4_

  - [x] 5.4 Implement header section

    - Add logo element
    - Add H1 heading with "Merge Infinity"
    - Add navigation menu with internal links (no .html suffix)
    - _Requirements: 2.1, 2.2, 6.1, 6.2, 8.4_
  - [x] 5.5 Write property test for internal link format


    - **Property 7: Internal Link Format Compliance**
    - **Validates: Requirements 6.1**

  - [ ] 5.6 Write property test for homepage link format
    - **Property 8: Homepage Link Format**

    - **Validates: Requirements 6.2**
  - [x] 5.7 Implement game section

    - Add game container div
    - Add iframe loading merge-infinity.embed
    - Set width="100%", height="600px", allowfullscreen
    - _Requirements: 1.1, 1.3, 1.4_

  - [x] 5.8 Write unit test for iframe structure

    - Verify iframe src, dimensions, and allowfullscreen
    - _Requirements: 1.1, 1.3, 1.4_
  - [x] 5.9 Write game description content (600-1200 words)


    - Write introduction section about Merge Infinity
    - Write beginner's guide with entry-level tutorials
    - Write advanced strategy section for experienced players
    - Maintain keyword density 2-5% naturally
    - Limit "merge infinity" to ≤3 per paragraph
    - Use semantic HTML with proper heading hierarchy (h2, h3)
    - _Requirements: 2.3, 2.4, 2.5, 5.1, 5.2, 5.3, 5.4_

  - [x] 5.10 Write property test for content word count

    - **Property 1: Content Word Count Range**
    - **Validates: Requirements 2.3**
  - [x] 5.11 Write property test for keyword density

    - **Property 2: Keyword Density Compliance**
    - **Validates: Requirements 2.4**

  - [ ] 5.12 Write property test for per-paragraph keyword limit
    - **Property 3: Per-Paragraph Keyword Limit**

    - **Validates: Requirements 2.5**
  - [x] 5.13 Write property test for heading hierarchy

    - **Property 6: Heading Hierarchy Validity**
    - **Validates: Requirements 5.3**
  - [x] 5.14 Add images with alt text


    - Add game-related images where appropriate
    - Ensure all images have descriptive alt attributes
    - _Requirements: 3.5_

  - [ ] 5.15 Write property test for image alt text
    - **Property 4: Image Alt Text Presence**
    - **Validates: Requirements 3.5**

  - [x] 5.16 Implement footer section

    - Add footer links
    - Add copyright text
    - Add Baidu Analytics script before closing body tag
    - Use tracking ID: 471271538dd9956248c1e87cca4f271c
    - _Requirements: 7.1, 7.2_

  - [x] 5.17 Write unit test for analytics script

    - Verify script placement and tracking ID
    - _Requirements: 7.1, 7.2_

  - [ ] 5.18 Link JavaScript file
    - Add script tag for main.js
    - _Requirements: 9.2_

- [x] 6. Create favicon and branding assets

  - [x] 6.1 Create favicon.ico


    - Design game-themed favicon
    - Add favicon link in HTML head
    - _Requirements: 8.3_
  - [x] 6.2 Create logo asset

    - Design logo with game visual elements
    - Save as SVG for scalability

    - _Requirements: 8.4_
  - [x] 6.3 Create Open Graph image

    - Create og-image.jpg for social sharing
    - Recommended size: 1200x630px
    - _Requirements: 3.3_

- [x] 7. Final Checkpoint


  - Ensure all tests pass, ask the user if questions arise.
