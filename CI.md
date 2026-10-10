# Continuous integration

Add manual CI runs, read-only permissions, bounded job times and current setup actions while preserving existing checks.

Existing Python tests, Python lint and TypeScript lint are retained. This workflow change introduces no service credentials or application changes.

Workflows: `.github/workflows/test.yaml`.

Hosted compatibility findings: legacy Whisper failed to build when isolated setuptools lacked `pkg_resources`, so CI constrains build setuptools to <81. The frontend installer failed with pnpm 7.27 under the runner’s newer Node runtime; CI now explicitly uses Node 20 and pnpm 7.33.7. Existing test suites and application code are unchanged.

Sources: [setuptools history](https://setuptools.pypa.io/en/latest/history.html), [pip build constraints](https://pip.pypa.io/en/stable/user_guide/#build-constraints), [pnpm Node 20 compatibility issue](https://github.com/pnpm/pnpm/issues/6424).
