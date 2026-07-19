# Project Blueprint: Vision-Guided Browser Agent

This document details the layout and architecture of a computer use agent navigating web pages using screenshot processing and element coordinates.

---

## 🏗️ System Architecture

```mermaid
graph TD
    Goal[User Task: Buy a ticket] --> AgentCore[Agent Core Node]
    AgentCore --> TakeScreenshot[1. Take Page Screenshot]
    TakeScreenshot --> ElementMap[2. Map interactive DOM elements]
    ElementMap --> OverlayGrid[3. Draw visual coordinate grid on image]
    OverlayGrid --> MultimodalLLM[4. Feed Gridded Image to Vision LLM]
    MultimodalLLM --> ChooseAction[5. Select Action: Click, Type, Scroll]
    ChooseAction --> ClickNode[6. Execute Click on coordinates (X, Y)]
    ClickNode --> TakeScreenshot
```

---

## 🗂️ Project Directory Layout

```
browser-agent/
├── src/
│   ├── browser/
│   │   ├── driver.py        # Playwright controller (navigate, screenshot)
│   │   └── dom.py           # Extract clickable elements and input selectors
│   ├── vision/
│   │   └── grid.py          # Draws visual overlays and numbers on image frames
│   ├── core/
│   │   └── loop.py          # Action parsing loop (click, scroll, keystroke)
│   └── main.py
├── requirements.txt
└── README.md
```

---

## 💡 Best Practices & Safety

1. **Relative Coordinates**: Scale screen coordinates (0-1000) to actual browser viewport widths dynamically to prevent misclicks on different display sizes.
2. **Action Delay**: Introduce randomized human-like delays (500ms - 1500ms) between clicks to prevent server-side blockages.
3. **Transaction Safety**: Implement blocklists for domains. Never let the agent execute actions on checkouts or payment fields unless running in sandbox test modes.
4. **Retry Loop Limits**: Cap page action retries at 5. If the page does not change state, stop and report the blockade to the user.
