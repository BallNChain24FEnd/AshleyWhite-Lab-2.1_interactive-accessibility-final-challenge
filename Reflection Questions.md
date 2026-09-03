Accessibility Lab Reflection and Corrections

1. What accessibility enhancements were the most challenging to implement, and why?

The most challenging accessibility enhancements were creating accessible form fields and properly structuring the HTML. I connected each `<label>` to its input using `for` and `id`, and used `<fieldset>` and `<legend>` to group radio buttons. I also used semantic elements such as `<header>`, `<main>`, `<section>`, `<nav>`, and `<footer>` instead of relying on `<div>` tags. During the lab, I added a skip navigation link for keyboard and screen-reader users and used rem units so font sizes can adjust more easily to browser settings.

2. How do ARIA attributes improve the experience for users relying on assistive technologies?

ARIA attributes give screen readers additional information about elements and their purpose. For example, aria-describedby can connect a form field to additional instructions or an error message, while aria-live="polite" can announce updated content. I also learned that accessibility includes providing meaningful alternative text (alt) for images, so users who cannot see an image can still understand its purpose. Decorative images can use alt="" so screen readers can ignore them.

3. What tools did you use to check color contrast, and how did they help?

I used the WebAIM Contrast Checker to test text contrast between foreground and background colors. One of my tests showed a contrast ratio of 8.59:1, which passed WCAG AA and AAA standards for normal and large text. This helped me understand how proper text contrast makes content easier to read for users with low vision or other visual impairments.



Final Challenge accessibility corrections also found on the bottom of the index.css page.

The following current issues have been fixed and resolved:

- Placeholder text has poor text contrast. Changed to a more muted color for visibility 
  .contact-input::-webkit:-webkit-input-placeholder, .contact-textarea::
  -webkit:-webkit-input-placeholder {
    color: #555555; from #aaaaaa.✔️

- Missing alternative text for images. Now, alt="A robot hand and a human reaching for each other.
  This allows users who cannot see the image to understand what it represents.✔️

- Missing labels for input fields. Filled in "Full Name," "Email," and "Message" labels. Then connected 
  each label to its input using matching for and id attributes. This helps screen-reader users 
  identify what information belongs in each field.✔️

- Ambiguous button text. The original button said “Done 🎉”, which was not very descriptive. 
  A screen-reader user might not understand what action the button would perform. I changed the button 
  text to “Send message 🎉” so the purpose of the button is clear.✔️

- Semantic HTML is lacking. The original code used `<div id="main">` for the main content area. I replaced 
  it with the semantic `<main>` element. I also changed the main heading from `<h2>` to `<h1>`. These changes 
  help screen readers understand the structure and importance of the content on the page.✔️
  
- Font-sizes were defined in px instead of rems. Corrected where applies. If a user increases their 
  browser’s default text size for readability, the page text can grow with it more reliably. Px's are 
  fixed and less flexible✔️

Contact page is now accessible!🦸 In fact, Lighthouse gives this webpage a 100% for Performance, 84% for Accessibility, 96% for Best Practice, and 82% SEO. Just two warnings needed to be fix: 1. A form field has an id or name attribute that the browser's autofill recognizes. However, it doesn't have an autocomplete attribute assigned. This might prevent the browser from correctly autofilling the form. To fix this issue, provide an autocomplete attribute. 2. One or more documents in this page is in Quirks Mode. You can add or modify the DOCTYPE to be `<!DOCTYPE html>` to render the page in No Quirks Mode.
