# Structured Data (JSON-LD) for Kazandji Law

This folder contains copy-paste ready JSON-LD for key pages:

- Homepage: Organization + LegalService + WebSite + WebPage
- Location pages: LegalService with areaServed for each city
- Practice area pages: LegalService referencing the firm as provider, and includes a unique FAQPage.

How to use:

1) Place each JSON-LD snippet into a script tag in the matching page template:

   ```html
   <script type="application/ld+json">
   { ... JSON from the corresponding file ... }
   </script>
   ```

2) Replace placeholder values where noted (logo URL, images). If you have a physical office address for a city, use the LocalBusiness-style PostalAddress fields in that page instead of just areaServed.

3) Validate each page using Google's Rich Results Test and Schema.org validator.

Notes:

- If a location page is service-area only (no staffed office at a public address), keep it as LegalService with areaServed (do NOT add a fake street address). If you do have an office, add PostalAddress and optional geo.
- Keep the same @id anchors across pages for the Organization (`https://www.kazandjilaw.com/#org`) and WebSite (`https://www.kazandjilaw.com/#website`) to help search engines connect entities.
- The `aggregateRating` for the main Organization is included on all location and practice area pages to reflect the firm's overall reputation.
- Each practice area page contains a unique `FAQPage` to make them eligible for rich snippets.

---

### How to Validate Your JSON-LD

There are two main tools to validate your structured data:

1.  **Google's Rich Results Test:** This is the most important tool. It shows you which of Google's rich results (like FAQ snippets, review stars, etc.) can be generated from your structured data.
    - **Open the tool:** [Rich Results Test](https://search.google.com/test/rich-results)
    - **Select 'Code':** Click on the **CODE** tab.
    - **Paste and Test:** Copy the entire content of a `.jsonld` file, paste it into the code editor, and click **"TEST CODE"**.
    - **Review Results:** The tool will show you which rich result types are valid and list any errors or warnings.

2.  **Schema Markup Validator:** This tool is for general-purpose validation and checks if your markup is valid according to the full Schema.org standard.
    - **Open the tool:** [Schema Markup Validator](https://validator.schema.org/)
    - **Select 'Code snippet':** Click the **"Code snippet"** option.
    - **Paste and Test:** Copy and paste the content of your `.jsonld` file and click **"RUN TEST"**.
    - **Review Results:** The validator will show all the entities it found and list any errors or warnings.

