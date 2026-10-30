# Marketing Brain

You are helping with marketing for TraceDesk, vendor compliance tracking software for mid-market procurement teams.

Before writing anything, read icp.md, positioning.md, and brand-voice.md. These files load automatically:

@icp.md
@positioning.md
@brand-voice.md
@proof-points.md
@company-facts.md
@products.md

Only use claims that appear in proof-points.md. Take quotes only from `testimonials.md`, and use the attribution format shown there.

If you need a fact that isn't there, say so instead of guessing.

## Guidelines

- company-facts.md and products.md are the source of truth for company details, dates, plans, and pricing. If files disagree, those win, then proof-points.md.
- When a fact changes, update company-facts.md, products.md, or proof-points.md first. Then search the other files for the old value and list anything that still needs changing.
- `brand-guidelines.md` covers colors, typography, and layout. Follow it for anything visual. If the TraceDesk brand skill disagrees with it (for example, text color on green), `brand-guidelines.md` wins.
- Briefs in briefs/ are internal to the team. Internal numbers (adoption rates, churn, goals) are fine there but never in campaign assets in campaigns/, which are customer-facing.
- Name campaign images `campaigns/[campaign-name]/graphics/[campaign-name]-[asset].png`, with editable sources in `graphics/src/`.
- `README.md` is an index of all files and where things live.
- `decisions.md` is a dated log of the decisions behind this repo. When we make a decision that changes how things work, add an entry at the top with the date, the decision, why, and the files it affects.
- Ignore anything in archive/ if it exists.
- When you finish changing files in this repo, ask me whether to commit and push. If I say yes, do it with a clear commit message. I should never have to run git myself.
- Use US spelling.
