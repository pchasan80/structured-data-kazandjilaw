# Structured Data (JSON-LD) for Kazandji Law

This folder contains copy-paste ready JSON-LD for key pages:

- Homepage: Organization + LegalService + WebSite + WebPage
- Location pages: LegalService with areaServed for each city
- Practice area pages: Service referencing the firm as provider

How to use:

1) Place each JSON-LD snippet into a script tag in the matching page template:

   <script type="application/ld+json">
   { ... JSON from the corresponding file ... }
   </script>

2) Replace placeholder values where noted (logo URL, images). If you have a physical office address for a city, use the LocalBusiness-style PostalAddress fields in that page instead of just areaServed.

3) Validate each page using Google's Rich Results Test and Schema.org validator.

Notes:

- If a location page is service-area only (no staffed office at a public address), keep it as LegalService with areaServed (do NOT add a fake street address). If you do have an office, add PostalAddress and optional geo.
- Keep the same @id anchors across pages for Organization (`#organization`) and WebSite (`#website`) to help search engines connect entities.
