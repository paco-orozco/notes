# Semantic Structure and Navigation 

Semantic structure is the bedrock of accessible markup. Screen readers rely on the meaning of HTML elements and attributes to convey information to blind users. It is through the semantic markup that browsers are able to parse accessibility cues and information through the accessibility API and pass that information on to users, through assistive technologies, such as screen readers.

### Page Title 

The `<title>` of the page is critical, because it is the first thing a screen readers user hears. Blind users cannot glance quickly at the content of a web page to see what the page is about, so they rely on the page title to give them this information. Also has an added "SEO" benefit. 

- Title for every page. The page MUST be present and MUST contain text. The page title MUST be updated when the web address changes. 
- Meaningful page title. 
  - The page title MUST be accurate and informative.
  - If the page is the result of a user action or scripted change of context, the text of the title SHOULD describe the result or change of the context to the user. (ex. title w/search text) `<title>"Warranty" - Search Results</title>`
  - The title SHOULD be concise. Best practice is to keep it as short as possible, without sacrificing accuracy or informativeness. 
  - The page SHOULD be unique, if possible. The goal is to give page titles that allow for easy and accurate identification.
  - Unique information SHOULD come first in the title. (ex. purpose of page is listed first) `<title>Mortgage Calculators - Smallville Credit Union</title>`
  - The page SHOULD match (or be very similar to) the top heading in the main content. Both the `<title>` and the top heading in the main content (ideally marked with `<h1>`) serve essentially the same purpose: to give the page a title.

### Language

- The primary language of the page MUST be identified with a valid value on the `<html>` element.
- Inline language changes MUST be identified with a valid _lang_ attribute. (ex. w/Spanish language) `<span lang="es">No comprendo nada de lo que dices.</span>`

### Landmarks

HTML has historically lacked some key semantic markers, such as the ability to designate sections of the page as the header, navigation, main content, and footer. With HTML 5, these designations are possible, using the new elements `<header>`, `<nav>`, `<main>`, and `<footer>`. Similar functionality is available using the ARIA (Accessible Rich Internet Application) attributes role="banner", role="navigation", role="main" and role="contentinfo".

- Landmarks SHOULD be used to designate pre-defined parts of the layout (`<header>`, `<nav>`, `<main>`, `<footer>`, etc.).
- All text SHOULD be contained within a landmark region.
- Multiple instances of the same type of landmark SHOULD be distinguishable by different discernible labels (aria-label or aria-labelledby). (ex w/multiple nav elements) `<nav aria-label="Main Menu">...</nav>` and `<nav aria-label="Product list">...</nav>`
- A page SHOULD NOT contain more than one instance of each of the following landmarks: banner, main, and contentinfo.
- The total number of landmarks SHOULD be minimized to the extent appropriate for the content. One of the main purposes of landmarks is to allow blind users to quickly find and navigate to the appropriate landmark, so you should keep the total number of landmarks relatively low.
- Landmarks SHOULD be made backward compatible. If you plan to support older browsers that don't understand HTML 5 elements, you'll need to take some extra steps and ensure the HTML 5 elements render correctly visually and in the DOM.
  - Set landmarks to display: block (To ensure that HTML 5 landmarks display properly for old browsers)
  - Use JS to fix landmark rendering issues in IE 8 and below

### Headings

- Text that acts as a heading visually or structurally SHOULD be designated as a true heading in the markup. (ex. use `<h1>`, `<h2>`, etc.)
- Text that does not act as a heading visually or structurally SHOULD NOT be marked as a heading. This is confusing for users that depend on screen readers because it creates an inaccurate structural outline of the page contents. 
- Headings MUST be accurate and informative. Heading Text SHOULD be concise and relatively brief.
- Headings SHOULD convey a clear and accurate structural outline of the sections of content of a web page.
- Headings SHOULD NOT skip hierarchical levels. 
- Heading Level 1 best practices:
  - The beginning of the main content SHOULD start with `<h1>`
  - Most web pages SHOULD have only one `<h1>`. Modals or overlays can be potential exceptions. Another exception could include index pages of several blog articles, in which every blog article preview begins with an `<h1>`

### Links

Links and buttons SHOULD be designated semantically according to their functions. Screen reader users are informed whether something is a button or a link.

1. __Links take users to different locations__ (either to a different page or to a different location on the same page);
2. __Buttons activate scripted functionality__ (e.g. make a dialog appear, expand a collapsed menu, turn font bold, etc.), usually on the same page, but a button can also submit form data.

- Links MUST be semantically designated as such:
  - A link marked with `<a>` wit a valid href value
  - A link marked with `role="link"` and `tabIndex="0"`
- A link that opens in a new window or tab SHOULD indicate that it opens in a new window or tab. (Indicate using alt text or CSS and Aria)
- A link to a file or destination in an alternative or non-web format SHOULD indicate the file or destination type. (ex. linking to a PDF) Can implement using alt text or link text.
- Links MUST be visually distinguishable from surrounding text.
- All focusable elements MUST have a visual focus indicator when in focus.
- Focusable elements SHOULD have enhanced visual focus indicator styles.

### Navigation between pages

- A navigation list SHOULD be designated with the `<nav>` element or `role="navigation"`.
- A navigation list SHOULD include a visible method of informing users which page within the navigation list is the currently active/visible page.
- A navigation list SHOULD include a visible method of informing users which page within the navigation list is the currently active/visible page.
  - visually hidden text
  - aria-label
  - aria-labelledby
  - aria-describedby
- Navigation patterns that are repeated on web pages MUST be presented in the same relative order each time they appear and MUST NOT change order when navigating through the site. (keep nav elements consistent throughout different pages)

### Navigation within pages 
- Skip Navigation Links
  - A keyboard-functional "skip" link SHOULD be provided to allow keyboard users to navigate - - directly to the main content.
  - The "skip link" SHOULD be the first focusable element on the page.
  - A skip link MUST be either visible at all times or visible on keyboard focus.
- Table of Contents
  - A table of contents for the page MAY be included at the top of the content or in the header.
  - If a table of contents for the page is included, it SHOULD reflect the heading structure of the page.
- Reading Order and Tab/Focus Order
  - The reading order MUST be logical and intuitive.
  - The navigation order of focusable elements MUST be logical and intuitive.
  - _tabindex_ of positive values SHOULD NOT be used.
- Paginated Views
  - A paginated view SHOULD include a visible method of informing users which view is the currently active/visible view.
  - A paginated view SHOULD include a method of informing blind users which view is the currently active/visible view.
- Single-Key Shortcuts
  - If a single-character-key shortcut exists, then at least one of the following MUST be true: single-character-key shortcuts can be turned off, remapped, or are only active when the relevant user interface component is in focus.

### Tables

- Semantic Markup for Tabular Data
  - Tabular data SHOULD be represented in a `<table>`.
- Table caption/name
  - Data tables SHOULD have a programmatically-associated caption or name.
  - The name/caption of a data table SHOULD describe the identity or purpose of the table accurately, meaningfully, and succinctly.
  - The name/caption of each data table SHOULD be unique within the context of other tables on the same page.
- Table Headers
  - Table headers MUST be designated with `<th>`.
  - Data table header text MUST accurately describe the category of the corresponding data cells.
- Simple Header Associations
  - Table data cells MUST be associated with their corresponding header cells.
- Grouped Header Associations
  - Table data group headers MUST be associated with their corresponding data cell groups.
- Complex Header Associations
  - Header/data associations that cannot be designated with `<th>` and scope MUST be designated with headers plus id.
- Nested or Split Tables
  - Data table headers and data associations MUST NOT be referenced across nested, merged, or separate tables.
- Table Summary
  - A summary MAY be provided for data tables.
  - A data table summary, if provided, SHOULD make the table more understandable to screen reader users.
- Layout Tables
  - Tables SHOULD NOT be used for the purpose of purely visual (non-data) layout.
  - Layout tables MUST NOT contain data table markup.

### Lists

- Semantic Markup for Lists
  - Lists MUST be constructed using the appropriate semantic markup.

### Iframes

- Frame titles
  - Iframes that convey content to users MUST have a non-empty title attribute.
  - The iframe title MUST be accurate and descriptive.
  - Frames MUST have a unique title (in the context of the page).
- Page Title Within an Iframe
  - The source page of an iframe MUST have a valid, meaningful `<title>`.
- Semantic structure across iframes
  - The heading hierarchy of an iframe SHOULD be designed to fit within the heading hierarchy of the parent document, if possible.
- Hiding iframes that don't contain meaningful content
  - Hidden frames or frames that do not convey content to users SHOULD be hidden from assistive technologies using aria-hidden="true".

### Other semantic elements

- `<strong>` and `<em>`
  - Critical emphasis in the text SHOULD be conveyed through visual styling.
  - Critical emphasis in the text SHOULD be conveyed in a text-based format.
- `<blockquote>` and `<q>`
  - The `<blockquote>` element SHOULD be used to designate long (block level) quotations.
  - The `<blockquote>` element SHOULD NOT be used for visual styling alone.
  - The `<q>` element (for inline quotations) SHOULD NOT be used as the only way to designate quotations.
- `<code>`, `<pre>`
  - Code SHOULD be marked with the `<code>` element.
  - Blocks of code SHOULD be formatted with the `<pre>` element.
- Strikethrough/Delete and Insert
  - Strikethrough text SHOULD be marked with the `<del>` element.
  - Critical strikethrough text MUST be supplemented with a text-based method to convey the meaning of the strikethrough.
  - Text designated for insertion SHOULD be marked with the `<ins>` element.
  - Critical text designated for insertion MUST be supplemented with a text-based method to convey the meaning of the insertion.
- Highlighting (`<mark>`)
  - Highlighted text SHOULD be marked with the <mark> element.
  - Critical highlighted text SHOULD be supplemented with a text-based method to convey the meaning of the highlighting.

### Parsing and validity

- Complete Start and End Tags
  - In content implemented using markup languages, elements MUST have complete start and end tags.
- Conflicts and duplicates
  - IDs MUST be unique within a web page.
  - Names, when provided, of block level elements (e.g. landmarks, tables, iframes, etc.) SHOULD be unique within a web page.
- Parent-child relationships
  - Markup SHOULD adhere to required parent-child relationships of elements and attributes.
- Deprecated Markup
  - Deprecated markup SHOULD NOT be used.