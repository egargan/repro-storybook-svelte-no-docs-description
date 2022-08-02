# Storybook Svelte 'Docs' tab missing description issue

This repo was created by running `npx degit chromaui/intro-storybook-svelte-template
repro-storybook...`.

## Installing and running

First, simply clone the repo, install its deps, then run the `storybook` script.

```
git clone git@github.com:egargan/repro-storybook-svelte-no-docs-description.git
cd repro-storybook-svelte-no-docs-description
yarn
yarn storybook
```

Then, have a look at the [`Button.svelte`](/src/stories/Button.svelte) component. The HTML comment
docblock should appear in the 'Docs' tab in Storybook, but it doesn't.

This issue appears to be because of the top-level `{#if size === 'medium'}`, wrapping the button
markup. Removing the button from this if fixes the issue, and has the component description appear
in the 'Docs' tab.
