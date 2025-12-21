# Implementation Plan

- [x] 1. Create embed files for new games




  - [ ] 1.1 Create pet-merge.embed
    - Use inline onclick pattern matching existing brainrot-merge-1.embed
    - Embed URL: https://html5.gamedistribution.com/31a8ddc1eef34b94a4347cd324970878/?gd_sdk_referrer_url=https://gamedistribution.com/games/pet-merge/
    - Game image: images/13/pet-merge.jpg


    - _Requirements: 1.1, 1.2, 5.1, 5.2, 5.3_

  - [x] 1.2 Create fruit-jam-merge-puzzle-game.embed


    - Embed URL: https://html5.gamedistribution.com/d1dde7ae11fa4cf7a6c08126c9118f09/?gd_sdk_referrer_url=https://gamedistribution.com/games/fruit-jam-merge-puzzle-game/
    - Game image: images/13/fruit-jam-merge-puzzle-game.jpg




    - _Requirements: 2.1, 2.2, 5.1, 5.2, 5.3_

  - [ ] 1.3 Create merge-fruit-2.embed
    - Embed URL: https://html5.gamedistribution.com/3cb2c3b36dca4446b037be38ddc12379/?gd_sdk_referrer_url=https://gamedistribution.com/games/merge-fruit-2/
    - Game image: images/13/merge-fruit-2.jpg
    - _Requirements: 3.1, 3.2, 5.1, 5.2, 5.3_

- [x] 2. Create Pet Merge game page



  - [-] 2.1 Create pet-merge.html





    - Follow brainrot-merge-1.html template structure




    - Include game sidebar with thumbnails (all existing games + 3 new games)
    - Add meta tags with "Pet Merge" keyword
    - Include Open Graph tags (og:title, og:description, og:image, og:url)


    - Include content sections: About, Beginner Guide, Advanced Strategy, Equipment Guide, Character Analysis




    - Add Baidu Analytics with ID 287aac72def1576b17d97ca57316c6d7
    - Maintain keyword density 2-5%, max 3 per paragraph
    - Add Related Keywords section with links to Pet Merge, Fruit Jam Merge Puzzle Game, Merge Fruit 2


    - _Requirements: 1.1, 1.3, 1.4, 1.5, 4.1, 4.2, 4.3, 4.4, 7.1-7.5, 10.1, 10.2, 11.1-11.3_








- [ ] 3. Create Fruit Jam Merge Puzzle Game page
  - [ ] 3.1 Create fruit-jam-merge-puzzle-game.html
    - Same structure as pet-merge.html with "Fruit Jam Merge Puzzle Game" keyword
    - _Requirements: 2.1, 2.3, 2.4, 2.5, 4.1, 4.2, 4.3, 4.4, 7.1-7.5, 10.1, 10.2, 11.1-11.3_

- [ ] 4. Create Merge Fruit 2 game page
  - [ ] 4.1 Create merge-fruit-2.html
    - Same structure as pet-merge.html with "Merge Fruit 2" keyword
    - _Requirements: 3.1, 3.3, 3.4, 3.5, 4.1, 4.2, 4.3, 4.4, 7.1-7.5, 10.1, 10.2, 11.1-11.3_

- [ ] 5. Update homepage and existing pages
  - [ ] 5.1 Update index.html game sidebars
    - Add Pet Merge, Fruit Jam Merge Puzzle Game, Merge Fruit 2 to left and right sidebars
    - Use game images from images/13/ directory
    - _Requirements: 6.1, 6.3_

  - [ ] 5.2 Update index.html Related Games section
    - Add links to Pet Merge, Fruit Jam Merge Puzzle Game, Merge Fruit 2 without .html suffix
    - _Requirements: 6.2, 11.1, 11.3_

- [ ] 6. Update site configuration files
  - [ ] 6.1 Update sitemap.xml
    - Add URLs for 3 new game pages without .html suffix
    - Update lastmod to 2025-12-21 for all entries including homepage
    - _Requirements: 8.1, 8.2, 8.3, 8.4_

  - [ ] 6.2 Verify robots.txt
    - Confirm /*.embed is already blocked
    - _Requirements: 5.4_

- [ ] 7. Final verification
  - [ ] 7.1 Verify all internal links use correct format (no .html suffix)
    - _Requirements: 11.1, 11.2, 11.3_

  - [ ] 7.2 Verify all pages include Baidu Analytics
    - _Requirements: 10.1, 10.2_
