## v0.19
- Added student-facing explanatory tooltips to buttons, input fields, mode controls, accordion headers, Live Performance measures, and Maximum Efficiency readouts.
- Prediction candidate buttons remain tooltip-free.
- Updated the visible version label to v0.19.

# Updates


## v0.17
- Changed startup defaults to **Full expanded model** vocabulary.
- Changed startup default for **Next-word prediction** to Off.
- Changed startup default for **Phrase prediction** to Off.
- Controls remain available so students can enable either prediction mode during experiments.

## v0.12
- Added **Words predicted** percentage to Maximum Efficiency / Optimal Route.
- Counts a word as predicted when a prediction action completes it; phrase selections can credit multiple target words.
- Added predicted-word count to the Optimal Route status.

## v0.11
- Fixed background frequency-table parsing; all 10,000 ranked entries now load at runtime.
- Added smoothed n-gram/frequency interpolation to improve short common-word prediction.
- Reserved approximately 70% of prediction-window slots for single words; the default 5-item window is 4 words + up to 1 phrase.
- Changed Target availability display to count / decision points plus a percentage.
- Retained all v0.9 layout, keyboard, target-passage, and test-history behavior.


## v0.7
- Added editable Target passage area in Test mode.
- Added paste-and-apply workflow for custom target passages.
- Added local `.txt` / `.md` target-file upload.
- Custom passages feed the same progress, prediction availability/rank, and miss metrics as built-in sample targets.
- Ctrl+Enter / Cmd+Enter applies an edited target passage.

## v0.6.1
- Added independent Next-word prediction ON/OFF control.
- With next-word prediction OFF, word-boundary predictions are suppressed while typed-prefix completion remains available.
- Anchored the main simulator workspace toward the bottom of the desktop viewport.
- Preserved physical number-row prediction selection: **1–9 → predictions 1–9; 0 → prediction 10**.
- Preserved all v0.4 vocabulary expansion and full-scope prefix-search improvements.

## v0.4
- Expanded local vocabulary coverage.
- Added everyday communication vocabulary promotion.
- Added mall and other common destination/activity examples.
- Prefix completion now searches the full selected scope.
- Verified physical number-row prediction selection: **1–9 → predictions 1–9; 0 → prediction 10**.
- Prediction shortcuts respect the selected 3–10 item window; inactive ranks do not intercept number keys.
- Numeric keypad keys are not treated as prediction shortcuts.

## v0.9
- Freeze Test-mode statistics on exact target completion and lock the composition field until restart/new target.
- Add Live target progress visibility toggle.
- Add single-open accordion behavior for the three right-side panes.


## v0.9
- Docked the Prediction Window to the bottom of the screen in Practice and Test modes.
- Moved Test History directly below Target Passage.
- Added a Test History visibility checkbox beside Live Target Progress; history is hidden by default.
- Kept Live Target Progress and Test History visibility independent.


## v0.11
- Added **Predicted but typed** count.
- Added **Prediction non-use rate** (% of completed target words that were available as predictions but were typed instead of selected).
- Added this measure to Test History.


## v0.17
- Default Characters before completion changed to 0.


## v0.17
- Made Test-mode parsing and optimal-route prediction punctuation-aware for commas and terminal punctuation.
- Removed prediction-button metadata line and enlarged/bolded number-row shortcut labels.


## v0.17
- Added physical `\` key as a pause/resume toggle.
- WPM and elapsed time freeze while paused; paused duration is excluded after resuming.
- Composition keys and prediction selections are disabled while paused.
- The pause key is a control and is not inserted into the composed message.

## v0.17
- Test trials now end when the participant/instructor selects **Finish trial**, not when the typed response exactly matches the target.
- The final response may contain unnoticed omissions, substitutions, spelling errors, or punctuation errors; timing and statistics freeze when Finish trial is selected.
- Exact target matching no longer auto-terminates a Test trial.

- v0.19: Added Predicted after typing count/rate to Live Performance and Test History; classification is based on the first time each target word appears in the prediction window.
