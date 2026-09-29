# Upstream and maintenance review

This package maintains `vfile-sort@3.0.1` under the independent `@stackline/vfile-sort` name.

- Source: https://github.com/vfile/vfile-sort/tree/4ac681c9c6e2629aad87c2366f9f9e9ea10f0e8d
- Public npm artifact integrity: `sha512-1os1733XY6y0D5x0ugqSeaVJm9lYgj0j5qdcZQFyxlZOSy1jYarL77lLyb5gK4Wqr1d5OxmuyflSO3zKyFnTFw==`.
- Upstream issue evidence checked: 2026-09-29T00:22:21.069158+00:00.
- Original license and author notices are retained.
- The upstream published runtime files and declarations are hash-checked in `.stackline/upstream.json`. Any runtime fix is explicitly listed there.
- Functional upstream suites run against the source and extracted final package. Development tools were reduced to those used by validation; full source and runtime audits must pass.
- Only direct dependencies of the original Stackline portfolio are in this migration. This is not a claim that all transitive projects are maintained by Stackline.

## Issue triage

The queried open-issue list contained no issue entries. This does not establish that the upstream is abandoned or bug-free. No runtime bug fix is claimed for this initial maintenance release.

The evidence query fetched the latest 100 open and 30 closed issue/PR entries and removed PRs. Closed entries were collected for context; this report does not claim an exhaustive historic review.

## Release discipline

The source commit, passing CI and CodeQL, reviewed CI tarball hash, npm provenance, normal and aliased installs, and immutable GitHub release are checked before a release is complete. Published versions and tags are never replaced.
