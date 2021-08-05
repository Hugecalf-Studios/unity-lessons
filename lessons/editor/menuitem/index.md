---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Customising Unity’s Menu Bar
sections:
  - title: Mastering the basics
    sections:
      - title: Vanilla MenuItem
        content: vanila.md
      - title: Nesting
        content: nesting.md
      - title: 'Trivia: How it works'
        content: howitworks.md
      - title: Using const for the path
        content: consts.md
      - title: Ordering
        content: ordering.md
      - title: Divide and conquer
        content: divideandconquer.md
  - title: More advanced usage
    content: advancedintro.md
    sections:
      - title: Disabled items
        content: disabled.md
      - title: Checkmarks/ticks
        content: checkmarks.md
      - title: Keyboard shortcuts
        content: shortcuts.md
  - title: FAQs
    content: faqs.md

---

{% include lesson.md root="editor/menuitem/" %}