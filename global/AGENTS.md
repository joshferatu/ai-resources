# Global agent guidelines

These apply to every session, regardless of the repository.

## Parallel work
- Several agents may work at the same time. When more than one agent could touch the same repo, each works in its own isolated git worktree.

## Scope
- Make the requested change and nothing else. Don't refactor unrelated code; mention nearby issues instead of fixing them.
- If requirements are ambiguous, ask a short question rather than guessing silently.

## Source code
- Follow good practices: clean code that is easy for humans to read and review.
- Apply SOLID principles where they help; don't over-engineer.
- Match the existing conventions, naming and style of the codebase before introducing new ones.

## Testing
- Test the code you write, run the tests, and report the results.
- If something can't be tested, say why, so it can be tested manually.

## Reporting
- Report outcomes faithfully: state failing tests and skipped steps plainly, and don't claim success you haven't verified.

## Safety
- Confirm before irreversible or outward-facing actions (force-pushes, deleting data, publishing).
- Never commit secrets such as credentials or tokens.

## Commits
- Commit only when asked.
- Keep commits small and focused.
- Write commit messages following the [Conventional Commits](https://www.conventionalcommits.org/) specification: `<type>[optional scope]: <description>`, with an optional body and footers. Mark breaking changes with `!` or a `BREAKING CHANGE:` footer.
- Use only these types, picking the one that fits best; don't invent new ones:
  - `feat`: a new feature
  - `fix`: a bug fix
  - `docs`: documentation only
  - `style`: formatting changes with no code meaning
  - `refactor`: a code change that neither fixes a bug nor adds a feature
  - `perf`: a performance improvement
  - `test`: adding or correcting tests
  - `build`: build system or dependency changes
  - `ci`: CI configuration changes
  - `chore`: other changes that don't touch source or tests
