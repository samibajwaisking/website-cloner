# Benchmark Methodology

How all quality measurements in `output-quality.md` were conducted.

---

## Model & Settings

- **Model:** claude-sonnet-4-20250514
- **Temperature:** 1.0 (default)
- **Max tokens:** 8096
- **System prompt:** Full SKILL.md content
- **Skill version tested:** v2.0.0

---

## Test Protocol

### Section Detection Tests

1. Select a real website from each category (SaaS, portfolio, e-commerce, agency)
2. Send to Claude: "Clone this website: [URL/screenshot]. Include all sections."
3. Open output HTML in browser
4. Manually check each section: present ✓ / missing ✗ / partially present ~
5. Run 10 trials per section type across different websites
6. Report % where section was fully present and visually correct

### Completeness Tests

1. Define complexity tiers:
   - Simple: homepage with hero + 1-2 sections
   - Medium: full landing page with 3-5 sections
   - Complex: multi-section page with 6+ distinct blocks
2. "Complete first try" = opens in browser, no console errors, all requested sections visible
3. Run 20 trials per complexity tier
4. Report pass rate

### Mobile Responsiveness Tests

1. Generate output HTML
2. Open in browser DevTools — test at 375px, 768px, 1280px
3. "Correct" = layout does not break, text readable, images scale properly
4. Run 15 trials per screen size

### Animation Tests (GSAP)

1. Generate output and open in browser
2. Scroll through page, hover over elements
3. "Working" = animation triggers as expected, no console errors
4. "Minor timing" = animation works but delay or easing feels off
5. "Not working" = animation does not trigger or causes layout shift

---

## Reproducibility

To reproduce any benchmark:

1. Load SKILL.md into Claude as system prompt
2. Use the test prompt: `Clone this website: [URL]. Build complete HTML with all sections, GSAP animations, Tailwind CSS, mobile-responsive.`
3. Open output in browser
4. Evaluate against the criteria above

---

## Limitations

- Results vary with different Claude model versions
- Website complexity is subjective — our tiers are approximations
- Color matching tolerance (10%) is visually estimated, not measured programmatically
- All test websites were publicly accessible at time of testing
- Results may differ for websites with heavy JavaScript-rendered content

---

## Questions

Open an issue if you believe a benchmark is inaccurate and provide your reproduction steps.
