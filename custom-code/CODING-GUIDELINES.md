Combeenation AI Coding Guidelines
Applies to AI-assisted changes in Combeenation Custom Code projects.

Priority: Customer specifications and rule spreadsheets take precedence. Then follow existing project conventions and enforced tooling. If a requirement conflicts with these guidelines, follow the higher-priority source and report the conflict.

Communication and scope
- Write code and code comments in English. Never use em or en dashes in any text, including chat, documentation, commits and comments. Use commas, colons, parentheses or separate sentences instead.
- Report changes, relevant findings and open questions concisely. Do not narrate investigation steps.
- Ask when a requirement is materially unclear. When a decision is needed, recommend one approach.
- Make narrowly scoped changes. Prefer simple solutions over speculative fixes, unnecessary abstractions, excessive edge-case handling or redundant safety checks.

Structure and naming
- Group files by domain (3d/, 2d/, checkout/, misc/, typings/). Use kebab-case filenames with a domain prefix and, where applicable, a role suffix (mgr, utils, helper, service). Domain prefixes may also appear inside domain folders.
- Place exported entry functions first, followed by internal helpers in call order. Separate private helpers with // PRIVATE FUNCTIONS between two // ----------------- lines. Use uppercase section labels in longer files or classes.
- Use module-specific initialization functions such as initViewerMgr(). Compose initialization in index.ts inside CfgrUtils.onCfgrReady(async () => { ... }) when the project uses a central entry point. await modules in dependency order. Not every initializer must live in index.ts.
- Keep shared identifiers (for example CtrlNames, node and tag names) in constants.ts. Keep typings/cfgr-defs.generated.ts generated. Never edit .generated.ts manually; create missing controls or columns in Combeenation and regenerate.
- Include units in variable names (widthMM, depthM) and centralize unit conversion.
- Split oversized files by responsibility. Avoid unnecessary module-level state and constants.

TypeScript
- Use named function declarations at module level and export function for public entry points. No exported arrow functions or export default. Local callbacks may be arrows.
- Prefer async/await over .then() chains. Do not add unnecessary type arguments such as <void> to calls.
- Use string enums for fixed identifiers instead of repeated literals, for example export enum CtrlNames { JS_Viewer3d = 'JS_Viewer3d' }.
- Name constants UPPER_SNAKE_CASE, prefix private module constants with _, and define them only when useful. If shared mutable module state is required, use export let UPPER_SNAKE_CASE; only its owning module may assign it.
- Prefer type; use interface with an I prefix for structured data contracts. Declare function return types only when they add clarity or are required.
- In classes, declare public/private explicitly. Use a static async create(...) factory when construction needs asynchronous setup.
- Prefer early returns, ?. and ?? over deep nesting. Use non-null ! only for guaranteed values. Avoid defensive checks without a realistic failure case.
- Do not use any or @ts-ignore. Restrict eslint-disable to justified, local cases. Do not invoke functions through a ternary; use if/else.
- Handle recoverable errors where they occur, using contextual console.warn or console.error (IDs, values). Keep the configurator usable when possible. Avoid broad or nested try/catch blocks.
- Do not add function descriptions or JSDoc function summaries.
- Use comments sparingly and only where needed to understand the code or its reasoning. Use // TODO:, // NOTE: and // WORKAROUND: consistently where applicable.
- Use blank lines and spacing according to context to separate logical steps, conditionals and comment blocks. Keep closely related statements together and follow the project's formatter.

Translations and project data
- Never hardcode user-facing UI text. Return or reference translation keys instead. Keys must be at most 30 characters and must not start with a digit.
- Supply translations for new keys (KEY,DE,EN,...). Update the project's existing translation Excel file when present; otherwise create a separate CSV/TSV translation file.
- Keep product data and translation sources in the project and edit existing files directly. Do not invent a new folder structure unless it is needed.

CSS and UI
- Reuse existing styles and CSS variables. Prefer CSS nesting for related selectors. Provide hover and active states with transitions. Do not invent new CSS variables.
- Keep custom CSS in the Custom Code project, preferably in a dedicated CSS file (custom-ui.css). Where supported by the project, import with ?inline and apply through CSSStyleSheet and document.adoptedStyleSheets in the index.ts file.
- Use existing platform icons (stored in css variables), rendered with CSS mask instead of background-image URLs or SVG filters. If an icon is missing, propose a variable name and ask for it to be created in Combeenation. Do not invent icon assets.
- Show a loader on the affected button for longer actions. Avoid a full-screen loading mask unless the entire UI is blocked.
