# Form Labels, Instructions, and Validation

### Labels

In order for users to know how to fill out a form, the form has to be accessible. For the most part this is easy to do. Key concepts include: 

- Labels for form inputs
- Labels for groups of inputs
- Instructions and hints, where necessary
- Error prevention 
- Form validation

With all of these, information must be visible on the screen, accurate and meaningful., programmatically discernible, and programmatically associated with the appropriate form element or group. 

The more interactive a form element or process is, the more attention needs to be given to accessability with respect to:

- Focus management 
- Setting and updating ARIA names, roles, and values, where necessary
- ARIA live announcements, where necessary 

__All form inputs and controls need to have a label__ — a label that is understandable by all users whether the user can see the page or not.

- Semantic Labels
  - Labels MUST be programmatically associated with their corresponding elements
    - __`<label>`__ (recommended method for most circumstances)
    - __aria-labelledby__ clicking on the aria-labelledby text does not put the focus in the associated form input, so it is an inferior choice, and should be used only when `<label>` does not work.
    - __`aria-label`__ it is only useful to screen reader users so not appropriate in most circumstances
    - __title attribute__ usually intended for extra, non-essential information, not for providing an accessible name
    - __placeholder__ highly discouraged because:
      1. it disappears as soon as users start typing
      2. the default styling fails contrast rules
      3. the intended use of _placeholder_ text is for extra, non-essential information  
  - Labels MUST be programmatically-discernible
- Meaningful Label Text
  - Labels MUST be meaningful
  - Labels MUST NOT rely solely on references to sensory characteristics 
    - _aria-label_ is informative
- Icons as Labels
  - Icons MAY be used as visual labels (without visual text) if the meaning of the icon is visually self-evident AND if there is a programmatically-associated semantic label available to assistive technologies.
- Placeholder Text as Labels
  - Placeholder text MUST NOT be used as the only method of providing a label for a text input
- Visibility of Labels
  - Labels MUST be visible
  - For user interface components with labels that include text or images of text, the name MUST contain the text that is presented visually
- Multiple Labels for One Field
  - When multiple labels are used for one element, each label MUST be programmatically associated with the corresponding element
- One Label for Multiple Fields
  - When one label is used for multiple elements, the label MUST be programmatically associated with each of the corresponding elements

### Group Labels
- Semantic Group Labels
  - Group labels MUST be programmatically-associated with the group if the individual labels for each element in the group are insufficient on their own.
  - Group labels MUST be programmatically-discernible.
- Meaningful Group Labels
  - Group labels MUST be meaningful.
  - Group labels MUST NOT rely solely on references to sensory characteristics.
- Proximity of Group Labels
  - Group labels SHOULD be visually adjacent to the grouped elements.
  - Group labels SHOULD be adjacent in the DOM to the grouped elements.
-Visibility of Group Labels
  - Group labels MUST be visible.

### Instructions & Other Helpful Info

One of the easiest ways to increase the accessibility of forms is to help users avoid making errors before they even happen. It is important that instructions and other helpful information are provided to users to help them successfully complete a form online.

- Ensure labels and instructions are clear and informative
- Make instructions and advisory information available to assistive technologies
- Clearly disclose constraints for form fields
- Clearly identify required form fields

- Instructions for Forms, Groups, and Sections
  - Instructions for groups or sections SHOULD be programmatically-associated with the group.
  - Instructions for groups or sections MUST be programmatically-discernible.
  - Instructions for groups or sections MUST be meaningful.
  - Instructions for groups or sections MUST be visible.
  - Instructions for groups or sections SHOULD be visually adjacent to the grouped elements.
  - Instructions for groups or sections SHOULD be adjacent in the DOM to the grouped elements.
  - If the instructions for groups or sections are not critical, the instructions MAY be hidden until the user requests them.
  - Instructions for groups or sections MUST NOT rely solely on references to sensory characteristics.
- Instructions for Inputs
  - Instructions for an element MUST be programmatically-associated with the element.
  - Instructions for an element MUST be available as programmatically-discernible text.
  - Instructions for an element MUST be meaningful.
  - Instructions for an element MUST be visible.
  - Instructions for an element SHOULD be visually adjacent to the element.
  - Instructions for an element SHOULD be adjacent in the DOM to the element.
  - If the instructions for an element are not critical, the instructions MAY be hidden until the user requests them.
  - Instructions for an element MUST NOT rely solely on references to sensory characteristics.
- Required Fields
  - Required fields SHOULD be programmatically designated as such.
  - Required fields SHOULD have a visual indicator that the field is required.
  - The form validation process MUST include an error message explaining that a field is required if the field isn't identified as required both visually and programmatically in the form's initial state.
- Input Purpose
  - The purpose for each common input field that collects an individual's personal data MUST be programmatically defined based on the list of 53 Input Purposes for User Interface Components.

### Dynamic Forms & Custom Widgets

- Changes in Context
  - Focusing on an element MUST NOT automatically trigger a change of context, unless the user has been adequately advised ahead of time.
  - Changing an element's value MUST NOT automatically trigger a change of context, unless the user is adequately advised ahead of time.
  - Hovering over an element with the mouse MUST NOT automatically trigger a change of context, unless the user has been adequately advised ahead of time.
- Custom Form Inputs
  - Native HTML form elements SHOULD be used whenever possible.
  - Custom form elements SHOULD act like native HTML form elements, to the extent possible.
  - Custom form elements SHOULD have appropriate names, roles, and values.
  - Updates and state changes that cannot be communicated through HTML or ARIA methods SHOULD be communicated via ARIA live messages.

### Form Validation 

Despite the best instructions in the world, mistakes will be made in forms. An important aspect of a form’s accessibility is how the errors are handled. Some of the things to consider for form validation based on the guidelines are:

- Let users know of any input errors that prevent form validation or let them know if form submission was successful. When an error is made, if a screen reader user does not receive any useful feedback from their assistive technology, that is a really poor experience. Similarly, if a sighted user does not visually see what errors were made in the form, that is also a poor experience.
- Preserve as much correct information as possible.
- Display error messages in context for quick resolution.
- Give users enough information to let them know how to fix the errors. Error alerts must:
  - Be clearly stated
  - Provide actionable feedback messages
  - Draw attention and focus to their message
  - Be styled distinctively from form inputs
  - Be fully accessible

- Error Identification Considerations
  - Error feedback SHOULD be made available immediately after form submission (or after an equivalent event if there is no form submission event).
  - Error feedback MUST be programmatically-associated with the appropriate element.
  - Error feedback MUST be programmatically-discernible.
  - Error feedback MUST be meaningful.
  - Error feedback MUST be visible.
- Success Confirmation Considerations
  - Success confirmation feedback SHOULD be programmatically-discernible.
  - Success confirmation feedback SHOULD be meaningful.
  - Success confirmation feedback MUST be visible.