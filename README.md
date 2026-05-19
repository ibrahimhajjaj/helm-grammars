# helm-grammars

Pre-built tree-sitter WASM grammars for [Helm](https://github.com/ibrahimhajjaj/helm).

## What's here

A GitHub Actions workflow that compiles tree-sitter grammars to WebAssembly and publishes them as a GitHub Release. Each grammar is packaged as `tree-sitter-<lang>.tar.gz` containing:

- `tree-sitter-<lang>.wasm`: the compiled grammar
- `queries/highlights.scm`: the upstream highlight query

## Languages

c-sharp, cpp, c, java, swift, ruby, lua, perl, r, julia, scala, elixir, erlang, haskell, ocaml, clojure, zig, dart, nix, terraform, hcl, ini, vue, svelte, graphql, prisma, sql, vim, xml, regex.

Add a language by editing `.github/workflows/build-grammars.yml` and adding the grammar's upstream repo to the matrix.

## Triggering a build

Actions → "build-grammars" → "Run workflow". Matrix runs ~30 jobs in parallel, `fail-fast: false` so flaky upstreams self-eject. A release tag `grammars-YYYY-MM-DD` publishes with one tarball per grammar that built successfully.

## License

MIT.
