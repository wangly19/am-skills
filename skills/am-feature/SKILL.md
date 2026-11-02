---
name: am-feature
description: 'Use before adding features, building components, changing product behavior, or planning new functionality. Applies to requests to clarify requirements, discuss a feature, or think through an idea before implementation. When requirements are clear, document them directly. Write feature specifications under docs/feature/ without implementing them.'
---

# Am Feature

Understand what the user wants and why, then write a feature specification that someone else can implement. Use text throughout. Do not offer a visual companion, open a browser to show prototypes, or start a preview server.

Write all responses, questions, summaries, and generated documents in English.

## 1. Assess What Is Known

- If the requirements are clear, document them directly. Do not ask questions just to follow a process.
- If important information about scope, behavior, or approach is missing, begin clarifying.
- Before the first question, say: "If you prefer to skip the questions, tell me and I'll document what we know, with assumptions marked." Then ask one open question about a real situation.
- If the user asks to skip questions, stop asking. State any significant approach choices in one sentence, then document the available information and assumptions.

## 2. Clarify Gradually

Ask one question per turn. Start with real situations, such as "What happened the last time you wished this feature existed?" Avoid narrowing the answer with options upfront; offer concrete suggestions when the user is stuck or asks for your judgment.

Explore these areas as needed rather than reading them out as a questionnaire:

- Who will use the feature, in what situation, and how they handle it today.
- Why it is needed and what success looks like.
- What is included, what is excluded, and which outcomes would be unacceptable.
- Main flows, key behavior, exceptions, and details the user cares about.
- Existing work, examples to follow or avoid, and time or resource constraints.
- Choices about platform, language, and dependencies: which the user wants to make and which they delegate to you.

For existing projects, prefer the current technology and conventions. If inspecting code, files, or external sources would help, explain what you intend to look for. Proceed within existing authorization; ask before going beyond it.

Once you understand a part, briefly play back its purpose and behavior and ask the user to correct omissions before moving on. Keep your assumptions separate from confirmed user decisions. Scale the conversation to the task; do not require long summaries or a fixed number of rounds.

## 3. Settle the Scope

When there is enough information for someone to implement the feature, explain in plain language whether this is a quick, clear task, a small change, or a full project, and summarize its scope.

If the request contains several independent features, agree on an order and work through them one at a time. If the scope grows substantially during the discussion, point out the change and revisit the boundaries.

## 4. Write the Feature Specification

Tell the user you are writing it up before saving. Write to `docs/feature/<topic>.md` in the current project, using an English kebab-case topic such as `docs/feature/user-auth.md`. Create the directory if needed. Update the existing document for the same topic rather than accumulating dated copies, preserving requirements that still apply.

Adapt the document to the feature's complexity and cover the information that matters:

- Background and intent: users, situations, and the problem to solve.
- Goals and scope: inclusions, exclusions, and unacceptable outcomes.
- Feature behavior: main flows, rules, and exceptions.
- Success criteria: observable, verifiable completion conditions.
- Constraints and approach: user decisions and existing project conventions.
- Assumptions and open decisions: clearly label your own choices, details left to the implementer, and unresolved questions when the user skipped clarification.

A quick, clear task may need only a few paragraphs. Do not force the full structure or present important unknowns as settled conclusions.

## 5. Hand Over and Stop

Report the document path, summarize the key questions settled, and identify your own decisions or anything still awaiting confirmation.

Stop there. Do not write product code, scaffold projects, install dependencies, invoke implementation skills, or offer to continue implementing. Implementation requires a subsequent request.
