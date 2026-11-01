# Commit Message Convention

This guide helps maintain a clean, clear, and easy-to-track git history. All team members must adhere to the following rules:

## 1. Commit Message Structure

```text
<prefix>(<scope>): <commit title>

[Detailed description / body for important updates]
```

The `(<scope>)` part is optional but encouraged: it names the area touched, e.g.
`fix(codegen): ...`, `build(cmake): ...`, `style(cpp): ...`. Plain
`<prefix>: <commit title>` is also accepted.

### Allowed Prefixes:

* `feat`: Add a new feature
* `fix`: Bug fix
* `docs`: Documentation updates
* `style`: Code style changes (formatting, missing semi-colons, etc.; no production code change). CI's clang-format job commits as `style(cpp): auto-format C++ code via clang-format`.
* `refactor`: Refactoring production code (neither fixes a bug nor adds a feature)
* `perf`: Performance improvements
* `test`: Adding or correcting tests
* `build`: Build system or toolchain changes (CMake, vcpkg, build scripts)
* `ci`: CI workflow changes (`.github/workflows/`)
* `chore`: Other minor changes (dependency updates, configuration changes, untracking files, etc.)
* `release`: Cutting a release (version bump, release notes), e.g. `release: cut v2.0.3.0`. `chore(release): ...` is equivalent.
* `merge`: Manual merge commits, e.g. `merge: feat/x into version/v2.0.4.0`. Default git/GitHub merge titles (`Merge branch ...`, `Merge pull request #N ...`) are also fine.

`wip` is **discouraged**. If you use it on a personal feature branch, squash or
reword those commits before the branch is merged; `wip:` commits should not land
on `master`.

---

## 2. Key Rules

1. **Title Length**:
   * Aim to keep the commit title (the first line) **at or under 72 characters**. This is a recommendation, not a hard rule, but titles beyond that get truncated in `git log --oneline`, GitHub and most tools and become hard to read.
   * Keep it concise, clear, and accurately describing the change. Put detail in the body, not the title.

2. **Detailed Description (Body)**:
   * **Mandatory** when the commit introduces **important updates** (e.g., breaking changes, significant architecture updates, critical security patches, etc.).
   * Always leave a blank line between the title and the body.
   * Example:
     ```text
     feat: support UTF-8 characters in colored console logs

     This update fixes the issue where ANSI color escape codes split raw
     bytes of multi-byte UTF-8 sequences (like blocks and border characters),
     causing corrupted output in terminals. We now process character-by-character.
     ```

3. **No Co-Author Trailers**:
   * Do **not** add `Co-Authored-By:` (or similar attribution trailers such as `Generated-By:`) to commit messages. This applies to commits written with AI tools too.
   * The commit author recorded by git is the only attribution.
