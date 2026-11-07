# Home Daily Brief

A daily planning skill for home and personal life. It checks the services you choose, helps decide what matters today, makes a realistic plan, and helps carry out next steps within your permissions.

It uses your assistant's existing connectors. It does not supply integrations, run a background service, or replace your task list. Adding a service means adding it to your private configuration once the assistant can access it.

Adapted from [AutomatedMarketer's morning-brief skill](https://github.com/AutomatedMarketer/cowork-ai-os/blob/64cdc9ebd9a7205b04e8a37fd528f57f53a60fef/cowork-ai-os/skills/morning-brief/SKILL.md), under the MIT license. The household focus and connector-independent setup replace the upstream business onboarding. The editable banned-language guidance is retained and expanded. See [NOTICE](NOTICE) and [LICENSE](LICENSE).

## Use it

The skill is in [`skills/home-daily-brief`](skills/home-daily-brief/SKILL.md). For Codex, copy that whole folder into your skills directory, normally `~/.codex/skills/`, then start a chat that can discover it. Other assistants that load `SKILL.md` can use the instructions, but their connector access, scheduling, and permissions differ. Codex UI metadata is included; other hosts may ignore it.

Start with a prompt like:

> Use $home-daily-brief to help me plan today and stay on top of things. Check my personal email, my selected Apple Reminders lists, and my calendar using your existing connectors. Tell me what matters, suggest a manageable plan, and help with the next steps. Use my local timezone. Flag sources you cannot check.

Name the actual accounts/lists to include. The skill cannot read a service until your host has working access to it; Apple Reminders is an example source, not a bundled or verified integration. More services can be added to the same prompt. No separate configuration framework is required.

For preferences you want to keep in a file, copy the [fictional example](skills/home-daily-brief/references/preferences.example.md) to a private workspace and point the assistant at it. Add personal language bans there. Shared editorial rules live in [writing-rules.md](skills/home-daily-brief/references/writing-rules.md).

## Schedule it

Test the skill interactively with your selected services first. Then use your assistant's scheduler with a prompt such as:

> Use $home-daily-brief. Read my private preferences at [your private preferences path]. Check every listed service through the existing connectors, reconcile unfinished items, and give me one short brief with a realistic plan. Carry out next steps only within my standing permissions. Deliver here. Flag missing or stale sources.

Replace the path with an actual private file, or put the service list directly in the prompt. Choose the timezone and schedule in the host. If scheduled runs cannot discover skills by name, configure them to read the installed `SKILL.md` by its actual path. Nothing runs just because this repository is installed.

## What the brief does

- Combines appointments, reminders, messages, bills, errands, home maintenance, and personal priorities when those sources are configured.
- Distinguishes deadlines from check-ins, and actionable tasks from waiting or already-scheduled work.
- Reconciles duplicate or completed obligations against their original records.
- Leaves room for travel, preparation, ordinary life, and rest.
- Reports actions actually completed and anything that needs your decision.
- Reports which sources were checked and where information is missing or stale.

It does not automatically send messages, pay bills, make bookings, change reminders, or create another authoritative task list. You can authorize specific actions or provide standing permissions in your host.

## Development and publishing

This is a portable instruction package, not an application. It has no executable dependencies or API keys. Keep personal configuration, real briefs, account identifiers, credentials, and household data outside this repository.

Publish this repository with its license and notices intact. A marketplace submission, if desired, is separate from publishing the source. Contributions that improve planning, coverage, follow-through, and plain language are welcome. See [the evaluation scenarios](EVALUATION.md) for review cases and verification limits.
