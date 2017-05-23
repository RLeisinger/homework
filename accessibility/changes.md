// Your recommended changes go here

The first time I visited https://www.healthcare.gov/see-plans/<br>
I got a modal window which I tested first
<p>
Some changes are listed, there are more that could be done on the modal and page


## Visual to the UI (CSS, visual elements)

## Technical changes: HTML, CSS, Javascript, ARIA attributes
What is wrong: Empty button violates WCAG 2.0 1.1.1 (Non-text Content) & 2.4.4 (Link Purpose)<br>
How tested: Automated code testing DOM against WCAG 2.0 AA<br>
How to fix: Add screen reader only text using existing screen reader only CSS<br>
Solution: Replace<br>
<button class="prefix-overlay-close prefix-overlay-action-later" title="Close subscription dialog"></button><br>
with<br>
<button class="prefix-overlay-close prefix-overlay-action-later" title="Close subscription dialog"><span class="sr-only">Close subscription dialog</span></button><br>
<p></p>
What is wrong: Inputs lack proper labels<br>
How tested: Automated code testing DOM against WCAG 2.0 AA<br>
How to fix: Add labels in inputs<br>
Solution:<br>
Replace<br>
<input placeholder="Enter email address" name="e" type="email" id="prefix-emailInput" title="Enter email address"><br>
with<br>
<input placeholder="Enter email address" name="e" type="email" id="prefix-emailInput" aria-label="Enter email address">
<p></p>
Replace<br>
<select name="q_23536" class="prefix-questionId"><br>
with<br>
<select name="q_23536" class="prefix-questionId" aria-label="Select State"><br>
<p></p>

What is wrong: Tab order doesn't match visual UI<br>
How tested: Keyboard only navigation (tab between focusable elements)<br>
How to fix: Match tab order an visual order<br>
Solution: Replace CSS that is re-ordering inputs and let natural order set visual order and tab order<br>
<p></p>

What is wrong: Email address is required field, yet no indication<br>
How test: tested form with NVDA, attempted to submit form with no email<br>
How to fix: Visual UI requires inidcator for required fields (*), screen reader needs to know required elements<br>
Solution: Replace<br>
<input placeholder="Enter email address" name="e" type="email" id="prefix-emailInput" title="Enter email address"><br>
with<br>
<input placeholder="Enter email address" name="e" type="email" id="prefix-emailInput" title="Enter email address" aria-required="true"><br>


## Content

After getting past the modal

## Visual to the UI (CSS, visual elements)
What is wrong: No visual indication when focus is on Navigation elements (Individuals & Families or Businesses)<br>
How tested: Keyboard only navigation with screen reader<br>
Solution: use :focus to match hover state to relay focus to tab nav users<br>

## Technical changes: HTML, CSS, Javascript, ARIA attributes
What is wrong: Inconsistent experience with Skip Navigation link (doesn't always work, doesn't take me to content)<br>
How tested: Keyboard only navigation with screen reader<br>
Solution: Replace script with simplier keyboard navigation only skip to main content link<br>

## Content
