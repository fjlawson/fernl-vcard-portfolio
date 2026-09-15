# AI Log
For each prompt, I used UMGPT, the model being GPT-5.6 Sol.

## 1st Prompt
**I first began with this prompt:**

You are assisting with a small, public static portfolio website.

Project context:
- Purpose: present a student's skills and projects to internship reviewers.
- Existing system: an HTML/CSS/JavaScript portfolio template.
- Allowed changes: content, styling, and small front - end corrections only.
- Do not add: a backend, login system, analytics tracker, or external data collection.
Acceptance criteria:
1. The landing page displays my full name and status as a student at my institution.
2. None of the sections are duplicates of existing sections.
3. Each section within the portfolio is separate. Additionally, no information is copied to other sections.
4. No placeholders (such as names, images, or links) remain on the finished website.
5. The page is readable on desktop as well as mobile devices.

Constraints:
- Do not invent education, work history, awards, links, or technical skills.
- Preserve required license and attribution.
- Keep the site usable on mobile screens.
- Maintain readable contrast, keyboard navigation, meaningful link text,and useful image alternative text.
- Do not expose private information.

First provide:
- A file-by-file implementation plan.
- Any Assumptions or risks.
- A proposed test checklist.
- Any questions that must be answered before implementation.Do not modify files until the plan is reviewed.

**The AI replied with:**

### 1. File-by-file implementation plan

Because the repository contents have not been provided, this plan uses common template filenames. I will map it to the actual structure after reviewing the files.

#### `index.html` or equivalent landing-page file

- Audit all existing sections, navigation items, links, images, and template content.
- Replace placeholder identity content with:
  - Full name
  - Student status
  - Institution
- Create a clear, nonduplicative information structure using only verified content, likely:
  - Introduction
  - Skills
  - Projects
  - Contact or approved professional links
- Ensure every fact appears in only its most relevant section.
- Remove duplicate sections rather than renaming or lightly rephrasing them.
- Remove any section that cannot be completed without invented or placeholder content.
- Replace placeholder links and images with user-provided assets or remove them cleanly.
- Use semantic HTML:
  - One descriptive `<h1>`
  - Logical heading order
  - `<nav>`, `<main>`, `<section>`, and `<footer>` where appropriate
  - Lists for grouped skills and projects
- Give links meaningful text instead of phrases such as “click here.”
- Add useful alternative text for informative images and empty `alt=""` for purely decorative images.
- Preserve any required license or attribution text.

#### CSS files, such as `styles.css`

- Preserve the template’s visual direction unless changes are necessary for readability or correctness.
- Make the layout responsive without relying on horizontal scrolling.
- Add or refine breakpoints for narrow mobile screens.
- Ensure:
  - Readable font sizes and line spacing
  - Sufficient text and interface contrast
  - Visible keyboard focus indicators
  - Comfortable link and button target sizes
  - Images and cards scale within their containers
  - Long project names, links, and descriptions wrap correctly
- Avoid fixed dimensions that break zooming or small screens.
- Respect reduced-motion preferences if the template includes animation.
- Remove unused styles only when their removal is clearly safe.

#### JavaScript files, such as `script.js`

- Audit scripts for template-only behavior, broken selectors, console errors, analytics, or external collection.
- Make only small front-end corrections, such as:
  - Accessible mobile-navigation toggling
  - Correct `aria-expanded` updates
  - Keyboard-operable controls
  - Safe handling of missing elements
  - Internal navigation behavior
- Remove analytics or external data-collection code if present, subject to preserving required attribution and confirming that removal does not violate the template license.
- Avoid adding a backend, login, tracking, or unnecessary dependencies.
- Avoid JavaScript for behavior that native HTML and CSS can handle reliably.

#### Images and other assets

- Inventory every image, icon, document, and downloadable file.
- Remove unused placeholder assets from the rendered site.
- Replace visible placeholders only with supplied or approved assets.
- Optimize oversized images while preserving reasonable quality.
- Assign useful alternative text based on each image’s purpose.
- Confirm that local asset paths and filename capitalization work on static hosting.
- Preserve asset-level licenses or attribution where required.

#### Metadata and supporting files

Depending on the repository, this may include `README.md`, a manifest, favicon files, or license documents.

- Update the page title and description using verified information.
- Remove placeholder social-preview metadata.
- Use only an approved favicon or remove an invalid placeholder reference.
- Preserve `LICENSE`, copyright notices, attribution comments, and required README credits.
- Update documentation only as needed to explain the site structure and static deployment.
- Do not include private contact details, credentials, unpublished documents, or sensitive metadata.

---

### 2. Assumptions and risks

#### Assumptions

- The site is a small static project built with HTML, CSS, and JavaScript.
- The existing template license permits content and styling changes.
- Final biography, project, skill, link, and asset information will be supplied or is already verifiably present in the repository.
- Sections without verified content may be removed rather than filled with generic text.
- Public contact information will be included only if explicitly approved.

#### Risks

- **Unknown file structure:** The exact plan may change after the repository is inspected.
- **Placeholder ambiguity:** Some polished template copy or stock imagery may not be obviously labeled as placeholder content.
- **Duplicate-content ambiguity:** Similar facts may appear in an introduction, education area, résumé, project card, or footer. I will consolidate them unless repetition is necessary for navigation or accessibility.
- **Licensing:** Template comments, credits, bundled assets, fonts, or icons may carry separate attribution requirements.
- **Insufficient content:** If verified content is unavailable for a section, keeping it would violate the no-placeholder and no-invention requirements.
- **External resources:** Fonts, embeds, icons, forms, or scripts may contact third parties even if they are not analytics. These should be reviewed before release.
- **Privacy:** Résumés, image metadata, email addresses, phone numbers, locations, or document properties can expose unintended personal information.
- **Accessibility regression:** Template animation, custom controls, menu behavior, low-contrast color choices, or nonsemantic clickable elements may require correction.
- **Static-hosting differences:** Case-sensitive paths, base URLs, and routing can work locally but fail after deployment.

---

### 3. Proposed test checklist

#### Content and acceptance criteria

- [ ] Landing page visibly displays the student’s full name.
- [ ] Landing page states that the student is a student at the named institution.
- [ ] All claims match information supplied or verified by the user.
- [ ] No education, work history, awards, technical skills, or links were invented.
- [ ] Every section has a distinct purpose and heading.
- [ ] No section duplicates an existing section.
- [ ] Information is not copied between sections.
- [ ] No template names, sample biographies, lorem ipsum, stock project data, or placeholder images remain.
- [ ] No `#`, empty, example-domain, or template-author links remain unless intentionally required.
- [ ] No unfinished labels such as “coming soon,” “your image,” or “project title” remain.
- [ ] Required license and attribution are preserved.

#### Functionality

- [ ] All internal navigation links reach the correct section.
- [ ] All approved external links resolve to their intended destinations.
- [ ] Links do not trigger unsafe or unexpected downloads.
- [ ] No JavaScript errors appear during normal use.
- [ ] Mobile navigation opens, closes, and reports its state correctly.
- [ ] The page remains useful if JavaScript fails, where practical.
- [ ] No backend, authentication, analytics, or external data collection is introduced.
- [ ] Any existing third-party network requests are reviewed and documented or removed where appropriate.

#### Responsive design

- [ ] Test at approximately 320, 375, 768, 1024, and 1440 CSS pixels wide.
- [ ] Test portrait and landscape orientations.
- [ ] No unintended horizontal scrolling occurs.
- [ ] Text does not overlap, clip, or become excessively small.
- [ ] Images, cards, and navigation remain within the viewport.
- [ ] Long words, URLs, and project titles wrap safely.
- [ ] The page remains usable at 200% browser zoom.

#### Accessibility

- [ ] The page has a descriptive title and one clear top-level heading.
- [ ] Heading levels follow a logical order.
- [ ] Landmarks and sections use semantic HTML.
- [ ] Every interactive element is reachable and operable by keyboard.
- [ ] Focus indicators are clearly visible.
- [ ] Keyboard focus order follows the visual and reading order.
- [ ] No keyboard trap exists.
- [ ] Link text is meaningful out of context.
- [ ] Informative images have useful alternative text.
- [ ] Decorative images use empty alternative text.
- [ ] Text and interface contrast meet Web Content Accessibility Guidelines (WCAG) 2.1 Level AA where applicable.
- [ ] Content does not rely on color alone.
- [ ] Motion respects `prefers-reduced-motion`.
- [ ] Automated accessibility checks are run, followed by manual keyboard testing.

#### Quality, privacy, and deployment

- [ ] HTML and CSS validation reveal no material errors.
- [ ] Asset paths work under the target static host.
- [ ] Filename capitalization is correct.
- [ ] Images are reasonably compressed and do not cause excessive loading.
- [ ] No credentials, private identifiers, hidden drafts, or private contact information are published.
- [ ] Image and document metadata are reviewed where relevant.
- [ ] The page is tested in current desktop and mobile browser engines where available.
- [ ] The final diff contains only approved content, styling, and small front-end corrections.

---

### 4. Questions that must be answered before implementation

1. **Can you provide the project files or repository contents**, including the license and all assets?
2. **What exact full name, student-status wording, and institution name should appear on the landing page?**
3. **What verified content should be included?** Please provide the final project details, technical skills, biography, and any education or work information you want shown.
4. **Which public links and contact methods are approved?** For example, a portfolio-safe email address, GitHub profile, LinkedIn profile, live project URLs, or résumé download.
5. **Which images may be published, and what does each image depict?** This is needed to remove placeholders and write accurate alternative text.
6. **What static hosting environment is targeted?** For example, GitHub Pages, U-M web hosting, Netlify, or another service.

No files will be modified until this plan has been reviewed and the necessary verified content is available.


## 2nd Prompt

**I replied with:**

1. The project files are at https://github.com/fjlawson/fernl-vcard-portfolio. First, you should inspect index.html and change the template code to match the student's.
2. The student's info will be listed below.
3. Remove the images from the Testimonials, Clients, Portfolio, and Blog sections. The Portfolio should list the specified projects in text boxes rather than with images.
4. The project will be hosted on GitHub Pages

The student's info is as follows:

### Section 1: Name and About

Name: Fern Lawson

About Me: I am a Computer Science student currently looking for opportunities in the field of software development, UI/UX design, and IT. I have four years of experience programming in Java and 2 years of experience programming in C++.

### Section 2: Education and Skills

Education: University of Michigan-FlintB.S in Computer ScienceGraduation: December 2026
Skills:
-Arduino
-Arduino IDE
-C++
-Code::Blocks
-Data Structures
-Algorithms
-Algorithm Analysis
-Algorithm Optimization
-Dynamic Programming
-Python (Programming Language)
-HTML
-Computer Science
-Database Design
-Database Management System (DBMS)
-Java
-Databases
-JavaScript
-Tech-savvy
-Microsoft Office
-Visual Basic .NET (VB.NET)
-Visual Basic
-Visual Studio
-Computer Literacy

### Section 3: Projects

Notable Projects in progress: "AIGentFlow" for Technology Capstone (CIT 485), "Fly Simply" for Human-Computer Interaction (CSC 310)
"AIGentFlow" description: Website which allows users to configure agents to simulate a team environment. They can watch them work together and provide tasks through a chat window."Fly Simply" description: Application which allows users to navigate airports. It displays the travel time to specific areas within the airport (gates, security checkpoints, and other establishments). It will also display wait times at areas such as security checkpoints.

Again, do not modify index.html; instead, give suggestions.

**The AI responded, including suggestions:**

I will not modify `index.html`. I also cannot inspect the live GitHub repository because a Web Search or GitHub connector is not available in this conversation. The suggestions below are therefore based on your requirements and supplied content rather than a direct inspection of the current markup.

### Suggested changes to `index.html`

#### 1. Landing/About section

Replace the template identity and biography with:

```html
<h1>Fern Lawson</h1>
<p>Computer Science student at the University of Michigan-Flint</p>

<h2>About Me</h2>
<p>
  I am a Computer Science student currently looking for opportunities in
  software development, UI/UX design, and IT. I have four years of experience
  programming in Java and two years of experience programming in C++.
</p>
```

Recommendations:

- Use **Fern Lawson** as the page’s only `<h1>`.
- Display the student/institution line near the name so the landing page meets the acceptance criterion immediately.
- Use “two” instead of “2” in prose for consistency.
- Do not repeat the biography in the Education, résumé, or footer sections.
- Remove template occupation labels that are not supported by the supplied information.

#### 2. Education and Skills section

Keep education and skills within one top-level section, but place them in separate subsections or cards:

```html
<section id="education-skills" aria-labelledby="education-skills-heading">
  <h2 id="education-skills-heading">Education and Skills</h2>

  <article>
    <h3>Education</h3>
    <p><strong>University of Michigan-Flint</strong></p>
    <p>B.S. in Computer Science</p>
    <p>Expected graduation: December 2026</p>
  </article>

  <article>
    <h3>Skills</h3>
    <ul class="skills-list">
      <!-- Skills here -->
    </ul>
  </article>
</section>
```

Use “Expected graduation” because December 2026 is in the future.

#### Suggested skill organization

The supplied list is easier to scan when grouped without duplicating individual skills:

**Programming languages**

- C++
- HTML
- Java
- JavaScript
- Python
- Visual Basic
- Visual Basic .NET (VB.NET)

**Computer science concepts**

- Algorithms
- Algorithm Analysis
- Algorithm Optimization
- Computer Science
- Data Structures
- Dynamic Programming

**Databases**

- Database Design
- Database Management Systems (DBMS)
- Databases

**Tools and platforms**

- Arduino
- Arduino IDE
- Code::Blocks
- Microsoft Office
- Visual Studio

**General technology skills**

- Computer Literacy
- Tech-savvy

Preserve all supplied skills, but consider whether these overlapping entries are intentional:

- “Databases,” “Database Design,” and “Database Management Systems”
- “Visual Basic” and “Visual Basic .NET”
- “Algorithms,” “Algorithm Analysis,” and “Algorithm Optimization”
- “Arduino” and “Arduino IDE”
- “Computer Literacy” and “Tech-savvy”

They are not exact duplicates, so they can remain. Grouping them prevents the section from looking repetitive.

#### 3. Projects section

Rename the template’s Portfolio section to **Projects** and replace image-based portfolio cards with text cards.

```html
<section id="projects" aria-labelledby="projects-heading">
  <h2 id="projects-heading">Projects</h2>
  <p>Notable projects in progress</p>

  <div class="projects-grid">
    <article class="project-card">
      <h3>AIGentFlow</h3>
      <p class="project-context">Technology Capstone (CIT 485) · In progress</p>
      <p>
        A website that allows users to configure agents to simulate a team
        environment. Users can watch the agents work together and provide tasks
        through a chat window.
      </p>
    </article>

    <article class="project-card">
      <h3>Fly Simply</h3>
      <p class="project-context">
        Human-Computer Interaction (CSC 310) · In progress
      </p>
      <p>
        An application that helps users navigate airports. It displays travel
        times to gates, security checkpoints, and other establishments, as well
        as wait times at areas such as security checkpoints.
      </p>
    </article>
  </div>
</section>
```

Recommendations:

- Do not add project links because none were provided.
- Do not invent technologies used for either project.
- Do not use empty anchors, “View project” buttons, or dummy URLs.
- Mark both projects clearly as **in progress**.
- If the template depends on portfolio filter buttons, remove those buttons and their associated JavaScript unless they still serve a real purpose.

#### 4. Testimonials section

You requested removal of its images, but the supplied information contains no testimonial content. The cleanest solution is to remove the entire Testimonials section, not merely its images.

Also remove:

- The Testimonials navigation link
- Avatar markup
- Testimonial modal markup
- Testimonial-specific JavaScript
- Unused testimonial styles, if safely separable

This prevents placeholder quotations, names, and job titles from remaining and avoids creating a content-poor section.

#### 5. Clients section

Remove the entire Clients section because no clients were supplied. Removing only the logos would leave an empty or misleading section.

Also remove:

- Client-logo links and images
- The Clients navigation link, if present
- Client-specific unused styles

Do not imply that employers, organizations, or courses are clients.

#### 6. Blog section

Remove the entire Blog section because no blog posts or approved links were supplied.

Also remove:

- Blog thumbnails
- Placeholder post titles, dates, categories, and excerpts
- The Blog navigation link
- Blog-specific scripts and styles when safely removable

An empty text-only Blog section would not satisfy the requirement that every section have distinct, completed information.

#### 7. Navigation

The final navigation should point only to sections that remain, likely:

- About
- Education and Skills
- Projects

If the template has a separate résumé section that duplicates Education and Skills, either:

- Convert that section into the sole Education and Skills section, or
- Remove it.

Do not keep both a résumé summary and an Education and Skills section containing the same information.

Example:

```html
<nav aria-label="Primary navigation">
  <ul>
    <li><a href="#about">About</a></li>
    <li><a href="#education-skills">Education and Skills</a></li>
    <li><a href="#projects">Projects</a></li>
  </ul>
</nav>
```

#### 8. Contact and social links

No public contact methods or profile links were supplied. Therefore:

- Remove template phone numbers, email addresses, locations, social accounts, and résumé links.
- Do not use `example.com`, `#`, or empty `href` values.
- Remove the Contact section if it cannot be completed with approved information.
- Do not expose Fern’s U-M uniqname or infer an email address from it.

### Suggested styling changes

Use existing template classes where practical, but make project cards work without images:

```css
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 18rem), 1fr));
  gap: 1rem;
}

.project-card {
  padding: 1.25rem;
  border: 1px solid currentColor;
  border-radius: 0.75rem;
}

.project-card h3 {
  margin-block-start: 0;
}

.project-context {
  font-weight: 600;
}

.skills-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  padding: 0;
  list-style: none;
}

@media (max-width: 480px) {
  .project-card {
    padding: 1rem;
  }
}

:focus-visible {
  outline: 3px solid currentColor;
  outline-offset: 3px;
}
```

Additional checks:

- Do not rely on hover alone to expose project information.
- Ensure cards do not have fake link behavior if they are not clickable.
- Retain visible focus styles on all actual controls.
- Check foreground/background combinations for Web Content Accessibility Guidelines (WCAG) 2.1 Level AA contrast.
- Avoid fixed card heights, which can clip content on mobile or at 200% zoom.

### GitHub Pages considerations

- Use relative asset paths such as `./assets/css/style.css`, not root-relative paths such as `/assets/css/style.css`, unless the deployment configuration specifically supports them.
- Match filename capitalization exactly; GitHub Pages is case-sensitive.
- Ensure the entry file remains named `index.html`.
- Remove references to deleted image assets from HTML, CSS, metadata, and JavaScript.
- Keep any template license file and required attribution.
- Check `og:image`, favicon, and manifest references for placeholder images.
- If deleted sections are targets of URL fragments, remove or update those links.

### Proposed final section structure

1. **About**
   - Fern Lawson
   - Computer Science student at the University of Michigan-Flint
   - Supplied About Me paragraph
2. **Education and Skills**
   - University of Michigan-Flint
   - B.S. in Computer Science
   - Expected graduation: December 2026
   - Supplied skills, grouped for readability
3. **Projects**
   - AIGentFlow
   - Fly Simply

Testimonials, Clients, and Blog should be removed completely. Portfolio should be transformed into Projects rather than retained as a separate duplicate section.

These are suggestions only; no repository files have been modified.
