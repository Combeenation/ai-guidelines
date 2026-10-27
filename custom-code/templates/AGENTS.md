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

1. Read `.ai/project/project.md` from the current repository.
2. Use it as project context alongside the central coding guidelines, customer requirements, existing code, and enforced tooling.
3. If the file is missing, inaccessible, or inconsistent with the code, explicitly report the issue. Do not invent missing project information.

After substantial changes that affect the project's features, architecture, integrations, data models, business rules, dependencies, or conventions:

1. Retrieve and follow the [update-project-description skill](https://github.com/Combeenation/skills/blob/master/skills/update-project-description/SKILL.md).
2. If the skill cannot be retrieved or executed, report this explicitly. Do not claim it was run.

Minor changes that do not affect the project description do not require running the skill.