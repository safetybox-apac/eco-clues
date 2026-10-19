# Eco Clues

A standalone sustainability game: four pictures, one word. Play individually on desktop or phone. No administrator, rooms, names, avatars, login or leaderboard.

## Deploy on GitHub Pages

1. Extract this ZIP. Create a separate repository such as eco-clues, or use the existing repository for this game.
2. Upload index.html, app.js, audio.js, styles.css, eco.css, puzzles.csv, .nojekyll and the complete images folder to the repository root. Keep images/pack1.jpg, images/pack2.jpg and images/pack3.jpg inside that folder. Upload files and folders, not the ZIP.
3. Commit to main. Under Settings → Pages, choose Deploy from a branch → main → / (root) → Save.
4. Open the Pages link after deployment, normally https://YOUR-USERNAME.github.io/eco-clues/.

No Apps Script, Assets.gs, setup function, API key or Google Sheet connection is required. The old Apps Script deployment is not changed by uploading this game. For local preview, run a web server in this directory (for example python -m http.server 8000); opening index.html directly may block puzzle-data loading.

## Player flow

Play on Desktop or Play on Phone → instructions → I'm ready → pictures finish preparing if necessary → 3–2–1 → game → score and answers.

Every new game lasts 10 minutes. The timer starts after the countdown and continues while settings, zoom, review or another tab is open. An early Finish requires confirmation. When time runs out, open dialogs close and results appear automatically.

Tap letter tiles or type a word, then Check answer. Feedback is immediate. Use Erase or Clear to revise the current guess. Wrong guesses cost no points and can be retried. Each solved word earns 3 points, or 2 if its hint has been used; it can score only once. The 15-word maximum is 45 points. Hint status persists through skipping, review and refresh.

Skip cycles through unsolved puzzles. Review opens the puzzle list and allows returning to any puzzle. Solved puzzles show their word; unsolved puzzles do not reveal answers during play. Solving all puzzles shows a completion screen from which players can finish immediately or review.

Results show solved/unsolved status, points, attempts and hint usage. Reveal answers displays the unsolved words and sustainability explanations. Desktop uses a review grid; phone shows one result at a time with Previous/Next.

## Pictures and phone layout

The 60 existing AI-generated clues are included in three image packs. They are downloaded silently on the home page; the game waits for successful preparation before starting its timer. No Google Drive image requests or external image hosts are used. Tap a clue to enlarge it. The AI-illustration notice is shown with the clues.

Phone mode keeps its timer and action controls outside the scrollable puzzle area. Normal play fits the tested 390×844 viewport. Small screens, enlarged text, hints, the software keyboard or long explanations can require scrolling within the puzzle area. Desktop offers a larger picture grid and keyboard input.

## Settings and recovery

Settings contains only music and sound-effects toggles. There is no password or timer editor. Music/effects default to on; the browser starts audio after a click, tap or key interaction. The lively soundtrack is synthesized locally and music pauses while the page is hidden.

Same-tab refresh restores progress, guesses, hints, letter arrangements and the original deadline when session storage is available. The timer does not pause during refresh. Play again creates a new shuffled game. Eco Clues uses its own saved-game and sound-preference keys.

## Edit puzzles.csv

The supplied 15 puzzles and their answer/hint/explanation/picture mappings are retained. Required headers:

Puzzle ID, Answer, Hint, Explanation, Picture 1, Picture 2, Picture 3, Picture 4, Enabled

Use unique IDs, answers of 2–20 English letters and Enabled = Yes or No. Include a hint and explanation for every enabled row. Answers normalize to uppercase. Puzzle order and each letter bank are shuffled for every new game.

Keep the existing builtin references to use the included pictures. A builtin reference identifies its image pack, row and column, such as builtin:1:0:0. Changing the answer alone does not change its pictures—keep all four clues consistent with the intended word.

To add your own pictures, put JPG, PNG or WebP files in images and use paths such as images/new-clue-1.jpg in the Picture columns. Use simple filenames containing letters, numbers, hyphens or underscores. Custom pictures display uncropped. The UI notice labels pictures as AI-generated, so use generated artwork or update that notice if introducing photographs.

Google Drive links are not supported in this standalone edition. Maintain the data in Sheets if preferred, then export the puzzle tab and replace puzzles.csv. Existing saved games retain their original puzzle snapshot until finished.

## Validation

Local Chromium checks passed for all 15 words and three picture packs, countdown and 10-minute timer, picture zoom, unlimited retries, 3-point and hinted 2-point scoring, prevention of repeat scoring, letter controls, phone viewport fit, refresh recovery, expiry with an open dialog, answer reveal and desktop results. Desktop and phone screenshots were visually checked. No browser JavaScript errors were recorded.

This package has not been published or tested on your work network. Test the deployed URL on your intended devices before the session.
 
