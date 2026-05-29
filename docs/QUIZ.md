# Quiz technical notes

This document explains how the interactive placement quiz in `index.html` works and how to update the assessment content.

Location

- UI container: [index.html](index.html#L1702)
- Script that parses tables and scores: [index.html](index.html#L2276)
- Answer key tables (hidden by default): [index.html](index.html#L921)

How it works

- The quiz script reads the rows from the hidden assessment tables and builds an internal `quizData` array.
- Supported item types (detected from the "Type" column):
  - MCQ / Multiple choice (single answer)
  - Multiple select
  - Matching (left/right pairs)
  - Sentence ordering
  - Fill-in-the-blank / translation / reading
- The engine normalizes user input and compares against the keyed answer(s). For sentence ordering and matching, specific parsing rules are used.

Editing items

- Update or add rows inside the assessment tables in the Placement Test section.
- Maintain the same column order as the existing tables (ID, Level, Type, Question, Options/Prompt, Answer, Explanation).
- For MCQ options, list options on separate lines with optional labels (A. ..., B. ...).
- For matching, place left items prefixed with numbers (1. ...) and right items prefixed with letters (A. ...). The answer cell should use mappings like `1-A,2-C`.

Customizing scoring

- The current scoring is 1 point per item. Adjust the scoring logic inside the script in `index.html` if you need differential weighting.

Debugging

- If the quiz finds no data, ensure the assessment tables are present and that `.assessment-card` elements are in the DOM.
- To reveal the hidden answer-key tables in the UI, click the "Show detailed answer key" button in the Placement Test section.

Extending

- To add audio for listening items, include audio elements in the question prompt and update the parsing rules to extract transcript and audio source.
- To persist progress across sessions, integrate `localStorage` saving where `state.answers` is updated.

Contact

- Add questions or propose changes via the repository issues or a PR with the relevant content and a note explaining the change.
