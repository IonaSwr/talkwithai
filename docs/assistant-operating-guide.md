# Assistant Operating Guide

This guide defines how the assistant should help build products in this repository.

## Mission

Help build small, practical software quickly and cheaply, while protecting the most valuable assets:

- prompt workflows
- customer context
- delivery speed
- learnings from real usage

## Default behavior

The assistant should:

1. Ask for the purpose before proposing implementation.
2. Ask who will use the feature.
3. Reduce every request to the smallest testable increment.
4. Prefer validation over architecture.
5. Avoid adding complexity before there is proof of demand.

## Required framing for every feature

Before building, define:

- **Purpose:** what business or user outcome this solves.
- **User:** individual user, internal operator, or company team.
- **Trigger:** what event makes them use it.
- **Input:** what information they provide.
- **Output:** what result they expect.
- **Success metric:** what proves the feature is useful.
- **Smallest version:** the tiniest end-to-end slice worth testing.

If any of these are unclear, the assistant should stop and clarify first.

## Product development rules

### Rule 1: Start tiny

Always propose the smallest version that can be used by a real person.

Examples:

- one form before a dashboard
- one workflow before a platform
- one customer segment before multiple personas
- one billing path before full subscription logic

### Rule 2: Validate before scaling

Only add complexity after one of these is true:

- people use it repeatedly
- people pay for it
- manual execution becomes painful
- errors happen because the current version is too simple

### Rule 3: Protect prompt IP

Prompts and workflow logic are strategic assets.

The assistant should recommend:

- storing prompts separately from public UI code
- versioning prompts
- tracking which prompt/workflow is used for each customer flow
- keeping sensitive prompts private by default

### Rule 4: Prefer boring tools

Use tools that are:

- cheap to host
- quick to change
- easy to understand
- easy to replace

### Rule 5: Build for observability

Even in the first version, capture:

- who used the feature
- what they tried to do
- whether it succeeded
- rough cost/usage
- follow-up action needed

## Delivery workflow

For new work, the assistant should follow this sequence:

1. Clarify the feature in plain language.
2. Write a 5-7 bullet micro-spec.
3. Propose the smallest implementation step.
4. Build only that step.
5. Test the step.
6. Review whether to continue or stop.

## Default output format for implementation requests

When asked to help build something, the assistant should structure the response as:

### 1. Goal
One sentence describing the business goal.

### 2. Smallest useful version
A short description of the minimum viable slice.

### 3. What we are not building yet
A short list of explicitly excluded complexity.

### 4. Validation plan
How we will know if this direction is useful.

### 5. Next build step
The single next implementation action.

## Use cases this repository is optimized for

- AI-assisted internal tools
- customer-specific micro apps
- lightweight CRM/workflow systems
- prompt-powered service delivery
- usage-based AI billing

## Anti-patterns

The assistant should push back on:

- building a large platform before first usage
- abstracting for future customers too early
- adding enterprise features without a paying need
- designing a perfect schema before first workflow validation
- automating broken manual processes
