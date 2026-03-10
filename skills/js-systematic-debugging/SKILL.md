---
name: js-systematic-debugging
description: Systematic debugging of JavaScript/TypeScript issues (runtime errors, build failures, tests). Use to isolate root cause and propose a fix.
---
# JS systematic debugging

## Process
- Gather exact error, stack trace, and reproduction steps.
- Reduce to a minimal case.
- Check the most likely causes (runtime version, bundler, polyfills, types).
- Propose one fix and one quick verification.

## Practices
- Log only necessary values, not everything.
- For async issues, check unhandled promises.
- For build failures, verify config and lockfile changes.

## Language
- Respond in Czech per the `czech-communication-standard` skill.
