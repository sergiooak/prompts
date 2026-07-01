# Coding Prompts

Reusable prompts for GitHub Copilot, Cursor, and Claude Code. One line per prompt, grouped by category. See [`AGENTS.md`](../../AGENTS.md) for the philosophy and how to contribute.

> Note: a few prompts below (Angular/RxJS/Nebular) are stack-specific and will move to their own file (e.g. `topics/coding/angular.md`) once that section grows enough to justify it.

## Code Readability & Legibility

📖 Make code more legible by refactoring and adding strategic comments only for complex logic
🔧 Refactor code to enhance clarity, consistency, and readability, following the styleguide and modern best practices
🔤 Rename variables, functions, and classes with concise, meaningful names that reflect their purpose
📐 Replace generic HTML tags (like div) with semantic elements (main, section, nav, etc.) where it meaningfully improves document structure and accessibility
🔵 Add types to this code. Add separate interfaces when possible. Do not change the code except for adding types

## Styling & Accessibility

🎯 Simplify CSS by removing unnecessary utility or wrapper classes, favoring semantic selectors and styles that map clearly to meaningful HTML structure
🌙 Ensure consistent application of Tailwind CSS dark mode
♿ Add ARIA roles, labels, and keyboard navigation enhancements to interactive elements for improved accessibility
🏷️ Implement IDs and data attributes (e.g., data-component, data-part) for easier component identification in DevTools
🌍 Extract hardcoded text and improve translations/localizations, avoid overly nested keys

## Code Cleanup & Documentation

🧹 Eliminate dead code, redundant comments, and unnecessary whitespace to keep the codebase clean
📚 Write clear JSDoc/TSDoc annotations with practical examples — focus on intent and behavior, not just types
🏷️ Add a file header documenting the module's purpose, key dependencies, and usage patterns
⚠️ Flag technical debt with TECH_DEBT comments; include context on why refactoring is needed and suggested approach
🗓️ Document future improvements in a ROADMAP section; link to related issues or feature requests where applicable

## Debugging

🐛 Add strategic console logging statements to aid in debugging complex issues
💭 Insert extremely detailed inline comments explaining code logic and flow
📉 Reduce line count while preserving functionality to simplify maintenance
🔍 Add breakpoint-friendly logging for RxJS observables (tap operator) to trace data flow through pipelines
⚡ Add performance timing logs to identify slow operations and bottlenecks in component lifecycle and service methods

## Testing

🔍 Write comprehensive unit tests covering normal operations, edge cases, and error scenarios
✅ Add test cases with realistic mock data to ensure robust validation and error handling

## Error Handling & Edge Cases

🕵️‍♂️ Scan for null/undefined reference errors; add guard clauses and optional chaining (?.) to prevent runtime crashes
⚠️ Identify missing type checks on API responses before accessing nested properties (e.g., `response?.data?.items?.[0]?.id`)
🛡️ Audit array operations for out-of-bounds access; add length checks before indexing or use safe array methods (`.at()`, `.find()`)
🔍 Check for unhandled Promise rejections and missing `.catch()` blocks on async operations
💥 Detect potential division-by-zero, null iteration, and type coercion bugs in calculations and loops

## Validation & Input Sanitization

✔️ Validate form inputs before submission: check required fields, format constraints, and value ranges; show field-level error messages
🔐 Sanitize user input to prevent XSS attacks; use Angular's `DomSanitizer` for HTML content, escape strings in templates with `{{}}` interpolation
📏 Enforce API contract validation: check response schema matches expected types, reject malformed or missing required fields
🧮 Add bounds checking on numeric inputs (min/max), string length limits, and enum validation before sending to the backend
⛔ Reject requests with obviously invalid data (empty strings when required, negative counts, future dates for past events)

## Code Modularity & Performance

🛠️ Break down large functions into smaller, single-responsibility functions (avoid creating new files unnecessarily)
📦 Modularize monolithic files into smaller components or services for better maintainability
🔄 Create shared utility functions to reduce code duplication across the codebase
⏩ Replace array.filter().map() chains with single reduce operations to streamline data processing
⏩ Enhance performance and reduce complexity by refactoring inefficient code patterns

## Version Control & Git Workflow

📝 Review all code changes, organize files by feature/topic, generate clear commit messages following conventional commit standards, and prepare commits for review
🌿 Suggest a descriptive branch name following the pattern `<type>/<description>` based on the changes in pt-BR
🔀 Generate a pull request title and detailed description with motivation, changes made in pt-BR

## Modern JavaScript & Framework Specific

⚙️ Utilize modern JavaScript features (destructuring, optional chaining, etc.) for cleaner, more efficient code
📅 Use locale-aware libraries for dates and numbers (e.g., Intl.DateTimeFormat) for accurate formatting
🧹 Ensure event handlers and subscriptions are properly cleaned up during component unmounting
🎹 Improve keyboard navigation and overall accessibility for interactive components
🚦 Support user preferences for reduced motion in animations and transitions

## Security & Maintenance

🔐 Implement security best practices to safeguard against vulnerabilities (e.g., XSS, injections)
📊 Add input validation and data sanitization to prevent processing of malicious data
📱 Make components fully responsive across all screen sizes, ensuring a consistent UX on every device
🎨 Improve visual hierarchy and styling consistency throughout the application
📦 Suggest package alternatives or updates for better performance and long-term maintainability

## Advanced/Niche Prompts

🤖 Explore alternative algorithms or design patterns to simplify complex logic
💡 Propose architectural changes that support scalability and long-term maintainability
🛡️ Review third-party dependencies for potential security or performance issues and suggest improvements
🧪 Generate end-to-end tests that simulate realistic user interactions and workflows

## Angular & RxJS

🔁 Replace imperative subscriptions with async pipe and reactive patterns to eliminate manual subscribe/unsubscribe boilerplate
🚿 Audit all component subscriptions for missing unsubscribe or takeUntil — add cleanup to prevent memory leaks
📡 Refactor service methods to use shareReplay(1) where multiple consumers request the same data to avoid duplicate HTTP calls
🧵 Replace nested subscribe() calls with switchMap, mergeMap, or forkJoin for cleaner async composition
⏸️ Use debounceTime and distinctUntilChanged on form inputs and search streams to reduce excessive HTTP calls and improve responsiveness

## Performance

🦥 Implement trackBy functions in all *ngFor loops to prevent unnecessary DOM re-renders
⚡ Audit @Input() bound objects — replace full-object bindings with primitive values where possible to reduce change detection cycles
🎯 Leverage OnPush change detection strategy in presentational components to minimize change detection runs across the component tree
📦 Defer heavy computations with async pipes and observables; avoid synchronous data transformations in templates
🔍 Profile component render times with Angular DevTools and identify bottlenecks; optimize or memoize expensive getters and methods

## Code Quality

🏗️ Extract repeated localStorage.getItem('NomePerfil') branching into a single UserProfileService method to centralize profile logic
🧩 Replace magic strings (route paths, localStorage keys, API segments) with named constants or enums
🔍 Audit all HTTP error handling — ensure 401/403 responses trigger auth guard redirect, 4xx show user-friendly toasts, and 5xx include retry logic
📋 Review all feature modules for unused imports, dead code, and circular dependencies; verify lazy-load boundaries match the routing structure
🎭 Consolidate duplicate table column configurations (filters, sorting, pagination) into shared reusable SmartTableConfig utilities to reduce maintenance burden

## UX / UI

⏳ Add skeleton loading states or spinners (NbSpinnerModule) to data-heavy pages while API calls are in flight
📭 Add empty-state messages to tables and lists when the API returns zero results
🔔 Add toast notifications (NbToastrService) for user feedback on successful saves, deletions, and error scenarios
⚙️ Add confirmation dialogs (NbDialogService) before destructive actions (delete, cancel, clear form) to prevent accidental data loss

## SEO & Meta

🔍 Add descriptive <title> and <meta name="description"> tags to every route using Angular's Title and Meta services
🏷️ Implement Open Graph and Twitter Card meta tags (og:title, og:description, og:image, twitter:card) on all public-facing pages
🔗 Add canonical <link rel="canonical"> tags to prevent duplicate content issues across parameterized or paginated routes
🤖 Add or audit robots.txt to control crawler access — disallow private/auth routes, allow all public content
📐 Enforce a single H1 per page and ensure heading hierarchy (H1 → H2 → H3) is semantically correct across all views
📊 Add structured data (JSON-LD) for key entity types (Organization, BreadcrumbList, WebPage) to improve rich-result eligibility
📱 Audit mobile usability: tap target sizes, font sizes, and viewport meta tag to pass Google's mobile-friendly test

## Miscellaneous

💬 Format output as a WhatsApp message for easy readability and searchability, using WhatsApp markdown and relevant emojis
🎓 Explain the code in simple terms — break down complex concepts into beginner-friendly language with real-world analogies
🔗 Suggest relevant documentation links, Stack Overflow threads, or MDN resources that complement the current code or pattern
