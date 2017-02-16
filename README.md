# a11y-checklist
An interactive guide to making your UI work accessible to all.

---
## Outline
### Visibility
- Use the visibility of display properties, or the hidden attribute
- Don't override too many of the browser's default behaviors
### Color
- There should be a certain amount of contrast in your color choices
### Focusability
- Everything on the page should be able to have focus
- If a control on the page isn't standard, they should have an appropriate ARIA role attached to them
### State Changes
- Statndard controls have this taken car of, but for custom controls, ARIA states provide solutions (aria-checked, aria-pressed, etc)
---
## A11y tools
- JAWS

---
## Developer Tools
- Fang's screen reader emulator
- WAI-ARIA best practices
- color contrast checker
- Tanaguru's automated accessibility testing service
- [html5accessibility.com](http://www.html5accessibility.com/)

---
## Info Resources
- [Simply Accessible Articles](http://simplyaccessible.com/articles/)

---
## Design Considerations
### Vision Issues
#### Screen reader user functional needs
- Programatic a11y; use HTML as it was intended
- Keyboard everywhere
- Text-based representations of visual elements
#### Magnified viewer needs
- Well placed alls to action
- Flexibility to stack elements... like mobile experiences
### Hearing issues
- Transcripts are king
- Captions are helpful
### Mobility & dexterity issues
- Design for Dragon or other voice control
- Visual & textual call to action need to match so Dragon can understand user commands
- See it & say it; make sure calls to action are always visible
### Cognitive issues
- Memory, problem solving, attention to focus, literacy & reading, visual comprehension, verbal comprehension
- Design for forgetfulness
- Write with plain language
- Provide predictability in your interface
- Issues may be temporary & related to the user's atmosphere, not necessarily a medical condition
