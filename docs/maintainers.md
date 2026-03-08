# Maintainer Guide (homebrew-openclue)

This repository is the public distribution target for OpenClue:
- Homebrew tap content for tap name `juangamnik/openclue` (cask files under `Casks/`)
- Public GitHub Release host for downloadable artifacts

Source code and release automation live in:  
https://github.com/juangamnik/openclue

## What Belongs Here

- Homebrew cask files in `Casks/` (primarily `Casks/openclue.rb`)
- Repository documentation (`README.md`, this guide)
- Lightweight repo assets (for example images in `assets/`)
- GitHub Release assets attached to releases (uploaded by automation, not committed)

## What Must Not Be Committed Here

- Built binaries or package files (`.zip`, `.tar.gz`, `.deb`, `.rpm`, etc.)
- Ad-hoc local build outputs, temporary test files, checksum dumps
- Manual copies of release artifacts that already belong in GitHub Releases

## First-Release Checklist

1. Confirm source repository release workflow targets `juangamnik/homebrew-openclue`.
2. Confirm required PAT/credentials for cross-repo publishing are configured in the source repo secrets.
3. Confirm `release` environment exists in the source repo and requires manual approval.
4. Confirm `Casks/openclue.rb` template/update logic is wired to the release workflow.
5. Create a test SemVer tag in source repo (`vX.Y.Z`) and run one full dry run.

## Per Tag-Release Checks (`vX.Y.Z`)

1. Trigger release from source repo using a valid SemVer tag.
2. Approve the run in source repo `release` environment.
3. Verify a release is created/updated in `juangamnik/homebrew-openclue`.
4. Verify release notes and expected artifact set were published.

## Post-Release Verification (Every Release)

1. New assets are present in the GitHub Release.
2. `Casks/openclue.rb` is updated to the new version/checksum values.
3. Homebrew installation is testable and works:
   - `brew tap juangamnik/openclue`
   - `brew install --cask openclue`

## Troubleshooting

### Missing PAT in Source Repo

Symptom:
- Workflow cannot publish release assets or update files in this repo.

Checks:
1. Verify PAT secret exists in `juangamnik/openclue`.
2. Verify token has repo write permissions for `juangamnik/homebrew-openclue`.
3. Verify workflow references the correct secret name.

### Missing Release Environment Approval

Symptom:
- Workflow pauses/fails before publishing to this repo.

Checks:
1. Confirm `release` environment exists in source repo.
2. Confirm required reviewers are configured and available.
3. Approve the waiting job, then re-check publish steps.

### Missing or Incorrect Cask Update

Symptom:
- Release exists, but Homebrew install fails or still points to old version.

Checks:
1. Verify `Casks/openclue.rb` was updated in this repo.
2. Verify version and checksum match the uploaded release asset.
3. Re-run source-repo cask update step or patch cask via normal PR flow if required.

## Governance

- Enable and enforce branch protection on `main`.
- Use the automated release pipeline from `juangamnik/openclue` as the standard path.
- Do not manually commit binary artifacts to this repository.
- Manual fixes should be limited, reviewable, and documented.
