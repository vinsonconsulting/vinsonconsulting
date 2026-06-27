# Jim Vinson

AI Product Manager and Technical Program Manager. I build operational AI systems:
pipelines and harnesses that do actual work, plus the operational, maintenance, and measurement layers that make them possible. 
My projects are architected and built from modular primitives, developed to allow for their own decomposition when desired. 

Most of the substantive builds are private client and product work. The
repositories pinned here are the parts I can show in full (or have explicit client permission to display). They are smaller than
the private work, but they are complete, and they carry the decisions behind them
in the open.

## limner: Agent Harness and Modular Primitives 

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

## phineas-case-study: Applied AI in Production

A public case study of PHINEAS, a CEFR teaching assistant I built and operate for an
English-language school: paste in a text and it returns the CEFR level, a
word-by-word vocabulary breakdown, and the passage rewritten to a new CEFR level. 

The product is live at [phineas.app](https://phineas.app); this
repo is the part I can show in full — the architecture write-up and a redacted,
runnable TypeScript reference implementation.

The decision worth reading: the CEFR levels are served from a bespoke corpus, not asked
of the model, so leveling is regulated before any model call is made. A human-gated
dual-loop flywheel feeds approved corrections back both ways — into the per-word
database lookups and into the model's training examples. Client identity and data
are redacted; the vocabulary is synthetic and the prompts paraphrased.

[vinsonconsulting/phineas-case-study](https://github.com/vinsonconsulting/phineas-case-study)

## Eval: Building Measurement Systems

A product manager's job includes building the measurement, not only the feature.
Two repos are that work.

[claude-skill-foundry](https://github.com/vinsonconsulting/claude-skill-foundry)
is a development and scoring harness for Claude skills. Each carded skill ships a Skill Card: a
recorded SkillSpector security scan, eval results, and trigger evals: generated and gated in CI
so the catalog cannot quietly drift from what was measured. Coverage is still
filling in (trigger precision/recall is the next measurement to land), and the catalog says so 
rather than printing a number it cannot back up.

[califa-cards](https://github.com/vinsonconsulting/califa-cards) is the
specification and toolkit underneath: the Skill Card schema, the security gate,
and the generators the foundry consumes as a dependency. It is the nutrition
label for an agent skill, plus the machinery that enforces it.

## lily-livered: Craft and Shipping Discipline

A one-page Astro site for domains that have an email address and not much else. I
keep it here as a sample of shipping discipline: semantic-version releases, Renovate for
dependencies, Biome for linting, and CI that runs Lighthouse three times per push
and takes the median (so the badge stays honest, and a bit less flakey).

[vinsonconsulting/lily-livered](https://github.com/vinsonconsulting/lily-livered)
· [live demo](https://lily-livered.jimvinson.com)

## Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Bun](https://img.shields.io/badge/Bun-000000?style=flat&logo=bun&logoColor=white)
![pydantic](https://img.shields.io/badge/pydantic-E92063?style=flat&logo=pydantic&logoColor=white)
![Claude](https://img.shields.io/badge/Claude-D97757?style=flat&logo=anthropic&logoColor=white)
![NVIDIA](https://img.shields.io/badge/NVIDIA-76B900?style=flat&logo=nvidia&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=flat&logo=cloudflare&logoColor=white)
![Cloudflare Workers](https://img.shields.io/badge/Cloudflare_Workers-F38020?style=flat&logo=cloudflareworkers&logoColor=white)
![Cloudflare Pages](https://img.shields.io/badge/Cloudflare_Pages-F38020?style=flat&logo=cloudflarepages&logoColor=white)
![Cloudflare D1](https://img.shields.io/badge/Cloudflare_D1-F38020?style=flat&logo=cloudflare&logoColor=white)
![Cloudflare R2](https://img.shields.io/badge/Cloudflare_R2-F38020?style=flat&logo=cloudflare&logoColor=white)
![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=flat&logo=googlecloud&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Astro](https://img.shields.io/badge/Astro-BC52EE?style=flat&logo=astro&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)

## Elsewhere

Portfolio, case studies, and credentials: [jimvinson.com](https://jimvinson.com). Find
me on [LinkedIn](https://www.linkedin.com/in/jimvinson/).

Open to full-time AI Product Manager, Technical Program Manager, or Operations
roles. Bay Area or genuine remote.
