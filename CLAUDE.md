# Claude Working Context — rachel smith (Salesforce SE)

## Who I am
Salesforce Solutions Engineer. I use Claude to build client-facing demos, architecture diagrams, decks, and strategic documents for enterprise accounts across commercial real estate, financial services, and enterprise SaaS.

## How to work with Claude (optimal setup)
**Always open Claude from `/Users/smithrachel/Documents/GitHub/se-demos/` or a subfolder inside it.**
This gives Claude full read/write access to both the client project files AND the git repo — so Claude can build files and publish to GitHub in the same session without any terminal handoff.

## Publishing demos
- **Demos repo (local):** `/Users/smithrachel/Documents/GitHub/se-demos/`
- **Demos repo (live):** `https://smithrachel-pf.github.io/se-demos/`
- **GitHub account:** `smithrachel-pf`
- **URL pattern:** `https://smithrachel-pf.github.io/se-demos/<filename>.html`
- **Git auth:** SSH only (`~/.ssh/config` → `id_ed25519_github`). Password/token auth does not work.

### To publish a new HTML file (when opened from se-demos/):
Claude can do this entirely — no terminal needed:
```bash
git add <filename>.html
git commit -m "<message>"
git pull --rebase
git push
```

## Client project folders
Each client has its own subfolder inside se-demos/:
- `M&M` — Marcus & Millichap leasing platform (data architecture diagram)
- `JLL`
- `Link Logistics Command Center`
- `CBRE`, `Equinox`, `GSA PBS`, `RWS`, `Related Rentals`, `Service Logic`, `Stockland`, `POD`, `BOE`, `Salesforce Brand`, `Slack Brand`, `Invisible CRM`, `_misc`

## Deliverable preferences
- HTML diagrams: self-contained single files, dark navy palette (`#0A1628`), no external dependencies
- Decks: PPTX via pptxgenjs
- Tone: consultant POV, not biased Salesforce employee — frank, honest about tradeoffs
- No JLL references in any client-facing output

## SLDS / Design System 2 Alignment Rules

Design system 2 starter kit repo: `git@github.com:salesforce-ux-emu/design-system-2-starter-kit.git`

When building or refactoring UI, always align with Salesforce's SLDS 2 standards:

1. **Component priority order** — check in this order before writing custom markup:
   1. Lightning Base Components (LBC) — e.g. `lightning-card`, `lightning-button`. Use real component names.
   2. Existing components already in this repo (e.g. global nav, example modal) — extend/match their pattern.
   3. SLDS Component Blueprints (HTML/CSS-only reference markup) — https://v1.lightningdesignsystem.com/components/overview/
   4. Only if none of the above fit: build a custom component, but it MUST use SLDS utility classes and global styling hooks (CSS variables) — never raw custom CSS.

2. **Never invent styles.** Use SLDS utility classes (https://www.lightningdesignsystem.com/2e1ef8501/p/05098e-utility-classes) and global styling hooks (https://www.lightningdesignsystem.com/2e1ef8501/p/591960-global-styling-hooks/b/768d36) instead of hardcoded colors, spacing, or fonts.

3. **Quality from the start, not a cleanup pass** — every component draft should already account for:
   - Realistic data states (empty, loading, error)
   - Accessibility basics (labels, contrast, keyboard nav)
   - Design-system alignment (no custom one-offs when a standard component exists)
   - Edge cases

4. **Verify, don't assume.** After generating/refactoring a component, explain what SLDS components/classes were used and why, so it can be checked against real SLDS docs before being trusted.

5. **Reference docs:**
   - Lightning Base Components: https://developer.salesforce.com/docs/platform/lightning-component-reference
   - SLDS overview: https://www.lightningdesignsystem.com/2e1ef8501/p/958017-develop
   - SLDS utility classes: https://www.lightningdesignsystem.com/2e1ef8501/p/05098e-utility-classes
   - Global styling hooks: https://www.lightningdesignsystem.com/2e1ef8501/p/591960-global-styling-hooks/b/768d36
