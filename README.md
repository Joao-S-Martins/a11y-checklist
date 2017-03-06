# a11y-checklist
An interactive guide to making your UI work accessible to all.

---
## Categories of disability
### Visual
Accessbility through screen readers, baile devices, screen magnification, clear content flow & grouping, keyboard interaction, & dictation software.
- Blindness
- Low/blurred vision
- Partial/limited field of vision
- Color deficiency
### Auditory
Accessiblity through transcripts, closed captioned audio & video, & visual indicators/alerts
- Deafness
- Hard of hearing
### Motor / Dexterity
Accessibility through efficient keyboard interaction & dictation software
- Limited or no use of fingers, hands, or arms
- Limited fine motor skills
### Cognitive / Learning
Accessibility through very simple & clear content flow & grouping, & great general usability
- Reading disorders
- Attention deficit disorders
- Intellectual disabilities
- Memory impairments
- Mental health disabilities
- Seizure disorders (photosensitive epilepsy)
### Device impaired
Has affected all of us at times
- Small screen devices
- Out of date screens or software
- Low network bandwidth

---
## Disability demographics
- 16-18% of world population lives with disability
- 10%, more than 600 million, live with life-altering disability, two-thrids of which are in developing countries
- 54 million persons with disabilities live in the United States
- Disability is a key driver of poverty; 70% of blind persons in the United States are unemployed
- A disablility is not always a well defined label
- People may have multiple disablilities

### Aging & Disabilities
- 18-24; 9.5%
- 25-34; 10%
- 35-44; 14.4%
- 45-54; 21.2%
- 55-64; 34%
- 65-74; 42.3%
- 75+; 64%

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
- Standard controls have this taken care of, but for custom controls, ARIA states provide solutions (aria-checked, aria-pressed, etc)

---
## A11y tools
### Readers
- JAWS
- NVDA
- VoiceOver

---
## Developer Tools
- Fang's screen reader emulator
- WAI-ARIA best practices
- color contrast checker
- Tanaguru's automated accessibility testing service
- [html5accessibility.com](http://www.html5accessibility.com/)
- Web developer toolbar for FF
- Firebug for FF
- Developer tools for Chrome

---
## Info Resources
- [Simply Accessible Articles](http://simplyaccessible.com/articles/)
- [WCAG Samurai](http://www.wcagsamurai.org/)

---
## Design Considerations
### Vision Issues
#### Screen reader user functional needs
- Programatic a11y; use HTML as it was intended
- Keyboard everywhere
- Text-based representations of visual elements
#### Magnified viewer needs
- Well placed calls to action
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

---
## A11y & SEO
### SEO tools
- SenSEO for ff
### Tips
- Define content language; `<html dir="LTR" lang="en-US" >` [lang ref](w3schools.com/tags/ref_language_codes.asp)
- Use meta tags; `<title>` & `<meta name="description" content="160 chars or less" />` & `<meta content="text/html; charset=utf-8" http-equiv="Content-Type" />`
- Symantic tags; `<!DOCTYPE html>` `<nav>` `<header>` `<section>` `<article>` `<p>` `<aside>` `<figure>` `<footer>`
- Use heading hierarchies; `<h1>` - `<h6>`
- Emphasize content; `<em>` & `<strong>`, not `<b>` & `<i>`
- Blockquotes are for quotes, not visual indentation; `<blockquote>`
- More symantic tags; [tag ref](https://www.w3schools.com/html/html5_semantic_elements.asp)
	- `<small>` is for legalese & fine print; `<small>Copyright 2017</small>`
	- `<cite>` is to cite an external source; `<cite>Clever Person</cite>`
	- `<meter>`measures data within a given range; `<meter value="9" min="0" max="10">9 out of 10</meter>`
	- `<abbr>` is for acronyms & abbreviations; `<abbr title="National Aeronautics & Space Administration">NASA</abbr>`
	- `<time>` 24-hour clock or Gregorian date; `<time datetime="2011-11-22T21:30-08:00">9:30PM, November 22, 2011</time>`
- Lists for menus, indicies, adn sequencial items; `<ul>` `<ol>`
- Hyperlink full markup; `<a href="" title="Screen readers will say 'link' before reading this title attribute, so avoid that word."><a/>`
- Image full markup; `<img src="" alt="Using the word 'image' should be avoided." />`
	- If image is for decoration only; `alt=""` or as a background
	- If image is inside a hyperlink; `alt` should match the hyperlink `title`
	- Default behavior is to describe the content of the image
	- Should be wrapped by `<figure>` & accompanying text, if such text exists
- Image header; use `<hgroup><h1><a>Title</a></h1><h2>Sub-title</h2></hgroup>` & use CSS for positioning & background image
- All menus should be unordered lists;
```
<nav>
	<h1></h1>
	<ul>
		<li><a href="#" title=""></a><li>
		<li><a href="#" title=""></a><li>
		<li><a href="#" title=""></a><li>
	</ul>
</nav>
```
- Skip navigation to quickly move focus;  use anchor with `href="#ID"` where "ID" is the id of an element on the page
- The focus psuedo-class should provide adequate visual cues;
```
a:focus {
	outline: blue solid 2px;
}
```
- Dropdown nav; Superfish Menu
- Multiple landing pages are much more valuable than dropdown menus
- Google Search Engine Optimization Starter Guide

## More Tips from Andy Clarke
- `<fieldset><legend>` reads with each form field, so be careful not to be annoying
- Avoid creating your own tabindex & key shortcuts, which may conflict with a11y software
- `em` for width, but not a hard & fast rule
- 6pt - nonpareil, 12pt - pica, 18pt, 24pt - dbl pica, 36pt - dbl great primer, 48pt, 72pt
```
body {font-size: 12px;}
h4 {font-size: 118%;}
h3 {font-size: 145%;}
h2 {font-size: 164%;}
h1 {font-size: 218%;}

body {font-size: 100%;}
h4 {font-size: .75em;}
h3 {font-size: .875em;}
h2 {font-size: 1.125em;}
h1 {font-size: 2.25em;}
```
- Line spacing (leading) is at least space-and-a-half within paragraphs within paragraphs, & paragraph spacing is at least 1.5 times larger than the line spacing (WCAG2.0 1.4.8)
- Too much & too little leading makes each line of the text difficult to find or read.
- Space below line == height of lowercase `t`
- Sans-serif or darker lettering requires more leading
- Letter-spacing (tracking)
- Measure (characters or glyphs per line) of 52-78; max Measure of 80 (WCAG2.0)
- `:visited` `:hover` `:active` `:focus`
## Images
- Almost always provide text descriptions for images
- WCAG 2.0; decoration, formatting, & unseen images don't need `alt` text
- Max recommended `alt` text; 150 chars
- `longdesc` can point at a large amount of text
## Video & Audio
- Captions aren't always do-able for all projects, but are encouraged
- Transcripts are a minimum requirement which serve a dual purpose by helping with SEO
- `a:target` can be used to adjust visibility/opacity of transcript text when the transcript link has focus
## Tables
- `<th>` w/ attribute `scope` w/ values `row` or `col`
- When headings are nested, give each header an `id` & in the `<td>` use the `headers` with a space-seperated list of relevant `<th>` IDs
- `<caption>` within `<table>` acts as title to screenreaders
- The `summary` attribute can be set on the `<table>` element, but isn't visible
- A visible & accessible summary can be employed by simply placing it in a `<p>` immediately befor the table
## Forms
- You can use tables to create layout & describe labels as headers to inputs, but it isn't recommended & you should still place the label text in a `<label>` element & associate it correctly to the input
- For search inputs, if the button `value="search`, then the field doesn't need a label, but does need `title="search"`
- Use the `title` attribute on inputs on those rare cases where a label isn't needed by a sighted user
- Put radios buttons & groups of checkboxes in `<ul><li>` so that the item cound is announced
- Always place radio buttons & checkboxes before their label text
- Combine groups of `<option>` in to `<optgroup>` tags
- Use `<fieldset>` for closely related `<inputs>`
- Use a `<legend>` withing a `<fieldset>` sparingly because it will be read before each label is read; when a `<legend>` isn't appropriate, use an appropriate heading tag
- Use `<em title="Required">*</em>`, or similar, within your `<label>` to note required fields in a visual and screen-readable way; CSS can then be used to position the `*` on the other side of the input
- Form errors should appear within the label of the faulty input; use `<strong>` to emphasize your error message

---
## Keyboard Accessibility
### Standards
#### WCAG 2.0 2.1.1 Keyboard (Level A)
All functionality is operable through a keybaord without requiring specific timings for individual keystrokes or when the path of the user's movement is required, not just endpoints.
#### WCAG 2.0 2.1.2 No Keyboard Trap (Level A)
All components that can take keyboard focus & also release keyboard focus
#### WCAG 2.0 2.4.3 Focus Order (Level A)
Items take focus in a logical order which retains context.
#### WCAG 2.0 3.2.2 On Input (Level A)
Don't change the UI when a user enters a component without advising the user ahead of time.
#### Section 508 1194.21 a
Software designed to run on a system with a keyboard should have every textuall discernable action executable by a keyboard.
### Common Problems
- Interactivity designed for mice, not for keyboards
- Read & tab order on screens is wrong
- There's no clear indication of where keyboard focus is
- No way to jump over repeated elements to get to screen content
- Keyboard shortcuts or custom keyboard behavior with a steep learning curve
- No structure or semantic tags
- Skip links instead of proper shortcut keys & structural 
- Elements recieving focus immediately cause changes to the UI
### Testing
- Remove your mouse (no cheating)
- Check that the tab order & read order are logical
- Check that keyboard behavior closely matches _typical_ behavior; is it intuitive?
- Check that keyboard shortcuts are discoverable
#### Standard Keyboard Behavior
- `ALT` places the focus on the application menu
- `SHIFT+F10` opens a context menu
- `TAB` moves between landmarks & controlls
- `ENTER` interacts with buttons
- `CTRL+TAB` or `CTRL+F6` to move from menus to toolbars to panels
- `ARROWS` switch between navigation tabs
##### Forms
- `TAB` moves between form controls within a fieldset
- `ARROWS` change radio, combobox, sliders, & similar selectable values when in focus
- `ALT` to show all combobox options
- `SPACE` selects & deselects selectable controls
- `ENTER` to interact with a button
- _Read only_ items should not be part of the tab order
##### Modals
- Focus on first item after `close` button
- Has its own cycling tab order
- Return focus to modal launcher when modal is closed
- `save` and `cancel` also close the modal
##### Tree Control
- `UP ARROW` & `DOWN ARROW` navigate up and down the open nodes
- `LEFT ARROW` & `RIGHT ARROW` close & open branches
- `ENTER` opens the selected folder or item without expanding the menu
- `-` & `+` collapse & expand all branches
- `HOME` & `END` jumps to the top & bottom of the tree
- `PAGE UP` & `PAGE DOWN` jumps between branches
- `SHIFT` & `CTRL+SHIFT` can be used to select contiguous & non-contiguous items
##### Shortcuts
- `ALT+F` to open file menu
- Have a categorized list easily & clearly available in the help files
- Make them customizable if posible
- Test for conflicts with assistive technology
##### Equivalent Alternative
- As a last resort only because it is difficult to maintain
- Make sure to maintain it & port the features
##### Tab Order
- WCAG 2.0 2.4.3 is about focus order
- Not every element needs to be tabbable, sometimes a top-level element is enoug; nav tress & drop-downs should be tabbable at the top level, then arrowable for child elements
- Cycle tab order through modals
- Make sure controls aren't skipped unless they are part of a group and arrowable
- Make sure you can't tab to invisible things
- Make sure the flow is logical
##### Behaviors
- Arrows & creativity or shortcuts are needed to replace drag-and-drop & drawing behaviors
##### Other Keyboard Issues
- Provide a way to skip repedative content, such as intro text of a repeating nav bar, with skip links or better content arrangement
- Skip links should be visible & be the first thing on the page
- Skip links are a mostly deprecated due to features in modern screen readers
- Test to make sure skip links actually work as intended
- Proper structural elements (headers & such) technically satisfy a11y requirements for screenreaders, but low-vision users might like to zoom on the skip links with each new page
- WCAG 2.0 3.2.2 No major UI changes onFocus (:focus) of an element; this can be disorienting
- Change UI only as a response to an input, such as the `SPACE` & `ENTER` keys
##### Prefered Keyboard Behaviors
- `TAB` through top-level menu items, `ARROWS` navigate the sub-menu items, & `SPACEBAR` activates the item (prefered behavior, not mandatory)
##### Events & Widgets
Stick closely to desktop keyboard conventions
- `onkeypress`, `onkeydown`, `onkeyup`
- Check `event.keyCode=32||event.keyCode=13` or other key codes
##### WAI-ARIA
Applying [WAI-ARIA](http://www.w3.org/WAI/PF/aria-practices).
- Works on any HTML element
- Specify a `role`
- Specify state & property attributes; these begin with `aria-`, such as `aria-label`
- Set `tabindes`; `0` places it in the default order without breaking, & `-1` allows it to be focusable, but doesn't include it in the normal order, which is useful for items that will receive focus as a special keybaord interaction
- `Element.focus()`
- Widgets should be focusable by tab and actions within the widget should be operated by other keys
- Don't use `tabindex` to micromanage the order, because it'll eventually break & is a sign of other problems that should be addressed
##### Drag and Drop
Possible solutions
- Add select or checkbox
- Use shortcut key
- Keyboard enable drag-select, then drop-select
- Copy-paste may occasionally be acceptable
- `aria-grabbed` & `aria-dropeffect`
- Allow user to cancel operation with `ESC`
##### Getting Around
Skip links are dead!
- Use symantic roles to regions, which may overlap with HTML5, like `<nav role="navigation>` to help a screenreader offer a jump between regions
- `role="application` belongs on the `<body>` & is **not recommended**, because is disables much of a screenreader's functionality, requiring your code to take a lot more of the responsibility & workload
- `role="document"`  returns some functionality lost by the application role for reading & editing text
- `banner`, `complementary`, `contentinfo`, `main`, `navigation`, `search`, `menubar`, `toolbar`, & `form` are landmark roles
- Shortcuts can be used to jump between regions, but should typically be avoided
- Shortcut standards vary across operating systems, so tread carfully
- `accesskey` is an HTML attribute that allows a single keystroke to be used to apply focus to some elements or fire a link
	+ Can clash with AT (assistive technology) shorcuts
	+ Not easily discoverable
	+ Rarely are there standard keys to assign for these behaviors

---
## Basic HTML Accessibility
### Images
- `alt` text for short descriptions in `<img>` & image map `<area>`
- Don't render text as images unnecessarily; use just text instead
- `<figure><img /><figcaption></figcaption></figure>` for longer image descriptions
- `aria-describedby` when an adequate description already exists elsewhere on the page
- Consider data tables instead of data-conveying images
### Form Controls
- Pair the `<label>` `for` attribute to the `<input>` `id` attribute
- Use `<input>` `title` when a label isn't present, as is common with search features
- Use `aria-labelledby` when a labeling exists outside of the HTML `<label>` tag
- Use roles such as `radiogroup` on elements that wrap input groups & related roles on the inputs when necessary
### Audio & Video
- Text transcripts, always
- Visual notifications to accompany audio notifications
- Captions to video when possible
	+ Synchronize using TTML (formerly DFXP) or WebVTT
	+ Provide cued audio descriptions of videos which don't audibly describe their visual content
- Ensure accessible playback controls exist for AV content
- Audio CAPTCHA to accompany visual CAPTCHA
### Reading Order
- New content appears at the end or takes focus (modal), never at the beginning without taking focus
- Reading order is determined by the HTML DOM order
- Tab order follows DOM order except where `tabindex` changes it
- CSS can change visual order without affecting AT read order
- When modals appear, all other page region elements need to set `aria-hidden="true"`, which can be inherited by child elements
- Modals should be receive focus when shown and return focus to a sensible element when closed
- Layout tables often read by row, which isn't always intended
### Structural Semantics
- `<h1>` through `<h6>`
- `ol` & `ul` with `li` children for any lists
- `em` & `strong` for emphasis & strong emphasis, not visual embellishment
- HTML 5
	+ `<nav>`
	+ `<article>`
### Tables
- Use `<table>` & maybe sometimes `<thead>` & `<tfoot>`
- Use `<th>` with the `scope` attribute
- Specify `headers` in `<td>` elements when multidimensional headers apply
### Keyboard
- Actionable elements should all be navigable
- Do not block the browser's visual focus mechanism without replacing it
- Provide a custom focus indicator for widgets
- Logical focus order with no trapping
- Avoid specifying a `tabindex` > 0
	+ -1 makes it focusable by JS, but not as part of the default order
	+ 0 places it in the default focus order
	+ > 0 assigns it a specific place in the order
### Misc.
- Use `<title>` in pages & specify `title` attributes within `<iframe>`
- Specify `lang` in the `<html>` tag
- ARIA fills gaps
- Text needs to be meaningful; don't use "click here", "read more", etc
- Colors alone cannot convey information; shapes & text should also be used
- Audio that plays for more than 3 secs must can be stopped, paused, or muted
- Dynamic content can be stopped, paused, replayed, & forwarded
- Sufficient contrast in the text
	+ Luminosity of 4.5:1 or greater between foreground & background
	+ Luminosity of 3:1 for large, bold text
- Text must be resize-able up to double its original size; be careful when fixing sizes
- Flashing content must be a a rate slower than 3 times per second or occur ins a very small part of the screen
- Don't make undue changes `onFocus`
- Make content parsable; no duplicate IDs or broken nesting
#### Resources
- [HTML Techniques](https://www.w3.org/WAI/GL/WCAG20-TECHS/html.html)
- [ARIA Techniques](https://www.w3.org/WAI/GL/WCAG20-TECHS/aria.html)
- [WCAG 2.0](https://www.w3.org/TR/WCAG/)
- [Understanding WCAG 2](https://www.w3.org/TR/UNDERSTANDING-WCAG20/)
- [ARIA 1.0](https://www.w3.org/TR/wai-aria/)
- [HTML 5.2](http://w3c.github.io/html/)
- [HTML Accessibility Overview](http://html5accessibility.com)
- [Adobe Accessibility](http://www.adobe.com/accessibility)

___
## Mobile
### Standards
- CVAA (US)
- 508 (US)
- Mandate M376 (EU)
- ADA (US)
- WCAG 2.0
### Overview
- iOS leads the game
### iOS
Added stuff starting in 2009
#### iOS ATs
- VoiceOver
- Zoom
- Assistive Touch
- Switch Control
- Guided Access
#### iOS A11y Features
- Large text
- Invert colors
- Increase contrast
- Bold text
- Speak selection/speak auto-text
- On/off labels
- Reduce motion
- Mono audio
- Custom vibration
- LED flashing for alerts
- TTY
- Siri
- Facetime
- Captions
#### iOS Platform A11y Interfaces
- Mobile Accessibility API
	+ UIAccessibility
	+ `isAccessibilityElement`
- Accessibility traits
	+ `UIAccessibilityTraitNone`
	+ `UIAccessibilityTraitButton`
	+ `UIAccessibilityTraitSearchField`
	+ `UIAccessibilityTraitSelected`
	+ `UIAccessibilityTraitNotEnabled`
	+ `UIAccessibilityTraitAdjustable`
	+ `UIAccessibilityTraitPlaysSound`
- Accessibility Notifications
	+ `UiAccessibilityAnnouncementNotification`
	+ `UIAccessibilityLayoutChangedNotification`
### Android
#### Android ATs
- TalkBack (4.1.1+)
- Magnification (4.2+)
- Spiel; third party screenreader
#### Android A11y Features
- Large Text
- Captions in Media Player (4.0+)
- Google Now
- Google Voice
- Google Video Chat
- Custom Keyboards; system-wide
#### Samsung A11y Features
- Custom vibration
- Inverse colors
- Mono audio
#### Android Platform A11y Interfaces
- AccessibilityService
	+  Receives `AccessibilityEvent`
	+ Manages tree of `AccessibilityNodeInfo`
- Accessibility CLass
	+ `AccessibilityNodeInfo`
	+ `AccessibilityEvent`
- Keyboard focus
	+ `setFocusable()`
	+ `requestFocus()`
	+ `nextFocusUp`, `nextFocusDown`, `nextFocusLeft`, & `nextFocusRight`
- Widgets
	+ `contentDescription`
	+ `editText`
	+ `setLabelFor` & `setLabeledBy`
	+ `performAction`
	+ `isChecked` & `isCheckable`
### Testing
#### VoiceOver
- Enable
- Use the Rotor
- One-finger gestures
- Two-finger gestures
- Three-finger gestures
- Inspect...
	+ Labels
	+ Bounding rectangles
	+ Input values
	+ Traits
	+ Hints
#### Accessibility Inspector
Runs in Xcode on a simulator
#### TalkBack (4.2+)
- Enable
- One-finger gestures
- Two-finger gestures
- Inspect...
	+ Widget labels
	+ Widget roles
	+ Widget values
#### Lint in Eclipse
Use to check for missing accessibility properties on Android code
#### Adobe Edge Inspect
Chrome plug-in that allows cross-platform screenshots & testing
#### Contrast Analyzer
Many tools exist to analyze screenshots from mobile devices
#### Types of Testing
- User testing
	+ Technical testing
		* Automatic testing
		* Manual testing
		* Global testing
	+ Functional
		* End users with disabilities
### Resources
- [iOS Accessibility](https://developer.apple.com/accessibility/ios/)
- [Android Accessibility](https://developer.android.com/guide/topics/ui/accessibility/index.html)
- [Level Access Learning](https://webaccessibility.com/#Learn)
- [Lint](https://developer.android.com/studio/intro/index.html)
