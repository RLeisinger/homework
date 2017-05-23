// Your recommended changes go here

The first time I visited https://www.healthcare.gov/see-plans/
I got a modal window which could have improved access


## Visual to the UI (CSS, visual elements)

## Technical changes: HTML, CSS, Javascript, ARIA attributes
What is wrong: Empty button violates WCAG 2.0 1.1.1 (Non-text Content) & 2.4.4 (Link Purpose)
How tested: Automated code testing DOM against WCAG 2.0 AA
How to fix: Add screen reader only text using existing screen reader only CSS
Solution: Replace
<button class="prefix-overlay-close prefix-overlay-action-later" title="Close subscription dialog"></button>
with
<button class="prefix-overlay-close prefix-overlay-action-later" title="Close subscription dialog"><span class="sr-only">Close subscription dialog</span></button>

What is wrong: Inputs lack proper labels
How tested: Automated code testing DOM against WCAG 2.0 AA
How to fix: Add labels in inputs
Solution:
Replace
<input placeholder="Enter email address" name="e" type="email" id="prefix-emailInput" title="Enter email address">
with
<input placeholder="Enter email address" name="e" type="email" id="prefix-emailInput" aria-label="Enter email address">

Replace
<select name="q_23536" class="prefix-questionId">
with
<select name="q_23536" class="prefix-questionId" aria-label="Select State">

What is wrong: Tab order doesn't match visual UI
How tested: Keyboard only navigation (tab between focusable elements)
How to fix: Match tab order an visual order
Solution: Replace CSS that is re-ordering inputs and let natural order set visual order and tab order


What is wrong: Email address is required field, yet no indication
How test: tested form with NVDA, attempted to submit form with no email
How to fix: Visual UI requires inidcator for required fields (*), screen reader needs to know required elements
Solution: Replace
<input placeholder="Enter email address" name="e" type="email" id="prefix-emailInput" title="Enter email address">
with
<input placeholder="Enter email address" name="e" type="email" id="prefix-emailInput" title="Enter email address" aria-required="true">


## Content

After getting past the modal

## Visual to the UI (CSS, visual elements)
What is wrong: No visual indication when focus is on Navigation elements (Individuals & Families or Businesses)
How tested: Keyboard only navigation with screen reader
Solution: use :focus to match hover state to relay focus to tab nav users

## Technical changes: HTML, CSS, Javascript, ARIA attributes
What is wrong: Inconsistent experience with Skip Navigation link (doesn't always work, doesn't take me to content, 
How tested: Keyboard only navigation with screen reader
Solution: Replace script with simplier keyboard navigation only skip to main content link

## Content
