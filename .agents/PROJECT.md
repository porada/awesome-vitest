# Project Documentation

This document records constraints, durable facts, maintenance decisions, and rationale that are not obvious from source and configuration. `AGENTS.md` remains authoritative for agent instructions.

## Tooling

### Managed Skills

Skills listed in the `postinstall` script are installed from external sources and kept out of Git. The resulting network dependency is an accepted tradeoff for one installation workflow across environments.
