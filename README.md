<p align="center">
    <a href="https://github.com/porada/awesome-vitest">
        <picture>
            <source
                srcset=".github/assets/awesome-vitest-dark-scheme-520@3x.png"
                media="(prefers-color-scheme: dark)"
            />
            <source
                srcset=".github/assets/awesome-vitest-light-scheme-520@3x.png"
                media="(prefers-color-scheme: light)"
            />
            <img
                src=".github/assets/awesome-vitest-light-scheme-520@3x.png"
                width="520"
                alt=""
            />
        </picture>
    </a>
</p>

<h1 align="center">Awesome Vitest</h1>

<p align="center">
    <i>pronounced “veetest” (/ˈviːtɛst/)</i>
</p>

<p align="center">
    <a href="https://vitest.dev">Vitest</a> is a next-generation testing framework<br />
    with native support for ES&nbsp;Modules,<br />
    TypeScript, and&nbsp;JSX.
</p>

<p align="center">
    <a href="https://awesome.re"
        ><img
            src="https://awesome.re/badge-flat2.svg"
            alt=""
    /></a>
</p>

<div>&nbsp;</div>

## Official Resources

### Guides

- [Getting Started](https://vitest.dev/guide/)
- [Migrating From Jest](https://vitest.dev/guide/migration/jest)
- [Browser Mode](https://vitest.dev/guide/browser/)

### Community

- [Discord](https://chat.vitest.dev)
- [GitHub Discussions](https://github.com/vitest-dev/vitest/discussions)

<div>&nbsp;</div>

## Packages

### Linting

- [**@vitest/eslint-plugin**](https://github.com/vitest-dev/eslint-plugin-vitest) — The official ESLint plugin.
- [**oxlint**](https://oxc.rs/docs/guide/usage/linter.html) — Rust-based linter with built-in Vitest rules.

### Mocking

- [**vitest-auto-spy**](https://github.com/ASDAlexey/vitest-auto-spy) — Create typed spies from classes.
- [**vitest-canvas-mock**](https://github.com/wobsoriano/vitest-canvas-mock) — Mock Canvas 2D APIs and snapshot recorded drawing calls.
- [**vitest-fetch-mock**](https://github.com/IanVS/vitest-fetch-mock) — Mock `fetch` requests and responses.
- [**vitest-mock-extended**](https://github.com/eratio08/vitest-mock-extended) — Create type-safe mocks from TypeScript interfaces.
- [**vitest-websocket-mock**](https://github.com/akiomik/vitest-websocket-mock) — Mock WebSocket servers and assert message exchanges.

### Snapshot Testing

- [**@cronn/vitest-file-snapshots**](https://github.com/cronn/file-snapshots/tree/main/packages/vitest-file-snapshots) — Snapshot data into JSON, text, and Markdown table files.
- [**path-serializer**](https://github.com/rstackjs/path-serializer) — Serialize file paths into consistent, cross-platform strings.
- [**vitest-ansi-serializer**](https://github.com/43081j/vitest-ansi-serializer) — Serialize ANSI escape sequences into human-readable strings.
- [**vitest-directory-snapshot**](https://github.com/XaveScor/vitest-directory-snapshot) — Snapshot directory trees, including file contents.
- [**vitest-image-snapshot**](https://github.com/webgpu-tools/wesl-js/tree/main/packages/vitest-image-snapshot) — Compare `ImageData` and PNG buffers against baselines, with HTML diff reports.
- [**vitest-package-exports**](https://github.com/antfu/vitest-package-exports) — Guard exported APIs against unintended breaking changes.
- [**vitest-pdf-snapshot**](https://github.com/dapotatoman/vitest-pdf-snapshot) — Compare rendered PDFs against PNG snapshots.
- [**vitest-react-serializer**](https://github.com/porada/vitest-react-serializer) — Serialize React components into formatted HTML.
- [**vitest-screenshot**](https://github.com/bhouston/vitest-gpu/tree/main/packages/vitest-screenshot) — Compare canvases and pixel buffers against image baselines in Node.js.
- [**vitest-snap**](https://github.com/Odonno/vitest-snap) — Snapshot data into plain text, JSON, YAML, and Markdown table files, with redaction for structured formats.
- [**vitest-snapshot-tools**](https://github.com/atombarel/vitest-snapshot-tools/tree/main/packages/vitest-snapshot-tools) — Review snapshot updates in a local UI and selectively apply them.
- [**vue3-snapshot-serializer**](https://github.com/tjw-lint/vue3-snapshot-serializer) — Serialize Vue 3 components into formatted HTML.

### Environments

- [**vitest-environment-happy-dom-extended**](https://github.com/laststance/happy-dom-extended/tree/main/packages/vitest-happy-dom-extended) — Run tests in Happy DOM with real Canvas 2D rendering and extended Web APIs.
- [**vitest-environment-web-ext**](https://github.com/crxjs/vitest-environment-web-ext) — Test Chrome extensions end to end with Playwright.
- [**vitest-environment-webgl-node**](https://github.com/bhouston/vitest-gpu/tree/main/packages/vitest-environment-webgl-node) — Run WebGL tests in Node.js without a browser.
- [**vitest-environment-webgpu-node**](https://github.com/bhouston/vitest-gpu/tree/main/packages/vitest-environment-webgpu-node) — Run WebGPU tests in Node.js without a browser.

### Browser Mode

- [**@augeo/assay**](https://github.com/AugeoCorp/assay) — Test Shopify Liquid templates with Vitest Browser Mode.
- [**@webcontainer/test**](https://github.com/stackblitz/webcontainer-test) — Test applications running in StackBlitz WebContainers.
- [**vitest-browser-three**](https://github.com/linbingquan/vitest-browser-three) — Test Three.js shader logic on a real GPU.

### Accessibility Testing

- [**@accesslint/vitest**](https://github.com/AccessLint/accesslint/tree/main/vitest) — Run accessibility tests with AccessLint.
- [**vi-axe**](https://github.com/dhshah/vi-axe/tree/main/packages/vi-axe) — Run accessibility tests with axe.
- [**vitest-accessibility-checker**](https://www.npmjs.com/package/vitest-accessibility-checker) — Run accessibility tests in Browser Mode with IBM Equal Access Accessibility Checker.

### Reporters

- [**@mergifyio/vitest**](https://github.com/Mergifyio/mergify-ci-integrations/tree/main/clients/ts/packages/vitest) — Mergify CI Insights reporter with flaky test detection and quarantine.
- [**@qualflare/vitest**](https://github.com/Qualflare/qualflare-vitest) — Qualflare reporter with retry history.
- [**@testream/vitest-reporter**](https://docs.testream.app/reporters/vitest) — Testream reporter with Jira integration.
- [**power-mode-reporter.vitest**](https://github.com/nomasprime/power-mode-reporter.vitest) — Customizable dot reporter with macOS sound notifications.
- [**vitest-llm-reporter**](https://github.com/hansjm10/vitest-llm-reporter) — Generate compact JSON test reports for LLMs, with failure context and streaming progress.
- [**vitest-md-reporter**](https://github.com/robertozmc/vitest-md-reporter) — Generate Markdown test reports for CI and coding agents.
- [**vitest-sentry-reporter**](https://github.com/cadesalaberry/vitest-sentry-reporter) — Sentry reporter for failed tests.
- [**vitest-sonar-reporter**](https://github.com/AriPerkkio/vitest-sonar-reporter) — SonarQube reporter for test execution results.
- [**vitest-teamcity-reporter**](https://github.com/eratio08/vitest-teamcity-reporter) — TeamCity reporter.
- [**vitest-time-stats-reporter**](https://github.com/crcatala/vitest-time-stats-reporter) — Reporter showing test duration distributions and highlighting slow tests.

### Coverage

- [**nextcov**](https://github.com/stevez/nextcov) — Collect Playwright E2E coverage for Next.js and Vite apps and merge it with Vitest coverage.
- [**supercov**](https://github.com/supercorp-ai/supercov) — Measure per-test coverage, including MC/DC.

### Utilities

- [**@async-fn/vitest**](https://github.com/team-igniter-from-houston-inc/async-fn/tree/master/packages/vitest) — Control when mocked async functions resolve or reject.
- [**@describe-me/vitest**](https://github.com/grzehub/describe-me/tree/main/packages/vitest) — Generate React component documentation from existing tests.
- [**@epure/vitest**](https://github.com/epuremethod/vitest) — Run Gherkin scenarios and structured YAML fixtures as tests.
- [**@vitejs/devtools-vitest**](https://devtools.vite.dev/vitest/) — Run and watch tests from Vite DevTools.
- [**executable-stories-vitest**](https://github.com/jagreehal/executable-stories/tree/main/packages/executable-stories-vitest) — Write `Given`/`When`/`Then` stories in tests and generate documentation.
- [**storyspec**](https://github.com/pluckey/storyspec/tree/main/packages/storyspec) — Link Markdown specifications to typed scenario tests and enforce traceability and architecture rules.
- [**vitest-affected**](https://github.com/craigvandotcom/vitest-affected) — Select affected tests using a persistent runtime dependency graph.
- [**vitest-fail-on-console**](https://github.com/thomasbrodusch/vitest-fail-on-console) — Fail tests on unexpected console errors and warnings.
- [**vitest-git-trigger-patterns**](https://github.com/manbearwiz/vitest-git-trigger-patterns) — Map changed files to specific tests during `--changed` runs.
- [**vitest-plugin-random-seed**](https://github.com/aklinker1/vitest-plugin-random-seed) — Provide a reproducible seed for random test data generators.
- [**vitest-testdirs**](https://github.com/luxass/vitest-testdirs) — Run tests against isolated directory fixtures.
- [**vitiate**](https://github.com/mjkoo/vitiate) — Find bugs with fuzz testing and replay failing inputs as regression tests.

### Integrations

- [**@cloudflare/vitest-plugin**](https://developers.cloudflare.com/workers/testing/vitest-integration/) — Run tests in a Cloudflare Workers runtime.
- [**@logtape/testing-vitest**](https://github.com/dahlia/logtape/tree/main/packages/testing-vitest) — Report LogTape logs when tests fail.
- [**@storybook/addon-vitest**](https://storybook.js.org/docs/writing-tests/integrations/vitest-addon) — Run Storybook stories as component tests in Browser Mode.
- [**@termless/test**](https://github.com/beorn/termless) — Test terminal applications across multiple terminal emulators.
- [**@wojtekmaj/vitest-react-native**](https://github.com/wojtekmaj/vitest-react-native) — Test React Native projects with the framework’s official mocks.
- [**ember-vitest**](https://github.com/NullVoxPopuli/ember-vitest) — Test Ember projects.
- [**eslint-vitest-rule-tester**](https://github.com/antfu-collective/eslint-vitest-rule-tester) — Test ESLint rules and autofixes with custom assertions and snapshots.
- [**gesso-testing**](https://github.com/kevinpbaker/gesso/tree/main/packages/testing) — Test Gesso components without a browser, with semantic queries and layout diagnostics.
- [**mcp-vitest**](https://github.com/nixrajput/mcp-vitest) — Test MCP servers.
- [**neon-testing**](https://github.com/starmode-base/neon-testing) — Run tests against isolated Neon Postgres branches.
- [**rescript-vitest**](https://github.com/cometkim/rescript-vitest) — Write tests in ReScript.
- [**vitest-bats**](https://github.com/spencerbeggs/vitest-bats) — Test Bash scripts through BATS.
- [**vitest-expo**](https://github.com/niondigital/vitest-expo) — Test Expo apps with SDK-specific mocks and navigation helpers.
- [**vitest-groq**](https://github.com/sanity-labs/vitest-groq) — Test GROQ queries and execution plans.
- [**vitest-mongo**](https://github.com/danielpza/vitest-mongo) — Start MongoDB test instances and expose their connection URI.
- [**vitest-native**](https://github.com/danfry1/vitest-native/tree/main/packages/vitest-native) — Test React Native components using real framework code with mocked native modules.
- [**vitest-plugin-rsc**](https://github.com/storybookjs/vitest-plugin-rsc) — Test React Server Components and Next.js App Router apps in Browser Mode.
- [**vitest-pool-assemblyscript**](https://github.com/themattspiral/vitest-pool-assemblyscript) — Run AssemblyScript tests in isolated WASM instances.

### Agent Skills

- [**antfu/skills**](https://github.com/antfu/skills) — Collection of agent skills by Anthony Fu, including Vitest.

<div>&nbsp;</div>

---

<div>&nbsp;</div>
<div>&nbsp;</div>
<div>&nbsp;</div>

<p align="center">
    <a href="https://github.com/porada/awesome-vitest">
        <picture>
            <source
                srcset=".github/assets/awesome-vitest-dark-scheme-90@3x.png"
                media="(prefers-color-scheme: dark)"
            />
            <source
                srcset=".github/assets/awesome-vitest-light-scheme-90@3x.png"
                media="(prefers-color-scheme: light)"
            />
            <img
                src=".github/assets/awesome-vitest-light-scheme-90@3x.png"
                width="90"
                alt=""
            />
        </picture>
    </a>
</p>

<p align="center">Awesome Vitest is curated by&nbsp;<a href="https://dom.engineering">Dom&nbsp;Porada</a>.<br />Licensed under <code>CC0-1.0</code>.</p>

<div>&nbsp;</div>
