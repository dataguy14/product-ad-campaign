# Product Ad Campaign — Claude Skill

An [Agent Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) that turns a
product reference photo into a **premium, commercially persuasive advertising campaign visual**, or into a
ready-to-use image-generation prompt for one. It keeps the product itself exactly as it appears in the photo.

Claude works as a creative director, advertising photographer, art director and product stylist in one. It
reads the product, works out *why someone would want it*, and builds an original campaign scene around it.
Only the environment, lighting and storytelling are invented. The product is never redesigned.

> **Product fidelity > commercial appeal > visual storytelling > aesthetics > decoration**

---

## What it does

| Step | What Claude does |
|------|------------------|
| 1. Analyze | Reads the product's category, materials, finish, colors, branding, target customer and positioning |
| 2. Strategize | Decides what is being sold, why it's wanted, and the strongest psychological trigger (trust, desire, luxury, performance…) |
| 3. Concept | Designs an original campaign environment that fits the product's category, not a generic template |
| 4. Direct | Sets composition, camera and lens, lighting, material realism and color grading |
| 5. Adapt | Leaves clean space for headline/CTA and fits the frame to the target platform |
| 6. Quality check | Checks product fidelity, photographic realism, composition and advertising value, and removes AI artifacts |
| 7. Deliver | Generates the image if an image tool is available. Otherwise returns a detailed prompt, a negative prompt and a short creative rationale |

### Guardrails built in
- Never changes the product's shape, proportions, color, packaging, logos or labels
- Never invents branding, slogans, claims, certifications, awards, specs or pricing
- No random props, clutter, fake glow, lens flares or cliché sci-fi interfaces
- Adds people only when they genuinely help the story, with believable hand–object contact
- Aims for agency-grade photographic realism, not "AI art", CGI mockups or stock photography

---

## Installation

### Claude Code: personal (all projects)
```bash
git clone https://github.com/dataguy14/product-ad-campaign ~/.claude/skills/product-ad-campaign
```

### Claude Code: one project
```bash
git clone https://github.com/dataguy14/product-ad-campaign .claude/skills/product-ad-campaign
```

### Claude.ai / Claude desktop app
1. Download this repo as a ZIP (**Code → Download ZIP**) or zip the folder containing `SKILL.md`.
2. Go to **Settings → Capabilities → Skills** and upload the ZIP.
3. Enable the skill.

### Claude API / Agent SDK
Upload the folder as a custom skill. See the
[Agent Skills docs](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview).

---

## Usage

Attach a product photo and describe what you want. The skill triggers automatically on requests like these,
or you can run it directly with `/product-ad-campaign` in Claude Code.

**Example prompts**

- *"Create a premium Instagram ad for this serum bottle."*
- *"Turn this headphone photo into a website hero image with space for a headline on the left."*
- *"Write a Midjourney prompt for a luxury campaign shot of this watch."*
- *"LinkedIn launch visual for this medical device. It should feel trustworthy and modern."*
- *"E-commerce lifestyle shot of this chair in a sunlit architectural interior."*

**Tips**
- Use a clear, well-lit, front-facing product photo. The reference is the single source of truth.
- Name the platform (Instagram feed, Stories, LinkedIn, web hero…) to get the right composition and aspect ratio.
- Mention whether you plan to add copy, so Claude leaves clean negative space for it.
- Ask explicitly if you want something about the product changed, such as a color variant. Otherwise it is preserved.

### Output

When Claude can't generate the image itself, it returns:

1. **Creative rationale**: product read, chosen trigger, campaign concept, target platform
2. **Image prompt**: one detailed prompt covering scene, camera, lens, lighting, materials, composition and grading
3. **Negative prompt**: artifacts and failure modes to avoid

Paste the prompt into your image model of choice, together with the product reference image if the model
supports image references or editing.

---

## Repository structure

```
product-ad-campaign/
├── SKILL.md   # The skill: frontmatter (name, description) + full creative-direction instructions
└── README.md  # This file
```

## Customizing

Edit `SKILL.md` to change the defaults, for example to add brand guidelines, house styles, preferred
aspect ratios or a fixed output format. The `description` field in the frontmatter controls when Claude
picks the skill up automatically.

---

## Disclaimer

The skill tells Claude to preserve your product's existing branding and never invent logos, claims or
third-party trademarks. You are responsible for having the rights to the product images and brands you use,
and for reviewing generated visuals before publishing them.

Created by **Ali Raza**.
