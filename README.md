# Vibe Coding, the Right Way

### A Student's Practical Handbook for Building Real Software with AI

> **The goal is not to make AI write more code. The goal is to become
> the person who can guide, understand, test, debug, and improve the
> software AI helps create.**

Welcome! This guide is designed for students who want to learn
**real-world vibe coding** with Claude or another AI coding assistant.
It assumes you may be a beginner, but it does not encourage you to
remain dependent on AI.

Vibe coding can make building software feel dramatically faster. It can
also produce confusing code, hidden bugs, security problems, and
projects that work only on the developer's machine. This handbook gives
you a repeatable process for avoiding those traps.

------------------------------------------------------------------------

## Table of Contents

1.  [What Vibe Coding Actually
    Means](#1-what-vibe-coding-actually-means)
2.  [The Student's Mindset](#2-the-students-mindset)
3.  [The Complete Development Loop](#3-the-complete-development-loop)
4.  [Phase 1 --- Understand the
    Problem](#4-phase-1--understand-the-problem)
5.  [Phase 2 --- Plan Before Coding](#5-phase-2--plan-before-coding)
6.  [Phase 3 --- Understand the Existing
    Project](#6-phase-3--understand-the-existing-project)
7.  [Phase 4 --- Build in Small, Verifiable
    Steps](#7-phase-4--build-in-small-verifiable-steps)
8.  [Phase 5 --- Run, Test, and Verify](#8-phase-5--run-test-and-verify)
9.  [Phase 6 --- Debug Systematically](#9-phase-6--debug-systematically)
10. [Phase 7 --- Review and Understand the
    Code](#10-phase-7--review-and-understand-the-code)
11. [Phase 8 --- Git and GitHub
    Workflow](#11-phase-8--git-and-github-workflow)
12. [Phase 9 --- Security, Privacy, and
    Secrets](#12-phase-9--security-privacy-and-secrets)
13. [Phase 10 --- Finish and Document the
    Project](#13-phase-10--finish-and-document-the-project)
14. [How to Work with Claude](#14-how-to-work-with-claude)
15. [Prompt Templates](#15-prompt-templates)
16. [Common Beginner Traps](#16-common-beginner-traps)
17. [A Practical Project Checklist](#17-a-practical-project-checklist)
18. [A 30-Day Learning Roadmap](#18-a-30-day-learning-roadmap)
19. [Glossary](#19-glossary)

------------------------------------------------------------------------

## 1. What Vibe Coding Actually Means

Vibe coding is a way of building software by describing goals in natural
language and collaborating with an AI coding assistant that can help
plan, write, explain, test, and improve code.

A weak version looks like this:

1.  Ask AI to build an entire application.
2.  Copy the generated code.
3.  Run it without understanding it.
4.  See an error.
5.  Paste the error into AI.
6.  Repeat until something appears to work.
7.  Have no idea why it works or whether it is reliable.

That is **code generation without engineering control**.

A stronger version looks like this:

1.  Explain the problem and intended users.
2.  Ask AI to clarify missing requirements.
3.  Agree on a small, realistic first version.
4.  Inspect the project structure and choose an implementation plan.
5.  Build one small feature at a time.
6.  Run the application and verify each feature.
7.  Read the changes and ask why they were made.
8.  Test normal cases, edge cases, and failure cases.
9.  Review security, maintainability, and accessibility.
10. Commit working changes and document what was built.

The human remains responsible for the product and the decisions. AI is a
collaborator, not an authority.

### The central rule

**Never accept a change that you cannot explain at a basic level or
verify with a test.**

You do not need to understand every advanced framework detail on day
one. You should, however, understand what each important file does, what
a feature is supposed to do, how to run it, and how to tell whether it
works.

------------------------------------------------------------------------

## 2. The Student's Mindset

Your objective is to build two things at the same time:

-   **The project:** a useful application that solves a real problem.
-   **Your engineering ability:** the understanding to maintain, debug,
    and extend that application.

Use AI to accelerate learning, not to skip learning.

### The five responsibilities

  -----------------------------------------------------------------------
  Responsibility                      What you should do
  ----------------------------------- -----------------------------------
  Product thinker                     Explain who has the problem and
                                      what success means.

  Planner                             Break a large goal into small
                                      features and tasks.

  Technical decision-maker            Understand the proposed tools and
                                      trade-offs.

  Tester                              Verify behaviour instead of
                                      trusting confident explanations.

  Learner                             Ask AI to explain unfamiliar code
                                      and concepts.
  -----------------------------------------------------------------------

### Ask these questions regularly

-   What problem does this feature solve?
-   What happens from the user's click to the final result?
-   Which file is responsible for this behaviour?
-   What data enters this function, and what comes out?
-   What could go wrong?
-   How will I test that?
-   What did this change affect elsewhere?
-   Is there a simpler solution?

### The learning rule: explain it back

After a feature is implemented, close the code and explain it in your
own words:

1.  What does the feature do?
2.  Which files are involved?
3.  What is the flow of data?
4.  What important function or component controls it?
5.  What happens when something fails?
6.  How did you test it?

If you cannot explain it, ask Claude to teach the missing concept with a
small example. Then return to the project.

------------------------------------------------------------------------

## 3. The Complete Development Loop

Use this loop for every meaningful feature:

``` text
PROBLEM
   |
   v
REQUIREMENTS
   |
   v
PLAN + DESIGN
   |
   v
SMALL IMPLEMENTATION
   |
   v
RUN THE APPLICATION
   |
   v
TEST EXPECTED + EDGE CASES
   |
   v
REVIEW THE CODE
   |
   v
COMMIT THE WORK
   |
   +------> Next small feature
```

Do not treat the process as a one-way waterfall. Testing may reveal a
missing requirement. Code review may reveal that the plan is too
complicated. Return to the relevant step and improve it.

### The feature-sized loop

For each feature, define:

-   **Goal:** What should the user be able to do?
-   **Input:** What information does the feature receive?
-   **Output:** What should happen?
-   **Rules:** What must always be true?
-   **Failure cases:** What if input is missing, invalid, or
    unavailable?
-   **Test:** How will you verify the behaviour?

Example:

**Feature:** Add a task to a to-do list.

-   Goal: A user can create a task.
-   Input: Task title.
-   Output: The task appears in the list.
-   Rules: A title cannot be empty.
-   Failure cases: Whitespace-only title; unusually long title.
-   Test: Add a valid title, then try an empty title.

This is much more useful than simply telling AI, "Make a to-do app."

------------------------------------------------------------------------

## 4. Phase 1 --- Understand the Problem

Before asking AI to write code, write down the problem in ordinary
language.

### A simple problem brief

``` text
Project name:
Problem:
Who experiences this problem?
How do they solve it today?
Why is the current method inconvenient?
What should my application improve?
Who will use the first version?
What is outside the scope of the first version?
```

Do not invent complexity. A student project does not need to become a
large startup platform immediately.

### Define the MVP

MVP means **Minimum Viable Product**: the smallest useful version that
lets you test the core idea.

For a student attendance application:

**First version** - Add a student. - Mark attendance. - View attendance
records. - Calculate attendance percentage.

**Not required in the first version** - AI attendance predictions. -
Multiple institution dashboards. - Complex analytics. - Mobile
applications for every platform.

A small working product teaches more than a huge unfinished codebase.

### Define acceptance criteria

Acceptance criteria are observable conditions that tell you a feature is
complete.

Example:

``` text
Feature: Add a student

Acceptance criteria:
- A student can be added with a valid name and ID.
- The application rejects an empty name.
- The application rejects a duplicate student ID.
- A successful addition appears in the student list.
- Refreshing the page does not unexpectedly remove saved data
  if persistence is part of the agreed design.
```

Avoid vague criteria such as "It should work perfectly."

------------------------------------------------------------------------

## 5. Phase 2 --- Plan Before Coding

Ask Claude to create a plan before it edits files.

A good plan should include:

1.  User stories or feature list.
2.  Pages or screens.
3.  Data model.
4.  Main components or modules.
5.  Technology choices and reasons.
6.  Project folder structure.
7.  Implementation order.
8.  Risks and assumptions.
9.  How each feature will be tested.

### Choose technology for a reason

Do not select a framework just because AI suggested it.

Ask:

-   What problem does this tool solve?
-   Is it necessary for this project?
-   Is there a simpler option?
-   What will I need to learn to maintain it?
-   What are the deployment and hosting requirements?
-   What are the trade-offs?

For a simple static information website, plain HTML and CSS may be
enough. A database, authentication system, or frontend framework should
be introduced when the requirements justify it.

### Keep an architecture note

A lightweight architecture note can look like this:

``` text
Application
|
|-- User Interface
|    |-- Pages
|    |-- Reusable Components
|
|-- Application Logic
|    |-- Validation
|    |-- Feature Services
|
|-- Data Layer
     |-- Database or Local Storage
     |-- Data Access Functions
```

This is a conceptual example, not a mandatory folder structure. Let the
actual requirements determine the architecture.

------------------------------------------------------------------------

## 6. Phase 3 --- Understand the Existing Project

When working inside an existing repository, **inspect before editing**.

Ask Claude to:

-   List the important files and folders.
-   Identify the language, framework, and package manager.
-   Find the application entry point.
-   Explain how the application starts.
-   Identify existing features and conventions.
-   Check the README and configuration files.
-   Identify tests and how to run them.
-   Report uncertainty rather than guessing.

### Important files you may encounter

  File              Common purpose
  ----------------- --------------------------------------------------
  `README.md`       Project overview, setup, and usage instructions.
  `package.json`    JavaScript project scripts and dependencies.
  `src/`            Application source code in many projects.
  `public/`         Static assets in many web projects.
  `.gitignore`      Files Git should not track.
  `.env.example`    Example names of required environment variables.
  `tests/`          Automated tests, if the project has them.
  `tsconfig.json`   TypeScript compiler configuration.
  `vite.config.*`   Vite build-tool configuration, when used.

These are conventions, not universal rules. A project may use a
different structure.

### Do not let AI rewrite everything

If you ask for a small button change, the assistant should not
unnecessarily replace the entire application.

Prefer targeted changes. Ask Claude to explain why a broader change is
necessary before approving it.

------------------------------------------------------------------------

## 7. Phase 4 --- Build in Small, Verifiable Steps

The most important practical habit is to implement one coherent feature
at a time.

### Bad request

> Build my complete college management system with login, attendance,
> fees, reports, admin dashboard, database, and responsive design.

This request is too broad. It encourages the assistant to make many
assumptions and change many files at once.

### Better sequence

1.  Create the basic application shell.
2.  Run it and verify that it starts.
3.  Create the student list screen using sample data.
4.  Run it and verify the layout.
5.  Add the form to create a student.
6.  Validate the form.
7.  Add persistence.
8.  Test refresh and invalid input.
9.  Add attendance functionality.
10. Test calculations and edge cases.

Each step should leave the project in a known state.

### Use checkpoints

After every significant change:

-   Inspect the changed files.
-   Run the relevant command.
-   Check the visible behaviour.
-   Read the terminal output.
-   Run relevant tests.
-   Fix issues before adding another feature.

### Avoid unnecessary dependencies

Every dependency adds maintenance, compatibility, and security
considerations.

Before adding a package, ask Claude:

-   Why do we need it?
-   Can the built-in language or platform features do this?
-   Is the package actively maintained?
-   Is it compatible with the current project?
-   What does it add to the project?

------------------------------------------------------------------------

## 8. Phase 5 --- Run, Test, and Verify

A program starting without an error does **not** prove that it is
correct.

Testing checks whether the software behaves as expected.

### Four useful levels of testing

**1. Manual testing**

Use the application like a real user. Click buttons, fill forms,
navigate pages, refresh, and observe results.

**2. Unit testing**

Test a small function or unit in isolation.

Example: a function that calculates attendance percentage.

**3. Integration testing**

Test whether multiple parts work together, such as a form, validation
logic, and database operation.

**4. End-to-end testing**

Test a complete user journey through the application, such as signing in
and creating a record.

A beginner project does not need every testing tool immediately. Start
with manual checks and focused unit tests where useful.

### Test more than the happy path

For every feature, test:

  -----------------------------------------------------------------------
  Case                                Example
  ----------------------------------- -----------------------------------
  Normal input                        A valid student name.

  Empty input                         Submit without a name.

  Invalid input                       Enter an invalid ID.

  Boundary input                      Use the minimum or maximum allowed
                                      value.

  Duplicate input                     Add the same ID twice.

  Failure                             Simulate an unavailable network or
                                      database.

  Persistence                         Refresh and check saved
                                      information.

  Permissions                         Try an action as a user who should
                                      not be allowed to do it.
  -----------------------------------------------------------------------

### Write a test plan

``` text
Feature:
Expected behaviour:
Test steps:
Expected result:
Actual result:
Status: PASS / FAIL
Notes:
```

Never claim a test passed unless it was actually run and the result was
observed.

### Ask Claude to distinguish facts from assumptions

A useful instruction:

> Do not say that the application works merely because the code looks
> correct. Tell me exactly which commands you ran, which tests passed,
> which tests failed, and which behaviours remain unverified.

------------------------------------------------------------------------

## 9. Phase 6 --- Debug Systematically

Debugging is not repeatedly asking AI to "fix everything." It is the
process of finding the cause of an incorrect behaviour.

### The debugging loop

1.  Reproduce the problem.
2.  Record the exact error or unexpected behaviour.
3.  Identify when it started.
4.  Inspect the relevant code and recent changes.
5.  Form a possible explanation.
6.  Test that explanation.
7.  Make the smallest appropriate fix.
8.  Re-run the original reproduction steps.
9.  Run related tests to check for regressions.
10. Document the cause and solution.

### Understand the error before changing code

When an error appears, capture:

-   The complete error message.
-   The command that produced it.
-   The file and line number, if shown.
-   What you expected.
-   What actually happened.
-   The steps required to reproduce it.
-   What changed immediately before it appeared.

Do not paste secrets, access tokens, passwords, private user data, or
production credentials into an AI chat.

### Common categories of errors

  -----------------------------------------------------------------------
  Category                            Meaning
  ----------------------------------- -----------------------------------
  Syntax error                        The code violates language grammar.

  Runtime error                       The program fails while executing.

  Logic error                         The program runs but produces the
                                      wrong result.

  Type error                          A value is used with an
                                      incompatible type or operation.

  Dependency error                    A required package or version is
                                      missing or incompatible.

  Configuration error                 Environment or project settings are
                                      incorrect.

  Network error                       A request cannot complete as
                                      expected.

  Database error                      A query, connection, schema, or
                                      permission is incorrect.
  -----------------------------------------------------------------------

### Do not accept random fixes

If Claude suggests changing several unrelated files, ask:

-   What is the root cause?
-   Which evidence supports that explanation?
-   Why is this the smallest safe fix?
-   What could this change break?
-   Which tests will verify the fix?

A fix is not complete until the original problem is reproduced
successfully after the change and relevant regression checks pass.

------------------------------------------------------------------------

## 10. Phase 7 --- Review and Understand the Code

Before accepting a feature, review it.

### Your code-review questions

-   Does the code meet the acceptance criteria?
-   Is the solution simpler than necessary, or unnecessarily complex?
-   Are variable and function names meaningful?
-   Is the same logic duplicated?
-   Are errors handled clearly?
-   Is user input validated?
-   Are permissions checked on the server where required?
-   Are secrets kept out of source code?
-   Are loading, empty, and error states handled?
-   Is the interface usable on smaller screens?
-   Are tests included for important behaviour?
-   Did the change affect unrelated features?

### Ask for a teaching explanation

Do not ask only, "Explain this code."

Ask Claude to explain:

1.  The purpose of each changed file.
2.  The role of each important function or component.
3.  The data flow from input to output.
4.  What happens in memory at a high level.
5.  Which parts are handled by the browser, server, database, or
    operating system.
6.  What happens when an error occurs.
7.  Why this design was chosen over a simpler alternative.

For unfamiliar concepts, request a tiny standalone example before
returning to the real project.

### Keep a learning log

``` text
Date:
Feature built:
New concepts learned:
Files changed:
Bug encountered:
Root cause:
How I verified the fix:
What I can now explain:
What I still need to learn:
```

This turns each project into a record of your growing engineering
ability.

------------------------------------------------------------------------

## 11. Phase 8 --- Git and GitHub Workflow

Git records changes to your project so you can understand history and
return to earlier working versions.

GitHub hosts Git repositories and supports collaboration through
branches, commits, and pull requests.

### A safe beginner workflow

``` bash
git status
git add .
git commit -m "Add student creation form"
git push
```

Before using commands, understand what they do:

-   `git status` shows the current state of your working directory.
-   `git add` stages selected changes for the next commit.
-   `git commit` records a snapshot of staged changes.
-   `git push` sends local commits to a remote repository.

Prefer staging specific files instead of blindly using `git add .` when
the project may contain secrets or unrelated changes.

### Make meaningful commits

Good examples:

``` text
Add student list page
Validate student registration form
Fix duplicate student ID handling
Add attendance percentage calculation
Improve mobile navigation
Update project setup instructions
```

Avoid messages such as:

``` text
final
update
changes
fixed
new code
```

### Branches and pull requests

For team projects:

1.  Keep the shared main branch stable.
2.  Create a branch for a focused feature.
3.  Make small commits.
4.  Push the branch.
5.  Open a pull request.
6.  Review the diff.
7.  Run tests.
8.  Merge only after review.

Example:

``` bash
git switch -c feature/student-registration
```

Do not force-push, reset shared history, or delete branches unless you
understand the consequences and have permission from the team.

### Review the diff

Before committing:

``` bash
git diff
git status
```

Ask Claude to explain the diff, but inspect it yourself too. A diff is
the actual set of changes, not just the assistant's summary.

------------------------------------------------------------------------

## 12. Phase 9 --- Security, Privacy, and Secrets

A working application can still be unsafe.

### Essential rules

-   Never commit passwords, API keys, access tokens, or private
    credentials.
-   Keep local secrets in environment variables or an appropriate
    secrets manager.
-   Add local environment files to `.gitignore`.
-   Provide a safe `.env.example` containing placeholder values only.
-   Do not expose private database credentials in browser-side code.
-   Validate input on the server when the server is responsible for the
    operation.
-   Enforce authorization on the server, not only by hiding buttons in
    the interface.
-   Use established authentication and security libraries instead of
    inventing your own security system.
-   Collect only the user data the application genuinely needs.
-   Do not upload private data or confidential code to AI tools unless
    you are authorized and understand the tool's data-handling settings.

### Important distinction: validation vs authorization

**Validation** asks: "Is this input acceptable?"

**Authorization** asks: "Is this user allowed to perform this action?"

Hiding an admin button does not protect an admin operation. The backend
must check permissions too.

### Treat AI-generated code as untrusted until reviewed

AI can produce insecure code or use outdated patterns. Review
authentication, authorization, file uploads, database queries, payment
logic, and handling of personal information carefully. For sensitive or
production systems, get qualified human review.

------------------------------------------------------------------------

## 13. Phase 10 --- Finish and Document the Project

A project is not complete just because the main screen looks good.

A usable repository should explain:

-   What the project does.
-   Why it exists.
-   Who it is for.
-   Which features are implemented.
-   Which technologies are used.
-   How to install dependencies.
-   How to configure environment variables.
-   How to run the project.
-   How to run tests.
-   Known limitations.
-   Future improvements.

### Suggested README structure

``` text
# Project Name

Short description

## Problem
## Features
## Screenshots
## Tech Stack
## Project Structure
## Requirements
## Installation
## Environment Variables
## Run Locally
## Tests
## How It Works
## Known Limitations
## Future Improvements
## Contributing
## License
```

Be honest about incomplete features. Do not describe a planned feature
as implemented.

### Before deployment

-   Confirm the build succeeds.
-   Run the relevant tests.
-   Check environment variables in the hosting platform.
-   Confirm secrets are not in the repository.
-   Test the deployed application.
-   Check error handling and logs.
-   Verify mobile usability.
-   Understand hosting costs, limits, and data retention.
-   Have a rollback plan for important changes.

------------------------------------------------------------------------

## 14. How to Work with Claude

Claude can act as a tutor, planner, pair programmer, debugger, reviewer,
and documentation assistant. Tell it which role you need.

### Recommended collaboration modes

  -----------------------------------------------------------------------
  Mode                                Ask Claude to
  ----------------------------------- -----------------------------------
  Tutor                               Explain a concept using simple
                                      examples.

  Product analyst                     Clarify users, problems, and
                                      requirements.

  Architect                           Propose a small architecture and
                                      explain trade-offs.

  Pair programmer                     Implement one approved feature at a
                                      time.

  Debugger                            Investigate a reproducible issue
                                      using evidence.

  Reviewer                            Inspect a diff for bugs, risks, and
                                      unnecessary complexity.

  Test engineer                       Create and run appropriate tests.

  Documentation writer                Document only what the project
                                      actually does.
  -----------------------------------------------------------------------

### Give Claude project context

At the beginning of a project, provide:

-   Your skill level.
-   The project goal.
-   The intended users.
-   The current repository or files.
-   The tools and technologies already chosen.
-   The constraints from your course or team.
-   What you have already tried.
-   What you want to learn.

Do not assume Claude knows your repository or your previous decisions
unless that context is available in the current workspace or
conversation.

### Ask before broad changes

For significant changes, ask Claude to explain the plan and wait for
your approval. This is especially important for:

-   Replacing frameworks.
-   Changing database schemas.
-   Modifying authentication.
-   Removing files or dependencies.
-   Changing deployment configuration.
-   Running destructive commands.
-   Reformatting or rewriting large parts of the repository.

### Use tool access carefully

If Claude can inspect files, run commands, or edit your repository,
grant only the access needed for the task. Read proposed commands before
approving them. Be particularly careful with commands that delete files,
change permissions, expose services, or alter Git history.

------------------------------------------------------------------------

## 15. Prompt Templates

These prompts are designed to be adapted. Replace the bracketed details
with your actual project information.

### Prompt 1 --- Start a new project correctly

``` text
I am a student learning software engineering through practical projects.

I want to build: [PROJECT IDEA]

My current skill level: [BEGINNER / INTERMEDIATE]
My constraints: [TOOLS, COURSE RULES, TIME, OR OTHER LIMITS]
Intended users: [USERS]

Act as my product-thinking partner and patient software engineering mentor.

Do not start coding yet.

First:
1. Help me clarify the real problem.
2. Identify the target users and their main needs.
3. Ask only the most important unanswered questions.
4. Suggest a realistic MVP.
5. Write clear functional and non-functional requirements.
6. Define acceptance criteria for each MVP feature.
7. Identify risks and assumptions.
8. Suggest a simple technology stack and explain why each tool is needed.

Separate confirmed facts from assumptions. Keep the first version small.
Wait for my approval before moving to architecture or implementation.
```

### Prompt 2 --- Inspect an existing repository

``` text
Before editing anything, inspect this repository.

Tell me:
1. What the application appears to do.
2. Which language, framework, and package manager it uses.
3. The purpose of the important files and folders.
4. The application entry point.
5. How to install, run, build, and test it.
6. Which features already exist.
7. Any obvious configuration, dependency, or structural risks.
8. What you could not determine from the available files.

Do not modify files. Do not guess when evidence is missing.
Explain unfamiliar terms in beginner-friendly language.
```

### Prompt 3 --- Plan one feature

``` text
I want to implement this feature: [FEATURE]

First, explain:
1. The user problem it solves.
2. Expected inputs and outputs.
3. Business rules and validation.
4. Normal, edge, and failure cases.
5. Which existing files may need changes.
6. A small implementation plan.
7. How we will test it.

Do not code yet. Check the existing project conventions and avoid unnecessary dependencies.
Wait for my approval.
```

### Prompt 4 --- Implement one approved feature

``` text
Implement only this approved feature: [FEATURE]

Follow the plan we agreed on and the existing project conventions.

Requirements:
- Make the smallest coherent change.
- Do not rewrite unrelated files.
- Do not add dependencies without explaining why.
- Handle expected errors and invalid input.
- Keep names clear and code maintainable.
- Add or update relevant tests.
- Do not claim that something works unless you actually verify it.

After implementation, report:
1. Files changed and why.
2. What the code does.
3. How data flows through the feature.
4. Commands and tests you ran.
5. Actual test results.
6. Anything still unverified.
7. What I should understand before moving on.
```

### Prompt 5 --- Explain code as a tutor

``` text
Teach me the following code as if I am a student learning computer science.

Do not merely paraphrase each line.

Explain:
1. The problem this code solves.
2. Why this approach is used.
3. The flow of execution step by step.
4. Inputs, outputs, and important variables.
5. The role of functions, classes, or components.
6. What happens in memory at a useful high level.
7. How the browser, operating system, server, or database is involved, where relevant.
8. Common mistakes and edge cases.
9. A simpler example that teaches the same concept.
10. A few questions I should answer to check my understanding.

Use simple language, but preserve correct technical terms.
Do not assume I understand a concept just because it appears in the code.
```

### Prompt 6 --- Debug an issue

``` text
Help me investigate this issue systematically.

Expected behaviour:
[WHAT SHOULD HAPPEN]

Actual behaviour:
[WHAT HAPPENS]

Steps to reproduce:
[STEPS]

Exact error or logs:
[PASTE RELEVANT OUTPUT, AFTER REMOVING SECRETS]

Recent changes:
[WHAT CHANGED]

Do not immediately rewrite the code.

First:
1. Identify the most likely failure area.
2. Explain what the error means.
3. List evidence and possible causes separately.
4. Suggest the smallest diagnostic checks.
5. Ask for missing information if necessary.

After we identify the root cause, propose the smallest safe fix and explain how to verify it.
```

### Prompt 7 --- Review my changes

``` text
Review the current Git diff as a careful software engineer.

Look for:
- Incorrect behaviour and logic errors.
- Missing validation and error handling.
- Security and privacy risks.
- Broken edge cases.
- Unnecessary complexity or dependencies.
- Duplicated logic.
- Accessibility and responsive UI issues, if relevant.
- Missing tests.
- Unrelated changes.

Prioritize findings by severity and include the file and relevant code location.

Do not change files yet. Explain each finding and suggest a minimal correction.
If you find no issue in an area, say that it was reviewed rather than claiming the entire application is bug-free.
```

### Prompt 8 --- Test a feature

``` text
Create a practical test plan for [FEATURE].

Include:
1. Normal cases.
2. Empty and invalid input.
3. Boundary cases.
4. Duplicate or repeated actions.
5. Failure cases.
6. Permission checks, if relevant.
7. Persistence and refresh behaviour, if relevant.
8. Regression checks for related features.

For each test, provide setup, action, expected result, and how to verify it.

Then inspect the available test setup. Do not claim a test passed unless it was actually executed and its result was observed.
```

### Prompt 9 --- Prepare a Git commit

``` text
Inspect my current Git status and diff.

Explain:
1. Which files changed.
2. What each change accomplishes.
3. Whether unrelated or sensitive files are included.
4. Whether tests should be run before committing.
5. A short, accurate commit message.

Do not commit, push, reset, or change Git history without my explicit approval.
```

### Prompt 10 --- Prepare the final project

``` text
Help me prepare this project for submission or demonstration.

Check:
- Requirements and acceptance criteria.
- Installation and run instructions.
- Build and test results.
- Important user journeys.
- Error and empty states.
- Responsive behaviour.
- Security and secrets.
- README accuracy.
- Known limitations.
- Demo steps.

Separate verified results from things that still need manual checking.
Do not invent screenshots, test results, features, or deployment status.
```

------------------------------------------------------------------------

## 16. Common Beginner Traps

  -----------------------------------------------------------------------
  Trap                    Why it causes trouble   Better habit
  ----------------------- ----------------------- -----------------------
  Asking for the entire   Too many assumptions    Build one feature at a
  app at once             and changes.            time.

  Copying code without    You cannot maintain or  Ask for a teaching
  reading it              debug it.               explanation.

  Trusting "it works"     Code may not have been  Ask for actual commands
                          run.                    and results.

  Fixing errors blindly   A patch may hide the    Reproduce and find the
                          real cause.             root cause.

  Installing packages for More dependencies and   Justify every
  everything              complexity.             dependency.

  Ignoring Git            Harder to recover from  Commit small working
                          mistakes.               checkpoints.

  Putting secrets in code Credentials can leak.   Use environment
                                                  variables and secret
                                                  storage.

  Skipping edge cases     Real users do           Test invalid and
                          unexpected things.      boundary inputs.

  Changing many files at  Hard to identify what   Keep changes focused.
  once                    caused a bug.           

  Never reading           You miss tool           Read official docs when
  documentation           constraints and correct behaviour matters.
                          usage.                  

  Treating UI as the      Data, permissions, and  Test the complete user
  whole product           error states may be     journey.
                          broken.                 

  Deploying without       Local success does not  Verify the deployed
  checking                guarantee deployment    version.
                          success.                
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 17. A Practical Project Checklist

Use this checklist as a quality gate. Not every item applies to every
project; mark genuinely irrelevant items as not applicable rather than
pretending they were completed.

### Before coding

-   [ ] I can explain the problem in my own words.
-   [ ] I know who the first users are.
-   [ ] I have defined a realistic MVP.
-   [ ] I have written acceptance criteria.
-   [ ] I understand why the chosen tools are needed.
-   [ ] I have a small implementation plan.

### During development

-   [ ] I inspect existing files before editing.
-   [ ] I work on one coherent feature at a time.
-   [ ] I run the project after meaningful changes.
-   [ ] I inspect the diff.
-   [ ] I test normal and invalid inputs.
-   [ ] I ask for explanations of unfamiliar code.
-   [ ] I avoid unnecessary dependencies.
-   [ ] I keep secrets out of source control.
-   [ ] I commit stable checkpoints.

### Before calling a feature complete

-   [ ] It meets its acceptance criteria.
-   [ ] Its main user journey has been tested.
-   [ ] Relevant edge cases have been checked.
-   [ ] Errors are handled clearly.
-   [ ] Related features still work.
-   [ ] I can explain the important code.
-   [ ] Test results are recorded honestly.

### Before submission or deployment

-   [ ] Setup instructions are accurate.
-   [ ] The application builds and starts.
-   [ ] Relevant tests have been run.
-   [ ] Environment variables are configured safely.
-   [ ] No secrets are committed.
-   [ ] The deployed application has been checked, if deployed.
-   [ ] Limitations are documented.
-   [ ] I can demonstrate the project without relying on unverified
    claims.

------------------------------------------------------------------------

## 18. A 30-Day Learning Roadmap

This roadmap is a suggested pace, not a strict deadline. Spend more time
on a topic when you need it.

  -----------------------------------------------------------------------
  Days                    Focus                   Practical outcome
  ----------------------- ----------------------- -----------------------
  1--3                    Problem definition and  A one-page project
                          requirements            brief and MVP.

  4--6                    Repository structure    A project you can run
                          and Git basics          and commit safely.

  7--10                   HTML, CSS, or your      A simple interface you
                          chosen UI fundamentals  can explain.

  11--14                  Functions, components,  One complete feature
                          and application logic   with validation.

  15--18                  Data and persistence    Save and retrieve data
                                                  appropriately.

  19--21                  Testing and debugging   A test plan and
                                                  documented bug fix.

  22--24                  Code review and         A simpler, more
                          refactoring             understandable
                                                  implementation.

  25--27                  Security and deployment A safely configured
                          basics                  demo deployment, if
                                                  appropriate.

  28--30                  Documentation and       A clear README and a
                          presentation            project demonstration.
  -----------------------------------------------------------------------

### Recommended practice projects

Build them in increasing complexity:

1.  **Personal portfolio:** pages, navigation, responsive layout.
2.  **To-do list:** state, forms, validation, persistence.
3.  **Student marks manager:** data modelling, calculations, edge cases.
4.  **Attendance tracker:** records, date handling, percentage
    calculations.
5.  **Small API-based application:** HTTP requests, loading states,
    errors.
6.  **Team project:** Git branches, pull requests, reviews, and
    documentation.

For each project, write a short explanation of what you built, what you
learned, what broke, and how you verified the fix.

------------------------------------------------------------------------

## 19. Glossary

  -----------------------------------------------------------------------
  Term                                Simple meaning
  ----------------------------------- -----------------------------------
  Repository                          A project folder tracked by Git.

  Source code                         Human-readable instructions written
                                      by developers.

  Runtime                             The environment that executes a
                                      program.

  Dependency                          External code or a package a
                                      project relies on.

  Framework                           A structured set of tools and
                                      conventions for building software.

  API                                 A defined way for software systems
                                      to communicate.

  Frontend                            The part of an application users
                                      interact with.

  Backend                             The server-side part that handles
                                      application logic and data.

  Database                            A system for storing and retrieving
                                      structured or unstructured data.

  Schema                              The structure and rules for data.

  Validation                          Checking whether input follows
                                      required rules.

  Authentication                      Verifying who a user is.

  Authorization                       Checking what an authenticated user
                                      is allowed to do.

  Debugging                           Finding and fixing the cause of
                                      incorrect behaviour.

  Regression                          A previously working behaviour
                                      breaking after a change.

  Unit test                           A test of a small unit of code.

  Integration test                    A test of multiple connected parts.

  Build                               The process of preparing software
                                      for execution or distribution.

  Deployment                          Making an application available in
                                      its target environment.

  Environment variable                A configuration value supplied
                                      outside the source code.

  Commit                              A recorded snapshot of staged Git
                                      changes.

  Branch                              An independent line of work in Git.

  Pull request                        A proposal to review and merge
                                      changes.

  Refactoring                         Improving code structure without
                                      intentionally changing its
                                      behaviour.

  MVP                                 The smallest useful version of a
                                      product.

  Edge case                           An unusual or boundary situation
                                      that still needs correct handling.
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## The Final Principle

The best vibe coder is not the person who can generate the most code in
the shortest time.

It is the person who can:

-   Turn a vague idea into clear requirements.
-   Choose a simple solution for the real problem.
-   Guide AI with precise context.
-   Understand the important parts of the generated code.
-   Test behaviour instead of trusting appearances.
-   Find root causes instead of collecting random fixes.
-   Protect user data and project credentials.
-   Use Git to work safely.
-   Explain the project to another developer.
-   Continue improving the software after the AI conversation ends.

**Use AI to increase your building speed, but use every project to
increase your own engineering skill.**

------------------------------------------------------------------------

# First Message to Give Claude

After adding this README to your Claude Project knowledge or placing it
in the repository, send Claude this message:

``` text
Read the complete Vibe Coding, the Right Way handbook provided in this project.

I am a student who wants to learn real software development while building practical projects. I do not want you to simply generate large amounts of code for me.

Act as my patient software engineering mentor and collaborative coding partner.

Follow these rules throughout our work:

1. Understand the problem before proposing code.
2. Ask focused questions when important requirements are missing.
3. Help me define a small MVP and acceptance criteria.
4. Inspect the existing repository before editing it.
5. Explain the plan and wait for approval before significant changes.
6. Implement one small, coherent feature at a time.
7. Explain important code, file responsibilities, and data flow.
8. Run relevant commands and tests when tools are available.
9. Clearly distinguish verified results from assumptions and untested behaviour.
10. Debug through evidence and root-cause analysis, not random rewrites.
11. Protect secrets, user data, and project integrity.
12. Use Git checkpoints and explain meaningful changes.
13. Teach me the concepts behind the implementation.
14. Do not claim that a feature, test, or deployment works unless it has actually been verified.
15. Never rewrite unrelated parts of the project without explaining why and getting my approval.

My goal is to become capable of building, understanding, testing, debugging, and maintaining real software—not just copying AI-generated code.

Start by asking me what I want to build or, if I already provided a project, inspect it without modifying files. Then guide me through the process one step at a time.
```

**Remember:** This README is a working guide, not a replacement for
official documentation, testing, or your own judgment. Adapt the process
to the project's size and risk.
