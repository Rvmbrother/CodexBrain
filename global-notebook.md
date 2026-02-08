# Global Notebook

Read this file at `/lfm` startup.
Store learnings that are safe across repositories and non-coding contexts.

## Agent Prompts & Workflows

## General Engineering Heuristics

## Language/Framework Patterns (Generic)

## Testing Philosophy (Generic)

## Git/Delivery Hygiene

## Reusable Templates

## 2026-02-08 20:45 WET - nextauth-url-env-validation
- What failed: Authentication routes failed in production with ERR_INVALID_URL when checking /en/login and /studio redirects.
- Root cause: NEXTAUTH_URL contained multiple origins and newline characters; NextAuth requires one absolute URL value.
- Final fix: Set NEXTAUTH_URL to one environment-appropriate absolute URL and redeployed before re-testing auth routes.
- Prevention check: Add an env lint check that rejects commas/newlines in URL vars and smoke-test /api/auth/providers and /en/login after env changes.
- Scope: global
- Status: confirmed-with-user
