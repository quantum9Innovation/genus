# Genus

An implementation of a novel genetic algorithm for performing k-means over an arbitrary metric space

---

## General Overview

Genus is a novel algorithm for efficiently clustering large datasets using the central ideas of k-means.
Unlike k-means, it can be applied in arbitrary metric spaces, where centroids cannot be exactly defined.
Instead, Genus attempts to find medoids by randomly sampling points in arbitrary clusters.
As a genetic algorithm, it is able to generate clusters that optimize a custom objective function;
we define a cost function measuring difference from uniform split and distance between clusters to score candidates,
where a certain parameter can be used to adjust the weight of either of these measures in the cost.
Through the process of natural selection and mutation, Genus can efficiently search through promising clusterings
and determine one that scores quite highly.

---

## Development

Get a Haskell development environment up and running quickly. Thanks to Nix, this template is optimized for a fully reproducible and friendly development environment. It is based on:

- [Nix](https://srid.ca/haskell-nix) + [Flakes](https://serokell.io/blog/practical-nix-flakes) (via [`github:srid/haskell-flake`](https://github.com/srid/haskell-flake)) + GHC 9.6
- VSCode + [HLS](https://github.com/haskell/haskell-language-server)
- [fourmolu](https://github.com/fourmolu/fourmolu) autoformatting
- [Relude](https://github.com/kowainik/relude) as Prelude.
  - `.hlint.yaml` is [from relude](https://github.com/kowainik/relude/blob/main/.hlint.yaml)
- Devshell commands are provided via [just](https://just.systems/); run `just` in devshell.

If you have an *existing* Haskell project, you should probably use https://github.com/srid/haskell-flake instead.

## Getting Started

*tldr: [Install Nix](https://nixos.asia/en/install), [setup direnv](https://nixos.asia/en/direnv), open in VSCode, install recommended extensions and run `just run`.*

Full instructions: https://srid.ca/haskell-template/start

Recommended dev environment setup: https://nixos.asia/en/direnv

## Tips

- Run `nix flake update` to update all flake inputs.
- Run `nix --accept-flake-config run github:juspay/omnix ci` to build _all_ outputs.
- [pre-commit] hooks will automatically be setup in Nix shell. You can also run `pre-commit run -a` manually to run the hooks (e.g.: to autoformat the project tree using fourmolu, nixpkgs-fmt, etc. as well run programs like hlint). The hooks will checked as part of flake checks (thus CI).
- Run `just docs` to start Hoogle with packages in your cabal file.
- Run the application without installing: `nix run github:quantum9innovation/genus` (or `nix run .` from checkout)
- Common workflows
  - Adding library dependencies in Nix: https://community.flake.parts/haskell-flake/dependency
  - Adding tests: https://srid.ca/haskell-template/tests

## Discussions

Questions? Ideas? Suggestions? Join our [NixOS Zulip](https://nixos.zulipchat.com/#narrow/stream/413949-haskell-flake) or post in [Github Discussions](https://github.com/srid/haskell-template/discussions).

[pre-commit]: https://github.com/cachix/git-hooks.nix
