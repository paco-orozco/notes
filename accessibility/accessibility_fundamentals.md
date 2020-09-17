# Accessibility Fundamentals
### Considerations
- custom controls (e.g., expand/collapse buttons, media player volume control, dialogs, etc.) Unlike native HTML elements, custom controls have no semantic parts natively, so screen readers can't tell users what the widget is and can't update users on the properties of the widget unless you supply that information via ARIA names, roles, states, and properties.
- users must receive immediate feedback after all actions. Examples of feedback: Expand/collapse region, value changed on a control (e.g., on a slider, successful/unsuccessful form submission, notification that a new "page" has loaded in single-page app, etc.).
- The pinch-to-zoom feature must not be disabled
html
<meta name="viewport" content="user-scalable=no">
When zooming is disabled on a web page, which the parameter `user-scalable=no` does, low vision users who use screen magnifiers to read content may be unable to properly see information on a web page.
- All text mus pass contrast guidelines against the background (verify using Deque's aXe accessibility browser extension or a similar tool). Textual elements that are too close in brightness to background colors may be difficult for users with low vision to see. 
- Links, buttons, and controls must have a visible `:focus` state and should have a visible `:hover` state. Having these focus states helps users to know where the keyboard/mouse focus is on a web page.
- Provide large click targets (links, buttons, controls) for consideration of users with motor disabilities. 
### WCAG (Web Content Accessibility Guidelines)
Level of criterion: 
- Level A (the minimum)
- Level AA (internal standard for most orgs because it is both achievable and meaningful without being burdensome to developers)
- Level AAA (the maximum)
**The 4 Main Principles**
1. Perceivable: Information and user interface components must be presentable to users in ways they can perceive. *[Ensure content is accessible to people who are blind and/or deaf.]
2. Operable: User interface components and navigation must be operable. *[Make sure all features are accessible by keyboard; not just by mouse].
3. Understandable. Information and operation of user interface must be understandable.
4. Robust. Content must be robust enough that it can be interpreted reliably by a wide variety of user agents, including assistive technologies.
**The 13 Guidelines**
1. Perceivable
- 1.1 Provide text alternatives for any non-text content so that it can be changed into other forms people need, such as large print, braille, speech, symbols or simpler language.
- 1.2 Provide alternatives for time-based media.
- 1.3 Create content that can be presented in different ways (for example simpler layout) - without losing information or structure.
- 1.4 Make it easier for users to see and hear content including separating foreground from background.
2. Operable
- 2.1 Make all functionality available from a keyboard.
- 2.2 Provide users enough time to read and use content.
- 2.3 Do not design content in a way that is known to cause seizures.
- 2.4 Provide ways to help users navigate, find content, and determine where they are.
- 2.5 Make it easier for users to operate functionality through various inputs beyond keyboard.
3. Understandable 
- 3.1 Make text content readable and understandable.
- 3.2 Make Web pages appear and operate in predictable ways.
- 3.3 Help users avoid and correct mistakes.
4. Robust 
- 4.1 Maximize compatibility with current and future user agents, including assistive technologies.
### Aria 
**Overview** 
WAI-ARIA—or just ARIA, for short—is a somewhat recent invention, intended to help fill in the gaps between the accessibility features of HTML and the real-world accessibility needs of today's robust, dynamic web applications, especially with regard to JavaScript. ARIA allows developers to specify the name, role, state, and property of HTML elements in both static and dynamic content. ARIA is not an entirely new language. It is an add-on to the HTML syntax. For example, to add a role of "navigation" to an HTML element, simply type it as an attribute.
ARIA is almost entirely for screen reader users (and for speech recognition users and some keyboard-only users), in the sense that the markup is hidden, and ARIA allows screen reader users to know what's happening visually on the screen, such as: 
- If a link opens a popup window
- If an object (like a folder icon) is expandable
- If an object is currently expanded or collapsed
- If something has changed or been updated on the page (via "live regions")
- What type of object or widget it is; for example:
  - A tab panel
  - A tab
  - A slider
  - An alert dialog
  - A tooltip
  - A menu
  - A menu item
  - A hierarchical tree view
  - And several other pre-defined roles