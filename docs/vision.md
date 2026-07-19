# Vision & Multimodal Execution

This guide covers instructions for multimodal AI agents executing visual verification and UI/GUI interactions.

---

## 👁️ Visual Inspection & Verification

Multimodal models can inspect layout outputs, diagrams, screenshots, and visual designs to ensure quality.

### Rules for Vision Tasks:

1. **Take Screenshots**: When writing frontend UI code (React, HTML/CSS), run the dev server and take screenshots using rendering tools or browser devtools MCP (`take_screenshot`).
2. **Review Layout Alignment**:
   - Verify that elements do not overlap.
   - Ensure color palettes match the design systems.
   - Check text wrapping and padding consistency across desktop/mobile views.
3. **OCR Processing**: When analyzing scanned documents, logs, or command-line screenshots:
   - Identify text coordinates carefully.
   - Extract error logs from terminal frames.
   - Avoid guessing text that is blurry or low resolution.

---

## 🎨 UI/UX Design Verification

When creating or modifying mockups/designs:

- Verify that user flows (e.g. login -> dashboard) are intuitive and do not lead to dead ends.
- Use carousels and slideshows inside walkthroughs to present UI evolution (before vs. after).
- Avoid generic styling. Leverage cohesive theme configurations (e.g. glassmorphism, tailored CSS vars).
