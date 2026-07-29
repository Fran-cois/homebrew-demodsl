# homebrew-demodsl

Homebrew tap for [demodsl](https://github.com/Fran-cois/demodsl) — a DSL-driven
automated product demo video generator.

```sh
brew install Fran-cois/demodsl/demodsl
```

`Formula/demodsl.rb` is generated on each release by the `publish-homebrew` job
in the main repository, from the standalone binaries attached to the GitHub
Release. Do not edit it by hand — the next release overwrites it.

The formula ships prebuilt binaries rather than building a Python virtualenv,
so there is no `resource` list to keep in sync with the dependency tree.

## Notes

Rendering a demo drives a real browser and the standalone binary does not bundle
Playwright's Chromium. Commands that never touch a browser (`validate`,
`capabilities`, `estimate`, `qa`, `eval`) work as installed. To record a page:

```sh
pipx run playwright install chromium
```

`ffmpeg` is pulled in as a formula dependency and is used for the final encode.
