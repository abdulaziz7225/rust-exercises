# Small Rust Projects

Welcome to this collection of small Rust projects designed to help you get hands-on experience with Rust,  
explore its syntax, and become familiar with its core features.

Each submodule focuses on a specific Rust concept or technique through clean, practical examples.

---

## Submodules Overview

| Project Name               | Description                                                                    | GitHub Link (main branch)                                                                 |
| -------------------------- | ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| atomic_reference_count     | Efficient atomic reference counting                                            | [View on GitHub](https://github.com/abdulaziz7225/atomic-reference-count/tree/main)       |
| build_your_own_shell       | Learn to build a simple shell in Rust                                          | [View on GitHub](https://github.com/abdulaziz7225/build-your-own-shell-in-rust/tree/main) |
| dynamic_dispatch           | Dynamic dispatch pattern in Rust                                               | [View on GitHub](https://github.com/abdulaziz7225/dynamic-dispatch-in-rust/tree/main)     |
| filter_out_even_numbers    | Filter odd numbers from integer lists in procedural and functional programming | [View on GitHub](https://github.com/abdulaziz7225/filter-out-even-numbers/tree/main)      |
| guess_number               | Simple number guessing game                                                    | [View on GitHub](https://github.com/abdulaziz7225/guess-number/tree/main)                 |
| multi_threaded_program     | Rust multi-threading examples                                                  | [View on GitHub](https://github.com/abdulaziz7225/multi-threaded-program/tree/main)       |
| simple_grep                | Simple grep implementation in Rust                                             | [View on GitHub](https://github.com/abdulaziz7225/simple-grep/tree/main)                  |
| sum_of_squares_of_integers | Sum of squares computations in procedural and functional programming           | [View on GitHub](https://github.com/abdulaziz7225/sum-of-squares-of-integers/tree/main)   |
| uuid_based_collections     | Collections keyed by UUIDs                                                     | [View on GitHub](https://github.com/abdulaziz7225/uuid-based-collections/tree/main)       |

---

## Getting Started

```bash
# Clone the repo including all submodules
git clone --recurse-submodules <your-repo-url>

# Or if already cloned, initialize and update submodules
git submodule update --init --recursive
```

Each submodule is pinned to a specific commit for reproducibility.
To update submodules to their latest `main` commits:

```bash
git submodule foreach 'git checkout main && git pull origin main'
git add .
git commit -m "Update submodules to latest main branch commits"
git push
```
