# Context Engineering

Feed agents the right information at the right time — rules files, context packing, MCP integrations.

## Overview

Agent output quality depends on context quality. Pack relevant files, skills, and documentation without flooding agents with unrelated information.

## When to Use

- Starting a session
- Switching tasks
- When output quality drops
- Before complex implementations

## Process

1. **Assess context** — what does the agent need to know?
2. **Pack relevant files** — read and provide relevant source files
3. **Load relevant skills** — only skills matching the current task
4. **Use MCP servers** — context7 for docs, postgres for DB schema, etc.
5. **Monitor quality** — if output drops, repack context

## Rationalizations & Rebuttals

| Excuse | Rebuttal |
|--------|----------|
| "More context is always better" | Too much context dilutes signal. Be selective. |
| "The agent will figure it out" | Agents need relevant context to produce quality work. |
| "I'll load all skills" | Unrelated skills increase noise and token usage. |

## Red Flags

- Output quality dropping without context repacking
- Unrelated skills loaded for simple tasks
- Agents guessing instead of using available docs/MCP
- Missing files that agents need

## Verification

- Relevant files read before implementation
- Only task-relevant skills loaded
- MCP servers used for docs/schema/context
- Output quality monitored and improved