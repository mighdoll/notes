What tools should we look at for wesl-js internal development?

What can we make better? (roughly in order)
- end to end test coverage is lacking
    - no tests that actually run in the browser
    - only one or two tests that run dawn, 
    - no tests un naga
    - few tests that run developer tools like webpack, etc.
- typechecking is currently slow especially across packages
- linting is currently disabled
- formatting is slow
- no automated generation of change logs for releases
- CI doesn't guarantee that tests are run
- build dependencies are manual (e.g. for building the wesl library package before building plugins)
- bump script for versioning packages is awkward and monolithic (eveything is published regardless of need)
- it'd be nice to publish to jsr as well
- it'd be nice to track linker perf and size over time across releases 
- lots more!


What tools should we look at
- **Biome** looks promsing for linting / formatting. There's also **oxlint**, and **sherif**.
- **deno** is highly thought of in the backend community, but mostly absent our front end community. But perhaps we we could use some deno tools nonetheless...
- for repo task running / dependency tracking, there are several options **turborepo** and **nx** seem most popular, **moonrepo** looks promising but newer, and **wireit** is the most minimal. (our monorepo isn't that big and complicated)
- **playwright** seems popular for end to end browser testing, and **@vitest/browser** looks interesting (uses **playwright**).
- `.editorconfig` looks popular, we should probably do that.
- **changeset** looks popular for managing lists of changes per release. There's also **beachball**, and **conventional-changelog**. 
- for keeping typescript in sync, there are many guides out there, 
including these from [nx](https://nx.dev/blog/managing-ts-packages-in-monorepos), [moonrepo](https://moonrepo.dev/docs/guides/javascript/typescript-project-refs), [turborepo](https://turbo.build/blog/you-might-not-need-typescript-project-references), and [colinhacks](https://colinhacks.com/essays/live-types-typescript-monorepo).

relesase-plan