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

## 2026-04-23 14:05 WEST - Bebob Ignatius forced-COLMAP Gaussian splat training
- What failed: 600k Ignatius training was launched from reference_pose_intrinsics_manifest.json instead of the recovered COLMAP manifest, despite the user asking to force COLMAP.
- Root cause: I validated COLMAP mapper/cache completion but failed to verify that the manifest passed into run_splatfacto.py had pose source colmap/recovered; --force only forced the training output, not the pose source.
- Final fix: Future forced-COLMAP runs must pass data/cache/colmap/.../manifest.json directly to training, not reference_pose_intrinsics_manifest.json.
- Prevention check: Before launching ns-train, inspect the exact manifest path and assert the first frame pose source/status is colmap/recovered.
- Scope: global
- Status: confirmed-with-user
