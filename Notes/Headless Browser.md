---
type: permanent
tags: [testing]
created: 2026-09-29
---

# Headless Browser

A browser running without the UI/window opening - it still runs the
CSS/JS engine internally, so it can take a screenshot or report page
state, it just doesn't display anything to a screen.

Forced by CI environments often having no display surface at all, while a
test still needs the real, fully-computed page - not a stripped-down fake
version.

Since the engine is identical in both headed and headless mode, a test
that only fails in one usually isn't a page-logic bug - it's an
environment default tied to having a real window: viewport size (check
first - layout/visibility issues are the most common E2E failure cause)
or GPU-accelerated rendering (rarer, mainly affects animations/canvas).

A specific instance of [[Headless Architecture]].
