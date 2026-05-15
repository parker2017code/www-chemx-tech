# www-chemx-tech Agent Guidance

## Scope

- This repo is the static redirect surface for `www.chemx.tech`.
- Keep it small, static, and dependency-free unless the user explicitly changes the site purpose.
- Preserve the redirect target unless the user asks for a different destination.

## Codex Operating Spine

- Codex is the primary agent for this repo. Use `AGENTS.md` as the durable instruction source.
- Claude Code is secondary future compatibility. `CLAUDE.md` should import this file instead of carrying a separate rule set.
- Start substantive work by checking `git status --short` and reading `index.html`.
- Make the smallest coherent patch. Do not rewrite unrelated files or add dependencies without explicit approval.
- Do not change DNS/domain/deploy behavior, analytics, or GitHub Pages settings without calling it out before the edit.
- After edits, report changed files, commands run, verification result, commit hash, push target, and any remaining risk.
- If a check fails, report the exact command and failure. Fix only failures related to the current task unless the user expands scope.

## Verification

- Cheap check: `python3 -m http.server 4177 --bind 127.0.0.1`, then request `/` and confirm it returns `200 OK`.
- For redirect changes, inspect the rendered HTML and verify the target URL is correct.
