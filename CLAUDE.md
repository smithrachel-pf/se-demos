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
