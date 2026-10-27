# Combeenation Coding Guidelines

The company-wide coding guidelines are maintained at:

https://github.com/Combeenation/ai-guidelines/blob/master/custom-code/CODING-GUIDELINES.md

Before creating, modifying, debugging, refactoring, or reviewing code:

1. Retrieve and read the current company guidelines from the URL above using the available tools.
2. Apply them alongside the project's existing architecture, conventions, and enforced linting and formatting rules.
3. Explicitly report any conflicts between the company guidelines and project-specific requirements.
4. If the guidelines cannot be retrieved, report this before making code changes. Do not claim to have followed guidelines that were not read.

Personal instructions and AI memory may supplement the guidelines but do not replace them.

## Project Description

Before every task involving project code:

1. Check for `.ai/project/project.md` in the current repository and read it if it exists.
2. Use the project description only as supporting context. The existing codebase is the source of truth for the current implementation. Customer requirements, actual project conventions, and enforced tooling take precedence over the project description. Report discrepancies; never change working code solely to match outdated documentation.
3. If `.ai/project/project.md` is missing, **invoke and execute** the [update-project-description skill](https://github.com/Combeenation/skills/blob/master/skills/update-project-description/SKILL.md) to propose its creation based on verified repository facts. Do not create it independently or invent project information. Follow the skill's review and approval process before writing the file.
4. If the file exists but cannot be read, report the issue. Do not guess its contents.

After substantial changes to the project's features, architecture, integrations, data models, business rules, dependencies, or conventions, **invoke and execute** the [update-project-description skill](https://github.com/Combeenation/skills/blob/master/skills/update-project-description/SKILL.md) to review the documentation and propose updates. Apply documentation changes only after user confirmation, as required by the skill.

Minor changes that do not affect the project description do not require the skill, unless `.ai/project/project.md` is missing or the user explicitly requests a documentation update.

If the skill cannot be retrieved or executed when required, report this explicitly. Do not claim it was run.
