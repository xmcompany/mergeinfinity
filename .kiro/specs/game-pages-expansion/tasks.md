# Implementation Plan

- [x] 1. Create embed files for new games




  - [ ] 1.1 Create idle-pop-merge.embed
    - Use inline onclick pattern matching existing merge-infinity.embed

    - Embed URL: https://html5.gamedistribution.com/1ae5b8b1590c4119bb5163d98b51be2c/?gd_sdk_referrer_url=https://gamedistribution.com/games/idle-pop-merge/
    - _Requirements: 1.1, 1.2, 6.1, 6.2, 6.3_

  - [ ] 1.2 Create cute-kitty-merge.embed
    - Embed URL: https://html5.gamedistribution.com/701576d8cb014f90a0612b091a556c64/?gd_sdk_referrer_url=https://gamedistribution.com/games/cute-kitty-merge/

    - _Requirements: 2.1, 2.2, 6.1, 6.2, 6.3_
  - [x] 1.3 Create brainrot-merge-1.embed




    - Embed URL: https://html5.gamedistribution.com/86689ca50c4d4239b7df5e20b45b6976/?gd_sdk_referrer_url=https://gamedistribution.com/games/brainrot-merge-1/
    - _Requirements: 3.1, 3.2, 6.1, 6.2, 6.3_
  - [ ] 1.4 Create brainrot-boing-boing-merge.embed
    - Embed URL: https://html5.gamedistribution.com/31a8ddc1eef34b94a4347cd324970878/?gd_sdk_referrer_url=https://gamedistribution.com/games/brainrot-boing-boing-merge/
    - _Requirements: 4.1, 4.2, 6.1, 6.2, 6.3_



- [x] 2. Create game page HTML files


  - [x] 2.1 Create idle-pop-merge.html


    - Follow index.html template structure




    - Include game sidebar with 6+6 thumbnails
    - Add meta tags with "Idle Pop Merge" keyword
    - Include content sections: About, Beginner Guide, Advanced Strategy, Equipment Guide, Character Analysis

    - Add Baidu Analytics with ID 287aac72def1576b17d97ca57316c6d7
    - Maintain keyword density 2-5%, max 3 per paragraph




    - _Requirements: 1.1, 1.3, 1.4, 1.5, 5.1, 5.2, 5.3, 5.4, 10.1, 10.2, 12.1-12.6_
  - [x] 2.2 Create cute-kitty-merge.html


    - Same structure as 2.1 with "Cute Kitty Merge" keyword




    - _Requirements: 2.1, 2.3, 2.4, 2.5, 5.1, 5.2, 5.3, 5.4, 10.1, 10.2, 12.1-12.6_
  - [x] 2.3 Create brainrot-merge-1.html






    - Same structure as 2.1 with "Brainrot Merge 1" keyword
    - _Requirements: 3.1, 3.3, 3.4, 3.5, 5.1, 5.2, 5.3, 5.4, 10.1, 10.2, 12.1-12.6_
  - [ ] 2.4 Create brainrot-boing-boing-merge.html
    - Same structure as 2.1 with "Brainrot Boing Boing Merge" keyword
    - _Requirements: 4.1, 4.3, 4.4, 4.5, 5.1, 5.2, 5.3, 5.4, 10.1, 10.2, 12.1-12.6_

- [ ] 3. Update homepage with new games
  - [ ] 3.1 Update index.html game sidebars
    - Left sidebar: Merge Infinity, Merge Infinity Lite, Idle Pop Merge, Cute Kitty Merge, Brainrot Merge 1, Brainrot Boing Boing Merge
    - Right sidebar: Same 6 games
    - Use game images from images/13/ directory
    - _Requirements: 7.1, 7.2, 7.3, 7.5_
  - [ ] 3.2 Update Related Games section
    - Add links to all 6 games without .html suffix
    - _Requirements: 7.4, 11.1, 11.3_

- [ ] 4. Update site configuration files
  - [ ] 4.1 Update sitemap.xml
    - Add URLs for 4 new game pages without .html suffix
    - Update lastmod to 2025-12-19 for all entries including homepage
    - _Requirements: 8.1, 8.2, 8.3, 8.4_
  - [ ] 4.2 Verify robots.txt
    - Confirm /*.embed is already blocked
    - _Requirements: 6.4_

- [ ] 5. Add CSS styles for game thumbnails with images
  - [ ] 5.1 Update css/style.css
    - Add .thumb-img class for game thumbnail images
    - Ensure responsive sizing for thumbnail images
    - _Requirements: 9.1, 9.2, 9.3, 12.3_

- [ ] 6. Final verification
  - [ ] 6.1 Verify all internal links use correct format (no .html suffix)
    - _Requirements: 11.1, 11.2, 11.3_
  - [ ] 6.2 Verify all pages include Baidu Analytics
    - _Requirements: 10.1, 10.2_
