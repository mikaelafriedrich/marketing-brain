Read the campaign brief at $ARGUMENTS. Also read icp.md, positioning.md, brand-voice.md, proof-points.md, testimonials.md, company-facts.md, products.md, and brand-guidelines.md.

Before writing anything, check the brief against company-facts.md and products.md: plans, pricing, which plan includes which feature, and any baseline numbers. If the brief conflicts with them, stop and ask me how to proceed.

Create every asset listed under "Assets needed" in the brief. Save each one as its own file in campaigns/[campaign-name]/ (use the campaign name from the brief, lowercase with hyphens).

Create any graphics the assets need (email headers, social images), following brand-guidelines.md. Save each image as campaigns/[campaign-name]/graphics/[campaign-name]-[asset].png and its editable source in campaigns/[campaign-name]/graphics/src/. Reference each image in its asset file with alt text.

Rules:
- Write for the audience named in the brief.
- Follow brand-voice.md closely.
- Every statistic or claim must come from proof-points.md, and every quote from testimonials.md (use the attribution format shown there). If you need a fact that isn't there, write [NEEDS SOURCE] instead of inventing one.
- Keep internal-only figures from the brief (adoption rates, churn, retention arguments) out of the assets.

Update the brief:
- Write proof points and quotes out in full, not just their IDs.
- Keep an "Assets and schedule" table listing each asset with a link to its file and graphic, a suggested go-live date, a "final by" date, and its status.
- Remove the prompts in parentheses from the field labels.

When finished, run the checks in .claude/commands/review.md on the campaign folder and fix any issues you find. Record the review and the fixes in the campaign's review-log.md, and link the log from the brief. Then give me a short summary of what you created and anything that needs my decision.
