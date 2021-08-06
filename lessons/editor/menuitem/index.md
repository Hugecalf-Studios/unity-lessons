---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Customising Unity’s Menu Bar using MenuItem
type: lesson
sections:
  - title: Mastering the basics
    id: mastering-basics
    sections:
      - title: Vanilla MenuItem
        content: vanilla.md
        id: vanila
      - title: How it works
        content: howitworks.md
        id: how-it-works
      - title: Nesting
        content: nesting.md
        id: nesting
      - title: Using const for the path
        content: consts.md
        id: consts
      - title: Ordering
        content: ordering.md
        id: ordering
      - title: Divide and conquer
        content: divideandconquer.md
        id: divide-and-conquer
      - title: Hijacking Unity's built in menus
        content: usingunitymenus.md
        id: hijacking-unitys-menus
  - title: More advanced usage
    content: advancedintro.md
    id: advanced
    sections:
      - title: Disabled items
        content: disabled.md
        id: disabled-items
      - title: Checkmarks/ticks
        content: checkmarks.md
        id: checkmarks
      - title: Keyboard shortcuts
        content: shortcuts.md
        id: keyboard-shortcuts
  - title: FAQs
    content: faqs.md
    id: faqs

---

{% include lesson.md root="editor/menuitem/" %}