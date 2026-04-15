# Email Development Technical Test

## Part 1: Email Development

- **Live template (web):** https://vilrodriguez.github.io/ScentbirdEmailTemplate/
- **HTML template code:** https://github.com/vilrodriguez/ScentbirdEmailTemplate/blob/main/index.html
- **GitHub repo:** https://github.com/vilrodriguez/ScentbirdEmailTemplate#


### Summary

I built a responsive, cross-client compatible HTML email using a table-based layout, reusable CSS classes, and inline styles to ensure consistent rendering across major email clients, including Outlook.  

All content was implemented as live text to improve accessibility, deliverability, and maintainability. The structure was organized into modular sections to allow updates without impacting other parts of the email. I followed a logical reading order, applied appropriate alt text, and treated decorative images accordingly.  

The layout adapts to mobile devices using media queries, with attention to spacing, readability, and tap target sizing. For Outlook-specific support, I included a VML-based button fallback to preserve rounded corners.  

Basic cross-client testing was performed using available free online tools. For production, I would recommend using platforms like Litmus or Email on Acid for more comprehensive testing and debugging across email clients.

---

### Questions or Clarifications

Before starting the build in a real-world scenario, I would confirm:

- Final deadline for delivery  
- Whether all copy is final  
- Availability of final URLs for all links  
- Whether alt text is provided or needs to be written  
- Availability of translations and expected timeline  
- Confirmation that the design is final  
- Whether rounded corners require VML support in Outlook or can remain square  
- Whether background images should include VML fallback for Outlook  

---

### Merge Tags

The `{% unsubscribe_link %}` tag is included in the footer section of the email.

---

## Part 2: Multilanguage Localization Plan

### Templating Approach

To support multiple languages, I would use a single, modular email template with dynamic content rendering rather than duplicating templates per language. Language selection would be driven by a user attribute (e.g., `language`, `content_locale`, `web_locale`), with a fallback to English if no value is present.  

Within the template, I would use conditional logic or a centralized translation object to inject the correct copy at send time. This approach keeps the structure consistent while allowing content to scale efficiently as more languages are added.  

To improve maintainability, content would be organized into reusable sections (headline, body, CTA, footer), with each pulling from language-specific values. If supported by the ESP, I would leverage content blocks or external data sources (e.g., JSON via connected content) to manage translations more cleanly.  

For send timing, I would use timezone-based delivery where the ESP sends the email at a consistent local time (e.g., 9 AM) for each user. If this is not available, I would segment audiences by region and schedule sends accordingly. Where possible, send-time optimization could also be used to improve engagement.

---

### Content and Translation Management

Translations would be managed through a centralized source (such as a structured spreadsheet or JSON file), ensuring consistency across all language variants. This allows for easier updates and reduces the risk of inconsistencies between versions.  

The template would be designed to handle text expansion across languages by avoiding fixed heights, using responsive layouts, and ensuring all text remains live (not embedded in images). UTF-8 encoding would be used to properly support special characters and accents.  

### QA Process

- Verify all translations are correctly implemented and fallback logic works as expected  
- Review layout and readability across languages and elements (header, links, CTA, etc.), especially for longer languages (e.g., German)  
- Test all links, merge tags, and functionality per locale (if localization is applied)  
- Perform cross-client testing (Gmail, Outlook, Apple Mail, Yahoo) using tools like Litmus or Email on Acid  

---

This approach ensures the email remains scalable, maintainable, and consistent across languages while meeting accessibility and cross-client requirements.