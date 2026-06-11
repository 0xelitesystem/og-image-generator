# og-image-generator

Generate Open Graph social cards from text input. 1200x630, ready to download. Browser-only, no signup, no Canva.

**Live demo:** https://0xelitesystem.github.io/og-image-generator/

## Why

Every blog post and landing page should have a custom social card so it looks like something when shared on Twitter/X, LinkedIn, Slack, iMessage. Most people skip this step because the existing tools are all overkill: Canva wants an account, Figma wants a workspace, and design-from-scratch takes 20 minutes per card.

This tool does one thing: type a title, pick a layout and color scheme, download a PNG. 30 seconds per card.

## Use it

Open `index.html` in any browser. Or visit the hosted version at `https://0xelitesystem.github.io/og-image-generator/` once GitHub Pages is enabled.

1. Pick a layout: Centered, Left-aligned, Top banner, or Side bar
2. Pick a color scheme from 8 presets (Ink, Paper, Ocean, Forest, Sunset, Violet, Linen, Graphite)
3. Type a title, optional subtitle, optional badge
4. Pick a heading font (Sans, Slab, Serif, Mono)
5. Click Download PNG

Click "Copy meta tags" to copy ready-to-paste OG and Twitter card meta tags for your `<head>` section. Replace the placeholder image URL with where you upload the PNG.

## Output specs

- Dimensions: **1200 x 630 pixels** (the OG and Twitter Cards standard)
- Format: PNG
- Render: native HTML Canvas, no rasterization tricks

This is the size used by:
- Twitter / X (`summary_large_image` card)
- LinkedIn (`og:image`)
- Facebook (`og:image`)
- Slack (link unfurls)
- Discord (link previews)
- iMessage and Apple Messages

Same image works for all of them.

## Layouts

- **Centered**, title centered, accent bar at bottom. Best for hero announcements and product launches.
- **Left-aligned**, title flush left, classic blog-card style. Most versatile.
- **Top banner**, colored bar across the top. Best for category branding (e.g. "Engineering Blog").
- **Side bar**, vertical accent bar on the left. Best for quotes or testimonials.

## Color schemes

Eight presets, each with a coordinated background, foreground, accent, and badge color set. They are designed to look distinct from each other so a feed of cards from your site has variety without going off-brand.

To add or remove schemes: edit the `SCHEMES` array at the top of the script block in `index.html`. Each entry is `{id, name, bg, fg, accent, subFg, badgeBg, badgeFg}`.

## Tech

- Single HTML file
- ~700 lines including CSS and JS
- Vanilla JS, no frameworks, no dependencies, no build step
- Uses the standard HTML Canvas API
- Tested in current Chrome, Firefox, Safari
- Light and dark UI themes (the *generated images* have their own color schemes independent of UI theme)
- WCAG AA contrast on the UI in both themes

## What it doesn't do

- Doesn't load custom fonts. The font dropdown uses system stacks. Custom fonts would require web font loading logic and licensing considerations.
- Doesn't accept image uploads. Adding logos or illustrations would push this past the "30-second tool" goal. For richer card designs use a real design tool.
- Doesn't auto-generate from URLs. Type your text in.
- Doesn't host the resulting image. Download the PNG, upload it to wherever your assets live (S3, Cloudflare, GitHub Pages, anywhere).

## License

MIT. See [LICENSE](LICENSE).

## Related

- [single-file-saas-template](https://github.com/0xelitesystem/single-file-saas-template), ship a SaaS in one HTML file
- [readme-slop-checker](https://github.com/0xelitesystem/readme-slop-checker), audit a README for AI cliches
- [prompt-cost-calculator](https://github.com/0xelitesystem/prompt-cost-calculator), estimate token cost across providers
- [prompt-templates](https://github.com/0xelitesystem/prompt-templates), production prompts targeting LLM failure modes
