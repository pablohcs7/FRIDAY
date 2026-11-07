# Agent Instructions

## Project context

FRIDAY is a standalone AI skills kit. Its current deliverable is the repository's documentary foundation. Read `README.md`, `docs/research/SOURCES.md`, `docs/plans/EXECUTION-STATE.md`, and the relevant task plan before implementation. Use the repository as the durable source of progress.

The `skills/` and `installer/` directories currently contain purpose documents only. Do not claim that skills, commands, dependencies, a CLI, CI, or installation workflows exist before they are implemented and verified.

## Confirmed direction

- Preserve the product discovery and bootstrap intent of vibe-coding-toolkit and the SDD workflow of agents-instructions. Record source revisions, adaptations, attribution, and applicable notices when incorporating upstream content.
- Build separate skills for Codex and Claude Code with an independent core and conditional technical profiles. Keep instructions concise and load supporting references only when relevant.
- Preserve the Colibri HIL concept: triage, product, technical solution and execution, exceptions, qualifications, visual verification when applicable, and final acceptance. Additional concept/design gates apply to the selected workflow level. Retain valid prior authorization for unchanged scope.
- Preserve completed specifications, task plans, decisions, and evidence in version control. Runtime behavior is established by code, tests, and current durable documentation, not by old plans. Do not require Jira.
- Reuse a consuming project's architecture, UI, components, and conventions. For a web project without a UI component base, prefer Mantine with styled-components. Use React Hook Form with Zod and `@hookform/resolvers`; do not add `@mantine/form` by default.
- Keep Mantine's theme and Styles API responsible for its internal styling where appropriate. Use styled-components for layouts and custom components, with shared tokens and documented portal limitations. Do not require Tailwind or shadcn/ui by default.
- When final visual guidance is absent, create only the components needed for the current work with a coherent provisional appearance and complete interaction states. Record that the visual design is provisional.
- Keep Expo/React Native and native Kotlin/Android as separate mobile profiles. Web UI libraries do not imply native component reuse.
- The future installer manages skills and diagnoses prerequisites on Windows, macOS, and Linux. It must preserve manual files and client settings; installing machine tools or project libraries is not its default responsibility.

## Language and documentation

- Write narrative documentation in Brazilian Portuguese. Keep `AGENTS.md` and `docs/plans/EXECUTION-STATE.md` in English.
- Use English for code, identifiers, filenames, and technical terminology. Use strict TypeScript when executable TypeScript is introduced.
- Keep the README informal, direct, and inspired by a developer's workshop. Keep technical documents concise and precise.
- Separate observed facts, approved decisions, proposals, and unverified integrations. Do not invent installation commands, validation evidence, or source authority.
- The acronym expansion is associated with the Avengers Campus variant. The year 1719 refers to Daniel Defoe's novel, not to the later English idioms. Preserve these distinctions.

## Task execution

- Before substantive implementation, create or resume a persistent task plan based on `docs/plans/TASK-TEMPLATE.md` under `docs/plans/active/`.
- Work within the approved task. Resolve routine local details independently; bring material product, architecture, security, data, public-contract, infrastructure, or scope changes to HIL with concrete evidence and a proposal.
- Validate the actual deliverable, review every change, and record checks and limitations. A documentary change does not require speculative application tests or new dependencies.
- Move successful task plans to `docs/plans/completed/` and update `docs/plans/EXECUTION-STATE.md`. Preserve blocked work and identify the specific missing decision or evidence.
- Creating a local repository does not imply publication. Follow the authorization recorded for the task for commits, remotes, push, releases, external configuration, and paid services.
