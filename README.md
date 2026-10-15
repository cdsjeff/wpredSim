# Word Predictor Simulator v0.19

Standalone browser-based teaching simulator for physical-keyboard word and phrase prediction.



## What changed in v0.19
- Default vocabulary scope is now **Full expanded model**.
- **Next-word prediction** now starts **Off**.
- **Phrase prediction** now starts **Off**.
- All three settings remain adjustable during use.

## What changed in v0.12

- Maximum Efficiency / Optimal Route now reports **Words predicted** as a percentage of all target words.
- A target word counts as predicted when an optimal-route prediction selection completes that word. This includes prefix completion and each completed word supplied by a selected phrase prediction.
- The Optimal Route status also reports the count, e.g., **6 of 14 target words predicted**.

## What changed in v0.11

- Fixed a JavaScript escaping error that prevented the embedded 10,000-word frequency table from being parsed into the runtime model.
- Rebalanced next-word scoring with smoothed 1-, 2-, and 3-word context interpolation plus a persistent frequency prior. Sparse contexts no longer overwhelm common words as easily.
- Increased protection for short, high-frequency words in the ranking.
- Changed the default five-item mix from roughly 3 word + 2 phrase suggestions to 4 word + 1 phrase suggestion; larger windows reserve about 70% of slots for words.
- Live Performance now displays **Target available / decision points** as both a count and percentage. This is a per-decision-point availability measure, not the same thing as word-level miss rate or KSR.
- Preserved the bottom-docked prediction window, number-row access (1–9, 0), Test History toggle, right-side accordion, custom target passages, and completion freeze.


## What changed in v0.9

- Added an independent **Next-word prediction** toggle. When OFF, predictions disappear at word boundaries but prefix-based word completion remains active once typing begins.
- Shifted the simulator workspace toward the **bottom of the viewport** on desktop displays, while preserving normal scrolling when content exceeds the available height.
- Expanded Full vocabulary with approximately 62,500 American-English vocabulary entries, merged with the existing model.
- Preserved 500 / 2,000 / 10,000 / Full vocabulary-scope controls.
- Added an everyday-communication vocabulary boost so common places, activities, health, food, transportation, family, and device terms are available in practical prediction ranges.
- Added conversational examples involving **mall**, pharmacy, restaurant, library, bank, clinic, parking, groceries, theater, and prescription.
- Fixed prefix completion so it searches the **entire active vocabulary scope** after each character rather than only a small high-frequency slice.
- Prediction keys are mapped to the physical QWERTY number row: **1–9 select predictions 1–9; 0 selects prediction 10**. The numeric keypad is not used for prediction selection. This mapping has been interaction-tested with 3–10 item prediction windows.

## Prediction model

The model uses up to the previous three completed words. It backs off from 3-word to 2-word to 1-word context when needed. Partial-word input is used as a prefix filter, and phrase candidates are extended from the resulting context-sensitive word predictions.

## Running

Open `index.html` in a modern desktop browser. No server or API key is required.


## Prediction miss measure

In Test mode, **Prediction misses** is a word-level measure. A target word is credited as predicted if it appears anywhere in the prediction window at least once while that word is being composed. Correct multiword phrase predictions credit every target word contained in the matching phrase. If a target word is completed without ever appearing in the window, it counts as a miss. The display reports **miss count · miss percentage**, where the denominator is all completed target words evaluated so far. Completed trials also store the miss count and percentage in Test history.


## Target passages (v0.9)
In Test mode, the Target passage panel is editable. Paste a sentence or multi-sentence passage and choose **Use passage**, or choose **Upload text** to load a local `.txt` or `.md` file. The entire passage becomes the active target for progress, availability, rank, and miss statistics. Press Ctrl+Enter (Cmd+Enter on macOS) while editing to apply the passage quickly.


## v0.9 changes
- Test trials now end in a hard completion state: the timer stops, composition locks, prediction selection is disabled, and performance statistics remain frozen until restart or a new target.
- Added a **Live target progress** Show/Hide toggle in Test mode. This affects only visibility; scoring continues normally.
- Converted the three right-side panes—**Prediction settings**, **Live performance**, and **Model description**—to a single-open accordion. Opening one closes the other two.


## v0.9 layout changes
- The prediction window is docked to the bottom of the viewport in Practice and Test modes, so prediction buttons stay available while other content changes.
- Test History is moved directly below the Target Passage area.
- Test History is hidden by default and controlled by a checkbox beside the Live Target Progress checkbox.
- Live Target Progress and Test History visibility can be controlled independently.


### v0.11: Prediction uptake
Test mode now reports **Predicted but typed** and **Prediction non-use rate**. A word is counted as predicted-but-typed when it appeared in the prediction window during its composition but was completed by ordinary typing rather than selecting a prediction. The non-use rate divides those words by completed target words that were available as predictions.


### v0.19 punctuation and prediction-button changes
- Commas and terminal punctuation are preserved in Test targets, counted as ordinary keyboard activations, and treated as lexical boundaries.
- Target-aware prediction insertion no longer inserts a space before punctuation that the student must type.
- Prediction buttons now use a single line: the number-row shortcut is bold and the same size as the prediction text; the second “word/phrase · number” line was removed.


## Pause / resume
Press the physical **\** (backslash) key to pause or resume a trial. While paused, elapsed time and WPM are frozen, composition and prediction selection are blocked, and paused time is excluded from the timing measures. The backslash character is not entered into the message.


### Test trial completion
A Test trial begins with the first composition action and ends only when **Finish trial** is selected. Exact agreement with the target is not required; errors can remain in the final response. At Finish trial, elapsed time, WPM, and all live statistics freeze and the trial is added to Test History.


## v0.19 tooltips
Explanatory hover/focus tooltips are embedded throughout the interface for controls, fields, live metrics, and optimal-route measures. Prediction candidate buttons are intentionally excluded.


## v0.19 prediction timing measures
- **Predicted after typing** counts completed target words whose first appearance in the prediction window occurred only after one or more letters of that word had been typed.
- **Predicted after typing rate** = predicted-after-typing words divided by all completed target words that appeared in the prediction window at some point.
- Words first offered before any letters are typed count as immediate predictions. Later words inside a phrase prediction also count as immediate because no letters of those words have yet been typed.
