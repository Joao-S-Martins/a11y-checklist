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
- Use meta tags; `<title>` and `<meta name="description" content="160 chars or less" />` and `<meta content="text/html; charset=utf-8" http-equiv="Content-Type" />`
- Symantic tags; `<!DOCTYPE html>` `<nav>` `<header>` `<section>` `<article>` `<p>` `<aside>` `<figure>` `<footer>`
- Use heading hierarchies; `<h1>` - `<h6>`
- Emphasize content; `<em>` & `<strong>`, not `<b>` & `<i>`
- Blockquotes are for quotes, not visual indentation; `<blockquote>`
- More symantic tags; 
	- `<small>` is for legalese & fine print; `<small>Copyright 2017</small>`
	- `<cite>` is to cite an external source; `<cite>Clever Person</cite>`
	- `<meter>`measures data within a given range; `<meter value="9" min="0" max="10">9 out of 10</meter>`
	- `<abbr>` is for acronyms & abbreviations; `<abbr title="National Aeronautics and Space Administration">NASA</abbr>`
	- `<time>` 24-hour clock or Gregorian date; `<time datetime="2011-11-22T21:30-08:00">9:30PM, November 22, 2011</time>`
- Lists for menus, indicies, adn sequencial items; `<ul>` `<ol>`
- Hyperlink full markup; `<a href="" title="Screen readers will say 'link' before reading this title attribute, so avoid that word."><a/>`
- Image full markup; `<img src="" alt="Using the word 'image' should be avoided." />`
	- If image is for decoration only; `alt=""` or as a background
	- If image is inside a hyperlink; `alt` should match the hyperlink `title`
	- Default behavior is to describe the content of the image
	- Should be wrapped by `<figure>` and accompanying text, if such text exists
- Image header; use `<hgroup><h1><a>Title</a></h1><h2>Sub-title</h2></hgroup>` and use CSS for positioning and background image
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

