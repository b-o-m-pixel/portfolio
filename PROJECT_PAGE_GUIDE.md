# Project Page Creation Guide

## 1. Purpose and Scope
This guide documents the established conventions for creating standalone project detail pages in the engineering portfolio. As the portfolio relies on vanilla static HTML and CSS without a build system or templating engine, following these conventions ensures a consistent visual identity, reliable responsive behavior, and robust accessibility across all project pages.

## 2. Page Structure
Each project page is a standalone `.html` file located in the `projects/` directory.

### Current Implementation Pattern
The current architecture relies on a pattern of duplicating global elements (the `<header>`, the `<footer>`, and the inline theme `<script>`). You do not need to reproduce every global element byte-for-byte in the future if the site architecture evolves, but you must ensure the functional structure (navigation, theme toggling, and semantic landmarks) remains intact.

### Core Layout
*   **Head:** Contains the theme-initialization script, fonts, and a relative link to `../styles.css`.
*   **Hero Section (`.project-page-hero`):** Contains a back link (`.back-link`), the project metadata (`.project-meta-strip`), the page heading (`.heading-page`), and a summary paragraph (`.lead-paragraph`).
*   **Detail Grid (`.project-detail-grid`):** A two-column responsive layout utilizing an `<aside>` for metadata and a `.project-detail-content` container for the narrative.

### Section Flexibility
Maintain a consistent heading hierarchy, but allow narrative sections (e.g., Problem & Objective, Scope, Architecture, Implementation, Results) to be flexible. You may omit sections entirely if they are not relevant to a specific project, or mark them as pending if the project is planned or incomplete. Avoid padding the page with redundant or empty mandatory sections.

## 3. Project Status and Evidence Rules
Project content must strictly align with the project's actual lifecycle state. Do not invent details.

*   **Completed:** Document work actually performed. Include explicit implementation details and results *only* if they are supported by concrete evidence (e.g., a notebook, repository, or verifiable metric).
*   **In Progress:** Clearly distinguish between built components and unfinished work. Do not extrapolate incomplete results.
*   **Planned:** Describe intended goals, proposed architecture, and expected tech stack without implying implementation.
*   **Pending Verification:** When a necessary section lacks confirmed facts, use the `.placeholder-callout` class:

```html
<div class="placeholder-callout">
  <span class="placeholder-callout-tag">Pending Review</span>
  <p>Content awaiting verification...</p>
</div>
