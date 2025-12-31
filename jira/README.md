# Jira Tickets Local Storage

This directory contains local copies of all Jira tickets for context and synchronization.

## Structure

- `tickets/` - Individual Jira tickets (stories, tasks, bugs, etc.)
- `epics/` - Epic-level items

## File Naming Convention

Format: `[TICKET-KEY]-[TITLE-SLUG].md`

Example:
- `PROJ-123-backend-user-auth-api.md`
- `PROJ-124-frontend-login-component.md`

## Purpose

- Maintain local context for AI assistance
- Enable two-way sync with Jira
- Track ticket history and changes
- Reference tickets without API calls

