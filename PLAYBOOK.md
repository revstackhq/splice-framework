# The Flux Framework: Context-Driven Engineering for the AI Era

**Version:** 1.0.0
**Core Premise:** Syntax is no longer the bottleneck; context transfer is. Scrum was built to manage human typing speed. Flux is built to orchestrate AI generation.

In the AI era, measuring developer productivity in "Story Points" or "Two-Week Sprints" is an anchor. Developers should not type boilerplate; they should stitch components, audit architecture, and guide AI models using perfect contextual documentation.

---

## 1. The Core Roles

We abandon the traditional hierarchy of typing speed (Junior, Mid, Senior). Instead, roles are defined by their responsibility in the context pipeline.

### Context Architect (Design)

- **Previously:** Product Manager / Tech Lead
- **Responsibility:** Owns the business rules, constraints, and the system prompts.
- **Action:** Never writes syntax. Writes `[domain]-context.md` files detailing exact database schemas, UI constraints, and architectural patterns. If the AI hallucinates, it is the Architect's fault for providing an ambiguous prompt.

### AI Orchestrator (Execution)

- **Previously:** Junior / Mid-Level Developer
- **Responsibility:** The pilot of the IDE (Cursor, Copilot, Claude Code).
- **Action:** Feeds the Context Blocks to the AI. Stitches the generated components together, checks local compilation, and reprompts the AI when syntax errors occur. They orchestrate the generation, they do not type from scratch.

### Logic Auditor (Review)

- **Previously:** Senior Engineer / QA
- **Responsibility:** Owns security, scale, and edge cases.
- **Action:** Reviews Pull Requests strictly for architectural flaws, data sanitization, and business logic. Completely ignores syntax formatting (handled by linters/formatters).

---

## 2. The Context Assembly Pipeline

A feature is never started by opening an empty code file. It starts with Context Assembly.

**Phase 0: Research (Optional)**
For highly ambiguous features. Fragmented ideas (interviews, technical feasibility) converge into a single `master-research.md` document to lower the ambiguity score.

**Phase 1: Distributed Context Drafting**
Domain experts work asynchronously in a feature folder (e.g., `docs/features/SOC-12/`):

- `ui-context.md`: Frontend constraints, component libraries (e.g., shadcn/ui), states.
- `db-context.md`: Database schemas (e.g., Drizzle/Prisma), relations, indexes.
- `infra-context.md`: Deployment targets (e.g., Vercel Edge, AWS S3).
- `qa-context.md`: Critical edge cases and integration test requirements.

**Phase 2: Consolidation**
The Context Architect uses an LLM to merge these domain files into a single `master-prompt.md`, resolving any contradictions before a single line of code is written.

**Phase 3: The Vibe (Generation)**
The AI Orchestrator feeds the `master-prompt.md` into the IDE. The AI generates the code. The Orchestrator stitches and verifies.

**Phase 4: Logic Audit**
The PR is opened. The Logic Auditor reviews for security and business constraints. Merged to production.

---

## 3. The Linear (or Issue Tracker) Setup

Ditch time-based estimation. We measure **Context Ambiguity**.

**The Workflow States:**

1. `Drafting Context`: Experts are writing their `.md` files. Code is strictly forbidden.
2. `Ready for Vibe`: The `master-prompt.md` is approved. Ambiguity is low.
3. `Generating`: The Orchestrator is in the IDE, stitching the AI output.
4. `Logic Audit`: PR is open. Senior is reviewing business logic.
5. `Live`: Deployed to production.

**Ambiguity Scoring (Replaces Story Points):**

- **1 Point (Low):** Perfect context. DB schemas and UI are defined. Generation takes minutes.
- **3 Points (Medium):** Minor missing edge cases. Orchestrator will need to re-prompt a few times.
- **5 Points (High):** Unclear business rules. Sent back to Phase 0 (Research).

---

## 4. Real-World Example: "Create a Post"

_Old Way:_ 3 Jira tickets (Backend, Frontend, QA), 2 weeks, multiple sync meetings.
_The Flux Way:_

1. **Drafting:** Architect pastes the Drizzle schema and UI rules into a Markdown file. Scored as Low Ambiguity (1 Point).
2. **Generating:** AI Orchestrator uses Cursor, references `@create-post-context.md`, and asks the AI to generate the Server Action and React Modal. Takes 45 minutes.
3. **Logic Audit:** Senior Engineer reviews the PR, realizes the Orchestrator's prompt missed file sanitization for S3. The Senior reprompts the AI in the PR branch to add Zod validation.
4. **Live:** Feature ships. Total time: 2 hours.

---

## 5. Zero-Friction Onboarding & Junior Acceleration

**Day 1 to Production in 48 Hours.**
New hires do not read dead wikis. They read the `.cursorrules` and `.clauderules` files—the executable DNA of the codebase.

**The 20x Junior Acceleration:**
In the Old Way, Juniors spent weeks fighting basic syntax, typos, and build tools to create a simple CRUD app.
In the Flux Way, the AI generates the syntax instantly. The Junior spends their time **reading** advanced, modular code and receiving architectural corrections from Seniors during the Logic Audit. They learn software design, system architecture, and prompt engineering from day one. They don't learn how to type; they learn how to build.

---

_Stop managing syntax. Start orchestrating context._
