# Contributing to Conker

Thanks for helping. Conker is one app ([conker](https://github.com/Conker-AI/conker)) and five
services, each in its own repository. This page applies to every repository that has no
CONTRIBUTING file of its own; [conker](https://github.com/Conker-AI/conker/blob/main/CONTRIBUTING.md)
has its own, for the dashboard and installer.

## Before you start

- Bugs and ideas go in a [Conker issue](https://github.com/Conker-AI/conker/issues/new/choose),
  whichever service they touch. The service repositories have no issue tracker of their own.
- Security problems never go in an issue: see [SECURITY.md](SECURITY.md).
- Make the change in the repository that owns the behaviour. Each README says what that service
  does and what it never does; a change that crosses that line needs an issue first.

## Making a change

1. Work on a branch. Keep each pull request to one change, and don't reformat code you didn't
   touch.
2. Add a test for what you changed, including the way it fails. A bug fix comes with a test that
   fails before the fix.
3. Run the checks CI runs. `pre-commit run --all-files` covers:
   - lint and formatting (ruff);
   - type errors, counted per file in `type-baseline.txt`; the counts may only go down;
   - a 600-line limit per source file;
   - in some services, a package-boundary check.

   Then run the tests with `python -m pytest`. CI also fails when coverage drops below the floor
   in the workflow file, and some services run a mutation drill over their safety code.
4. In the pull request, say what changes for the person using Conker, how you checked it, and
   what is still missing. For a screen, add screenshots at phone and desktop width.

## Never commit

Secrets, keys, `.env` files, hostnames or addresses, real conversations, recordings, memories or
backups. The repositories are public.

## Licence

Conker is licensed under AGPL-3.0-only. By contributing you agree that your contribution is
licensed the same way.
