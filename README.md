# Jim Vinson

AI Product Manager and Technical Program Manager. I build operational AI systems:
software that does real work, plus the harnesses and measurements that keep it
honest. The pattern runs both directions. I develop systems in order to deploy
them, and I deploy systems in order to build the next ones better.

Most of the substantive builds are private client and product work. The
repositories pinned here are the parts I can show in full. They are smaller than
the private work, but they are complete, and they carry the decisions behind them
in the open.

## limner: the flagship

A harnessed image-generation agent, built as a worked example of clean seams
between a model and its tools. Claude reasons, Cloudflare executes, D1 remembers.

The point of view: most agent demos hand a model an API key and hope. limner is
built the other way. The reasoning loop runs on Anthropic's managed agents
platform and never holds provider credentials. Tool execution runs in Cloudflare
Workers as deterministic TypeScript with explicit bindings. The seam between them
is an OAuth-gated MCP surface, the same contract any MCP client uses. Memory is a
database, not a context window, so the agent recalls what it recorded last week
instead of being re-told.

[vinsonconsulting/limner](https://github.com/vinsonconsulting/limner)

## The eval story: building the measurement

A product manager's job includes building the measurement, not only the feature.
Two repos are that work.

[claude-skill-foundry](https://github.com/vinsonconsulting/claude-skill-foundry)
is a library of portable Claude skills where each one ships a Skill Card: a
recorded SkillSpector security scan plus measured trigger metrics, gated in CI.
The catalog reads straight from the cards, so the numbers cannot quietly drift
from the truth. Coverage is still filling in (4 of 6 skills carded today), and the
catalog says so rather than printing a number it cannot back up.

[califa-cards](https://github.com/vinsonconsulting/califa-cards) is the standard
and tooling underneath: the schema, the security gate, and the generators the
cabinets consume as a dependency. It is the nutrition label for an agent skill,
plus the machinery that enforces it.

## lily-livered: craft and shipping discipline

A one-page Astro site for domains that have an email address and not much else. I
keep it here as a sample of how I ship: semantic-version releases, Renovate for
dependencies, Biome for linting, and CI that runs Lighthouse three times per push
and takes the median so the badge stays honest. The README is candid about its own
tradeoffs, including a deliberately absurd 72 KB logo that drags the performance
score down on purpose.

[vinsonconsulting/lily-livered](https://github.com/vinsonconsulting/lily-livered)
· [live demo](https://lily-livered.jimvinson.com)

## How I work

The polished prose in these repos is fair to question, so here is the human
fingerprint. limner's README documents a Deploy-to-Cloudflare button spike that
failed on 2026-06-12, why it failed (the button's monorepo mode severs a workspace
dependency), and what I shipped instead. The full decision records sit in
[the architecture document](https://github.com/vinsonconsulting/limner/blob/main/docs/Limner_Cloudflare_CMA_Architecture.md).
A failed spike written up with its cause is the part a text generator does not
produce on its own.

## Elsewhere

Portfolio, case studies, and credentials: [jimvinson.com](https://jimvinson.com).
A live product in the same vein: [phineas.app](https://phineas.app).

Open to full-time AI Product Manager, Technical Program Manager, or Operations
roles. Bay Area or genuine remote.
