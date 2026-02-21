# Box Learning Method (Leitner System)

## Overview

The Box Learning Method (also called the Leitner System) is a spaced-repetition technique for learning with flashcards. Cards are sorted into boxes that determine review frequency: easier cards move to boxes reviewed less often, while difficult cards return to the first box for frequent review.

## How it works

- Prepare a set of flashcards (question on one side, answer on the other).
- Initialize all cards in Box 1 (the review-every-session box).
- During a study session, review cards from Box 1 and any other boxes scheduled for that session.
- If you recall a card correctly, move it to the next higher-numbered box.
- If you fail to recall a card, move it back to Box 1.

Each box has an associated interval. Example schedule:

- Box 1: every session (daily)
- Box 2: every 2 sessions
- Box 3: every 4 sessions
- Box 4: every 8 sessions

Adjust intervals to match your needs (hours/days/weeks).

## Example workflow

1. Start a session and draw cards from boxes scheduled for today.
2. For each card:
   - Attempt recall.
   - If correct, promote the card to the next box.
   - If incorrect, demote the card to Box 1.
3. End session; mark the session index (or date) so scheduling uses it.

## Simple algorithm (pseudocode)

```pseudocode
session += 1
for box in boxes:
  if session % box.interval == 0:
    for card in box.cards:
      if test(card):
        move card -> next box
      else:
        move card -> box1
```

## Implementation notes

- Store for each card: `question`, `answer`, `box_index`, `last_seen_session`.
- Use either discrete session counters (1,2,3...) or real dates with intervals in days.
- When scaling, consider randomized selection from large boxes to limit session length.
- Optionally add graded correctness (partial credit) to fine-tune movement.

## Tips

- Keep sessions short and regular.
- Add new cards in small batches to avoid overload.
- Adjust box intervals based on retention and available study time.

---

If you want, I can add a small code example (JavaScript or Python) and a test harness in this repo.
