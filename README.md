<p align="center">
    <a href="https://github.com/porada/awesome-vitest">
        <picture>
            <source
                srcset=".github/assets/awesome-vitest-dark-scheme@3x.png"
                media="(prefers-color-scheme: dark)"
            />
            <source
                srcset=".github/assets/awesome-vitest-light-scheme@3x.png"
                media="(prefers-color-scheme: light)"
            />
            <img
                src=".github/assets/awesome-vitest-light-scheme@3x.png"
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
- [Migrating From Jest](https://vitest.dev/guide/migration#jest)

### Features

- [Browser Mode](https://vitest.dev/guide/browser/)
- [Type Testing](https://vitest.dev/guide/testing-types)
- [In-Source Testing](https://vitest.dev/guide/in-source)

### Community

- [Discord](https://chat.vitest.dev)
- [GitHub Discussions](https://github.com/vitest-dev/vitest/discussions)

<div>&nbsp;</div>

## Packages

### Linting

- [**@vitest/eslint-plugin**](https://github.com/vitest-dev/eslint-plugin-vitest) — The official ESLint plugin.
- [**oxlint**](https://oxc.rs/docs/guide/usage/linter.html) — Next-generation linter written in Rust with native support for Vitest.

### Mocking

- [**vitest-canvas-mock**](https://github.com/wobsoriano/vitest-canvas-mock) — Mock and snapshot HTML `<canvas>` output.
- [**vitest-fetch-mock**](https://github.com/IanVS/vitest-fetch-mock) — Mock `fetch` requests and responses.
- [**vitest-mock-extended**](https://github.com/eratio08/vitest-mock-extended) — Type-safe mocking extensions.
- [**vitest-websocket-mock**](https://github.com/akiomik/vitest-websocket-mock) — Test complex WebSocket interactions.

### Snapshot Testing

- [**@cronn/vitest-file-snapshots**](https://github.com/cronn/file-snapshots/tree/main/packages/vitest-file-snapshots) — Snapshot assertions for specific file formats.
- [**path-serializer**](https://github.com/rstackjs/path-serializer) — Serialize file paths into consistent, cross-platform strings.
- [**vitest-ansi-serializer**](https://github.com/43081j/vitest-ansi-serializer) — Serialize ANSI escape sequences into human-readable strings.
- [**vitest-image-snapshot**](https://github.com/wgsl-tooling-wg/wesl-js/tree/main/tools/packages/vitest-image-snapshot) — Visual regression testing for images.
- [**vitest-package-exports**](https://github.com/antfu/vitest-package-exports) — Guard exported APIs against unintended breaking changes.
- [**vitest-react-serializer**](https://github.com/porada/vitest-react-serializer) — Serialize React components into formatted HTML.
- [**vue3-snapshot-serializer**](https://github.com/tjw-lint/vue3-snapshot-serializer) — Serialize Vue 3 components into formatted HTML.

### Browser Mode

- [**@augeo/assay**](https://github.com/AugeoCorp/assay) — Test Shopify Liquid templates with Vitest Browser Mode.
- [**@webcontainer/test**](https://github.com/stackblitz/webcontainer-test) — Run tests inside StackBlitz WebContainers.
- [**vitest-environment-web-ext**](https://github.com/crxjs/vitest-environment-web-ext) — Dedicated testing environment for Chrome Extensions.

### Accessibility Testing

- [**vi-axe**](https://github.com/chaance/vitest-axe) — Run accessibility tests with Axe.
- [**vitest-accessibility-checker**](https://www.npmjs.com/package/vitest-accessibility-checker) — Run accessibility tests with IBM Equal Access Accessibility Checker.

### Reporters

- [**@testream/vitest-reporter**](https://docs.testream.app/reporters/vitest) — Teststream reporter with Jira integration.
- [**vitest-llm-reporter**](https://github.com/hansjm10/vitest-llm-reporter) — Structured JSON output optimized for LLM parsing, with streaming support.
- [**vitest-sentry-reporter**](https://github.com/cadesalaberry/vitest-sentry-reporter) — Sentry reporter for failed tests.
- [**vitest-sonar-reporter**](https://github.com/AriPerkkio/vitest-sonar-reporter) — SonarQube reporter.
- [**vitest-teamcity-reporter**](https://github.com/eratio08/vitest-teamcity-reporter) — TeamCity reporter.
- [**vitest-tiny-reporter**](https://github.com/manbearwiz/vitest-tiny-reporter) — A minimal reporter with concise output.

### Utilities

- [**@async-fn/vitest**](https://github.com/team-igniter-from-houston-inc/async-fn/tree/master/packages/vitest) — Test async functions with controlled resolution and chronological flow.
- [**@raegen/vite-plugin-vitest-cache**](https://github.com/raegen/vite-plugin-vitest-cache) — Improve test performance through caching.
- [**executable-stories-vitest**](https://github.com/jagreehal/executable-stories) — Test user stories in a Cucumber-style format.
- [**vitest-affected**](https://github.com/craigvandotcom/vitest-affected) — Run only tests affected by changed files.
- [**vitest-coverage-merge**](https://github.com/stevez/vitest-coverage-merge) — Merge coverage reports across `jsdom` and Browser Mode test runs.
- [**vitest-fail-on-console**](https://github.com/thomasbrodusch/vitest-fail-on-console) — Fail tests on `console.error()`.
- [**vitest-testdirs**](https://github.com/luxass/vitest-testdirs) — Run tests against isolated directory fixtures.

### Integrations

- [**@cloudflare/vitest-pool-workers**](https://developers.cloudflare.com/workers/testing/vitest-integration/) — Run tests in a Cloudflare Workers runtime.
- [**@storybook/addon-vitest**](https://storybook.js.org/docs/writing-tests/integrations/vitest-addon) — Run Storybook stories as Vitest tests.
- [**eslint-vitest-rule-tester**](https://github.com/antfu-collective/eslint-vitest-rule-tester) — Test ESLint rules using Vitest.
- [**neon-testing**](https://github.com/starmode-base/neon-testing) — Test projects that rely on Neon Postgres databases.
- [**vitest-native**](https://github.com/danfry1/vitest-native) — Test React Native components.
- [**vitest-pool-assemblyscript**](https://github.com/themattspiral/vitest-pool-assemblyscript) — Run AssemblyScript tests in isolated WASM instances.

### Agent Skills

- [**antfu/skills**](https://github.com/antfu/skills) — Collection of agent skills by Anthony Fu, including Vitest.

<div>&nbsp;</div>

## Related Lists

- [Awesome Vite](https://github.com/vitejs/awesome-vite)
- [Awesome Jest](https://github.com/jest-community/awesome-jest)
