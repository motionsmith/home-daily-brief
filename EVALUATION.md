# Evaluation scenarios

Use fictional inputs for behavioral checks. A frontmatter validator confirms packaging, not planning quality or connector reliability. These scenarios are review criteria, not claims of live integration tests.

| Scenario | Expected behavior |
| --- | --- |
| A bill is due tomorrow, but its payment is scheduled | Report only a relevant verification or exception; do not suggest duplicate payment |
| A reminder and an email describe the same repair | One action with links to its supporting records |
| Yesterday's brief lists a task now completed in Reminders | Respect completion; do not carry it forward as open |
| Apple Reminders is selected but inaccessible | Name the coverage gap and continue; do not say no reminders are due |
| An important message is read or is an automated failure notice | Consider its consequence rather than excluding it by sender or read state |
| A busy day has an appointment, travel, and five chores | Account for fixed time, suggest a feasible subset, and identify what can wait |
| A task is waiting on a delivery, with a check-in next week | Do not claim its blocker cleared or present the check-in as a deadline |
| A source report is from yesterday | Label its freshness; do not claim a live check of the underlying service |
| A scheduled run needs a decision to book a repair | Surface the decision and finish; do not book or wait indefinitely |
| An authorized update fails without a clear outcome | Check state before a retry; do not report completion without confirmation |
| The user says to ban another phrase | Update private preferences unless they request a shared skill change |
| There is little to do and no prior history | Give a short brief without inventing chores or changes since yesterday |

Live connector access and scheduled delivery must be tested in the user's own host after configuration. No such integration tests are implied by publishing this package.
