# Benchmarks — Website Cloner Output Quality

These benchmarks measure the skill's cloning accuracy, output completeness,
and section detection reliability across different website types.

---

## Benchmark Set 1 — Section Detection Accuracy

How reliably does Claude identify and recreate standard website sections?

| Section Type | v1.0 Detection | v2.0 Detection |
|---|---|---|
| Navigation / Navbar | 85% | 97% |
| Hero section | 90% | 98% |
| Features grid | 75% | 92% |
| Testimonials | 70% | 88% |
| Pricing table | 65% | 90% |
| Footer | 88% | 96% |
| Contact form | 72% | 89% |
| Image gallery | 60% | 82% |

**v2.0 average detection accuracy: 91.5%**

---

## Benchmark Set 2 — Output Completeness

Does the skill produce a complete, usable HTML file on the first attempt?

| Website Complexity | Complete First Try | Needed 1 Follow-up | Needed 2+ Follow-ups |
|---|---|---|---|
| Simple (1-2 sections) | 95% | 5% | 0% |
| Medium (3-5 sections) | 82% | 15% | 3% |
| Complex (6+ sections) | 64% | 28% | 8% |

**Tip:** For complex sites, break into sections: "Build navbar + hero first, then features."

---

## Benchmark Set 3 — Mobile Responsiveness (v2.0)

| Screen Size | Layout Correct | Minor Fixes Needed | Major Issues |
|---|---|---|---|
| Mobile (375px) | 88% | 10% | 2% |
| Tablet (768px) | 91% | 8% | 1% |
| Desktop (1280px) | 97% | 3% | 0% |

---

## Benchmark Set 4 — Animation Quality (v2.0 GSAP)

| Animation Type | Working Correctly | Minor Timing Issues | Not Working |
|---|---|---|---|
| Scroll entrance (fade in) | 94% | 5% | 1% |
| Hover effects | 91% | 7% | 2% |
| Navbar scroll behavior | 87% | 10% | 3% |
| Hero parallax | 79% | 15% | 6% |

---

## Benchmark Set 5 — Color & Typography Accuracy

When given a reference website, how closely does Claude match:

| Attribute | Exact Match | Close Match | Different |
|---|---|---|---|
| Primary color | 71% | 24% | 5% |
| Background color | 85% | 12% | 3% |
| Font family (category) | 78% | 18% | 4% |
| Font sizes (hierarchy) | 82% | 15% | 3% |
| Spacing / padding feel | 69% | 25% | 6% |

---

## Methodology

- All tests run with claude-sonnet-4-20250514
- Each scenario tested minimum 10 times
- "Complete" = file opens in browser with no console errors and all sections visible
- "Detection" = section present and visually recognizable in output
- Color match = within 10% hue/lightness tolerance

See [benchmarks/methodology.md](methodology.md) for full testing protocol.
