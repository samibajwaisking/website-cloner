# Frequently Asked Questions

---

## General

### Q1: What exactly does "cloning a website" mean in this context?

It means Claude analyzes a website's visual design, layout, and structure — and
recreates it as a clean, self-contained HTML/CSS/JS file. It does not copy the
original source code. Claude builds a new implementation from scratch that looks
similar, using modern techniques like Tailwind, GSAP, and vanilla JS.

---

### Q2: Is this legal? Can I clone any website?

You can clone websites for:
- **Personal learning** — studying how layouts are built
- **Your own websites** — rebuilding your own site in a different stack
- **Inspiration** — creating something similar in design but original in content

You must NOT use this skill to:
- Impersonate brands or create phishing pages
- Copy copyrighted content and publish it as your own
- Reproduce another person's commercial product without permission

When in doubt, only clone what you own or have permission to use.

---

### Q3: Do I need coding knowledge to use this skill?

No. Load the skill into Claude and describe or share the website you want to clone.
Claude handles the code. Basic knowledge of how to open an HTML file in a browser
is all you need to see results.

---

### Q4: What is required before using this skill?

Per the Custom Attribution License:
1. ⭐ **Star this repository**
2. 👤 **Follow @samibajwaisking** on GitHub
3. 🔗 **Add visible credit** in any project built with this skill
4. 🔗 **Link back** to this repo in your project

See [LICENSE](LICENSE) for full details.

---

## Technical

### Q5: How do I load the skill into Claude?

**Claude.ai Projects (recommended):**
1. Go to [claude.ai](https://claude.ai) → Projects → Create or open a project
2. Upload `SKILL.md` as a project instruction file
3. Claude now uses the skill automatically

**API:**
```python
with open("SKILL.md", "r") as f:
    system_prompt = f.read()

response = client.messages.create(
    model="claude-sonnet-4-20250514",
    max_tokens=8096,
    system=system_prompt,
    messages=[{"role": "user", "content": "Clone this website: [URL or description]"}]
)
```

---

### Q6: Should I give Claude a URL or a screenshot?

Both work. Best results come from:
- **URL + description:** "Clone this website: [URL]. Recreate the homepage with the same layout and color scheme."
- **Screenshot:** Upload an image of the page and say "Recreate this as a clean HTML file."
- **Description:** "Build a dark SaaS landing page with hero section, features grid, and pricing table — similar to Stripe's design."

---

### Q7: The output HTML is missing some sections. What should I do?

Try these fixes:
1. Be more specific: list every section you want — "hero, navbar, features, testimonials, pricing, footer"
2. Ask Claude to complete missing parts: "Add the pricing section that was missing"
3. Increase max_tokens in your API call — complex pages need more output tokens
4. Break it into parts: "Build only the hero and navbar first"

---

### Q8: Can I use the output for commercial projects?

Yes, with attribution. The cloned HTML output belongs to you. You must:
- Add the required credit block (see README)
- Link back to this repository
- Not resell the skill itself

---

### Q9: Does this work with React or other frameworks?

The default output is vanilla HTML/CSS/JS with optional Tailwind and GSAP.
You can ask Claude to output React components instead:
```
Clone this website as React components with Tailwind CSS. Use functional components.
```

---

### Q10: How is v2.0 different from v1.0?

v2.0 added GSAP animations and Tailwind CSS support, resulting in significantly
more polished output with smooth transitions and responsive design out of the box.
See [CHANGELOG.md](CHANGELOG.md) for full version history.

---

*More questions? Open a [GitHub Discussion](https://github.com/samibajwaisking/website-cloner/discussions)
or join the [WhatsApp Channel](https://whatsapp.com/channel/0029VbCNzQeISTkQR04DvX3r).*
