# CSUN Notes
------------
## Sessions
### Static vs Interactive Widget Roles
- Static ARIA, Pseudo Interactive, Iteractive Widget
- http://whatsock.com/training/matrices/
#### Static Roles
- Require no scripting
- Landmark & region
- Structural
- Specialty
#### Psuedo Interactive
- Require some scripting
- Dialog
- Live Region
#### Interactive Widget
- Much scripting
- SImple Interactive Widget
- Complex Interactive Widget
#### Interactive examples
##### Static Roles
- Region w/ `aria-label`
- Heading w/ `aria-level`
- Toolbar w/ `aria-label`
##### Pseudo Interactive
- Modal; circular tab indexing, starting with modal title
- Live region w/ `aria-live`
##### Interative Widget
- Link
- Button
- Checkbox; unchecked, checked
- Combobox; focusable, collabpsed, expanded, aria-activedescendant
### Tools & Resources
- http://github.com/accdc/tsg
- http://github.com/accdc/tsg-mootools
- http://github.com/accdc/tsg-dojo
- http://github.com/accdc/training
- http://whatsock.com/training
- http://whatsock.com/training/matrices
- http://whatsock.com/training/matrices/visual-aria.htm
#### Speakers
- Bryan Garaventa, bryan.garaventa@ssbbartgroup.com
- Terri Fellers, terri.fellers@ssbbartgroup.com

## The Accessibility Playground
[http://playground.accessibility.tools](http://playground.accessibility.tools). A set of educational, interactive, test cases to learn a11y practices.
- Based on JS Bin
- Additionally, snippets of code can be op
- Open source to Github soon
- i8 toolkit?
#### Speakers
- Greg Kraus, ia11y.com, @ia11y

## Bring Accessibility into the Development Lifecycle with CI
- Pre-checkin process is a good test point for linting
- post-checkin, unit & smoke tests for BDD testing
- Level Access's Access Engine
- Component & functional tests
- Linting helps

## Motivating Developers
- Time & fears/costs put a11y work on to the backburner
- Phases of a11y implementation:
	+ Technical
	+ Keyboard
	+ Screenreader
- Developer motivators:
	+ Understanding challenges
	+ Createing value
	+ Building empathy
	+ Generating excitement
	+ Setting goals
- Fix the broken windows; many small wins make the big win
#### Speakers
- JoAnna Hunt
- Heidi Jungel
- accessibility@blackboard.com

## 7 Minute Accessibility Assesment
[http://goo.gl/6NvnVD](http://goo.gl/6NvnVD)
- Android accessibility scanner
- Use screenreader & check for state, role...
- Complete tasks & trigger errors
- Analyze color contrast
- Assign severity; block, annoyance, trivial, technical non-conformance

#### Speakers
- Aidan Tierney @AidanA11y

## How to Improve Your Testing (for Beginners)
- Start screen reader before opening the browser
- Using JAWS w/ keyboard only
	+ Make sure the audible ezperience matches the visual experience
	+ Start with the arrow keys, not tab key
	+ Use shortcurts and make sure links, headings, title, labels etc. match
- Remove colors to see if any information is lost
- Remove images to see if any information is lost
- Check the links for a consistent implementation of link text styling & text that have similar styling that doesn't link
- Change browser color settings (inverse them) & see if any information is lost
- Enlarge text to 200% using the browser controls & enable responsive design view to check for wrapping, lost alignment, pixilation, & repositioning
- Return the screen to normal & activate a [color contrast checker](http://www.ssbbartgroup.com/reference/)
- Check that tooltip-ish dialogs either don't obscure the content behind them or can be removed by keystroke
- Remove CSS & make sure the content is still clearly represented; rarely done by the disabled, but is very telling of how other tools & search engines will view your page
- Use [Visual ARIA Bookmarklet](http://whatsock.com/training/matrices/visual-aria.htm) if you have any ARIA attributes on your page to make sure it has been implemented correctly
- Run automated web accessibility tests; Level Access [has tools](http://www.webaccessibility.com) & new toolbars are coming soon & will be announced
- Verify automatics in AMP, verify guided automatics, add manual violations
#### Speakers
- Level Access
- [Slides][(http://www.ssbbartgroup.com/blog/)
----------------------------------------------
## Accessibility, Visual Design, & Front-End Development
Color contrast & keyboard access remain to be tough problems for designers to work through.
- Updating a heading may be acceptible as an accessible indicator for which tab/item is selected
- Challenges
	+ Contrast
		* Designer is mostly responsible
	+ Keyboard
		* Tab order
		* Focus management for in-page updates
		* Visual focus indeication
		* Keystrokes to select or activate
- `TAB` & `SHIFT+TAB`
- `ARROW` keys & `SPACE` to select
- `ENTER` || `SPACE` to activate
- Tooltip onFocus is kinda nice; treating onFocus the same as onHover is usually a good idea
- (See image example of who is responsible for what)
- Mobile-first design often solves your tab order
- Don't supress the browser focus indicators with a CSS reset; replace it
- Use natve elements or put in the extra JS work for full support of custom components
#### Speakers
- Level Access

## Advanced ARIA
- ARIA describes roles, states, & properties
- Buttons take `ENTER` & `SPACE`
- Links take `ENTER`
- Best practices
	+ Opt for native elements before using ARIA
	+ Checkbox, buttons, lists
- Use the [Custom Control Accessible Development Checklist]() when creating custom widgets
- Live Regions
	+ Real-time updates
	+ status updates
	+ chat logs
	+ progress indicators
	+ Must be used sparingly because multiple instances can become very confusing
	+ [Live Region Playground](http://schne324.github.io/live-region-playground)
	+ `aria-role`, `aria-live`, `aria-atomic`, `aria-relevant`
	+ [Dragon Drop](http://www.harris-schneiderman.com/demos/dragon-drop/index.html) makes use of a live region to announce changes status & command options
- Toggle buttons
	+ Keyboard operable & toggle without changing label text
	+ role=button
	+ aria-pressed=true||false, changed on `ENTER` or `SPACE`
- Modal dialog
	+ Shift focus to the modal & return it on close
	+ Circular tabbing
	+ `ESCAPE` to close
	+ `aria-label`||`aria-labelledby`
	+ `aria-hidden` applied outside of the modal for screenreaders
- Mega menu
	+ `ENTER` opens submenu if it exists, activates button otherwise
	+ `DOWN ARROW` opens submenu
	+ `UP ARROW` can return you ot the top level
	+ Many more arrow details...
	+ `ESCAPE` closes submenu & returns focus to the parent
	+ No dual-purpose menu items because of the `ENTER` behavior
	+ `role=menubar||menuitem||menu`, `aria-haspopup=true`
	+ Use list to get a size count spoken or use `aria-setsize`
	+ Adobe has a Mega Menu exaple that uses `aria-expanded`
	+ [Example](http://mattisner.com/a11y-examples/menu/)
	+ Whether menu is horizontal or vertical doesn't matter; WCAG is very specific and should be followed even if it isn't intuitive for the sighted viewer
- Tabs
	+ `role=tablist||tab||tabpanel`, `aria-controls`, `aria-selected`, `aria-labelledby`, `aria-hidden`
	+ Use lists for the screenreader count
	+ ARROW keys, because tabbing a bunch really sucks.
- Checkboxes
	+ `SPACE` or 
	+ `aria-checked`, `aria-labelledby`, `role=checkbox`
- Application
	+ Overrides assisting technology
	+ Very very very rare cases where this is appropriate
	+ There is a list of elements/roles where you should't use role=application
	+ Google docs places `role=application` on the body & does it well
	+ Date-pickers are a potential use-case
- Validate your a11y with [aXe Chrome Extension](https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd)
##### Speakers
- Deque
- Harris Schneiderman, Web Application Developer
- [Slides](https://schne324.github.io/csun-advanced-aria)

## WCAG 2.1—A New Version of Accessibility Guidelines
[WCAG 2.1  draft](http://www.w3.org/tr/wcag21)
- 2.0 finalized Dec. 2008, tech agnostic
- Certain techs have become more important, new features exist
- Structure
	+ [Cognitive disability users addressed](https://w3.org/WAI/GL/cognitiv-a11y-tf)
	+ [Low vision users addressed](https://w3.org/WAI/GL/low-vision-a11y-tf)
	+ [Small-screen devices addressed](https://w3.org/WAI/mobile-a11y-tf)
	+ [Success Criteria](https://w3.org/WAI/GL/wiki/WCAG_2.1_Success_Criteria)
- [Timeline](https://w3.org/WAI/GL/project), wrap up main work by end of this year and proceed to ratification
- Work is also going in to WCAG 3.0 and could go in to WCAG 2.2 if needed
- Utilize the 2.0 A/AA/AAA structure
- Avoid modifying/replacing existing requirements
- [File issues](https://github.com/w3c/wcag21/issues/new)
##### Speakers
- [Slides](https://www.w3.org/2017/Talks/0303_WCAG21_MC/)
- Judy Brewer
- Michael Cooper
- Andrew Kirkpatrick

## Accessibility Ambassadors: Building a Community of Accessibility Advocates
Wells Fargo puts out the word to all employees
- Educating ambassadors
	+ Don't preach to the choir
	+ Be passionate
	+ "Edutain" the audience
- Measuring success
	+ Feedback
	+ Quantity of discussions around the office
	+ Flow of invites to the program
- RoI
	+ Engaged partners
	+ Water cooler conversations
	+ New way of thinking across the organization
### Meetings
Award or recognize ambassadors for their efforts improve access to our world
- Select interesting & somewhat-relevant content to open a dialog
	+ IoT
	+ Voting experiences during election season
	+ _Finding Dory_, _Finding Nemo_, & _Me Before You_
#### Special events
Special days & an awareness month.
#### Guest speakers
Sharing other people's work & experiences is very engaging
#### Partnerships with groups
Work with external groups that bring interesting stories & causes
#### Social media & news
#a11y search & other people's stories that spark conversations
#### Personal stories
Engaging & allow your ambassadors to contribute & share. Many people who have interest in being an ambassador do so because they have intimate experiences with disabilities.
##### Speakers
- Monica Reha, Digital Accessibility& Governance Manager, Wells Fargo

## A Product Manager’s Perspective on Accessibility: An IBM Case Study
So many product divisions, in so many product silos.
- Paradigm shift from Product Management to Offering Management
### Offering Management
- Process (Agile)
	+ Strategic planning & portfolio management
	+ Market opportunity & approach
	+ Define & prove
	+ Build & delive
	+ Sense & respond
### The change
#### First step: Accessibility 101
OM Bootcamp with an accessibility module that defined:
- What is accessibility
- Differentiate offerings
- Government & industry regulation
- Case studies / innovation
- Tools & resources
### Accessibility Training Classes
28 sessions, 1500+ attendees. A11yRocks Initiative.
### A11y & OM Deliverables/Artifacts
- Exploration Playback
- Market Playback
- Playback 0
	+ Consider disabled personas
	+ Define a11y requirements
- Commitment Pitch Playback
	+ Define compliance goals (A or AA or 508?)
	+ Accessible tech
	+ Skilled a11y resources
- Launch Readiness Playback
	+ VPAT
	+ A11y marketing materials
- Business Review Playbacks
	+ Market feedback
### IBM Accessibility Handbook
Delivers a message in the language of Offering Managers
- Does my team understand a11y & have the skills/resourcesi?
- What are the a11y needs of my target market?
- Within that market, what are their a11y needs?
- Is my offering fully accessible for launch?
##### Speakers
IBM Accessibility enablement team
---------------------------------

