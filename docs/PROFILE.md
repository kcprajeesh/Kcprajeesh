# Profile design and maintenance

## Concept

An editorial security workbench: personal identity first, a compact typographic manifesto, then source-backed projects. CYVANTAS supplies the signature without taking over Prajeesh’s profile. The four verbs become a two-line poster; the featured repositories explain what those verbs mean in practice.

Three directions were considered using the design-taste skill: split stage, type-only statement, and contact sheet. Type-only statement was selected because verified source code is the strongest available material. The direction seed is `118017292`, with no redraws. Its green-black (`#161c1a`), bone (`#e3e2da`), and jade (`#9fc7b8`) palette carries into the local SVG artwork.

GitHub controls the document typography and layout. The artwork uses system serif and sans-serif fallbacks instead of web fonts; there are no font downloads, CSS, JavaScript, tracking pixels, statistics services, stock photographs, or generated product screenshots. The website skill’s scroll effects and image quota do not fit the requested Markdown format. The interactive element is the native contribution disclosure, with a static alternative for reduced motion.

## Files

| File | Purpose |
| --- | --- |
| `README.md` | Public profile, curated projects, research interests, and supplied public channels. |
| `assets/hero.svg` | Desktop manifesto, 1200 × 330. |
| `assets/hero-mobile.svg` | Compact manifesto, 720 × 300; selected at viewport widths up to 600px. |
| `assets/activity-static.svg` | Static contribution prompt for reduced motion; does not invent activity data. |
| `.github/workflows/snake.yml` | Existing contribution generator, with pinned dependencies and history-preserving publication. |
| `docs/backups/README.before-redesign.md` | Exact original README from commit `2afb8c3b7696fa9018f7710672614cd50287c419`. Historical content, not current profile copy. |
| `docs/PROFILE.md` | Design decisions, evidence, validation limits, and publication instructions. |

The three SVGs total about 2 KB. They are original editable text/vector assets with accessible titles and descriptions, and require no build process or attribution. Keep both hero variants in sync when changing the manifesto. Their opaque dark field works in both GitHub themes.

## Repository evidence

Checked on 2026-10-26 through GitHub’s public repository API, recursive file trees, READMEs, package manifests, and selected implementation files. All five public repositories returned by the account listing were considered; all list `main` as their default branch. The profile’s canonical name is [`kcprajeesh/Kcprajeesh`](https://github.com/kcprajeesh/Kcprajeesh). The existing lowercase remote resolves to it and was preserved.

| Selected repository | Reason and supporting implementation |
| --- | --- |
| [Vibe-pentesterlab](https://github.com/kcprajeesh/Vibe-pentesterlab) | User’s main project. `pyproject.toml` defines the Python `vibe` entry point; `vibe_pentesterlab/cli.py` implements the displayed report arguments. `report.py` exports Markdown/JSON/SARIF; `sandbox.py` runs bounded Python AST parsing inside Docker. The README explicitly places full application lifecycle and browser testing on the roadmap. |
| [CyvantasAlAgent](https://github.com/kcprajeesh/CyvantasAlAgent) | The distinct agent/control-plane project. `cyvantas/security/policy.py` implements authorization/scope/permission decisions; `scope.py`, `orchestration/task_graph.py`, and `storage/evidence.py` substantiate scope matching, task scheduling, and evidence handling. The README and package metadata retain Pentest Agent Suite upstream references, so the profile acknowledges that lineage and does not claim sole original authorship. |
| [CyvantasForge](https://github.com/kcprajeesh/CyvantasForge) | Related modular Python toolkit. The manifest defines `cyvantasforge.interface.cli:main`; `agents/orchestrator.py`, `report/report.py`, and `llm/mock.py` substantiate the package organization, report writers, and deterministic offline provider. Presented as related work rather than an unrelated new capability. |

The `Cyvantas` repository was not featured: the API reported size zero and no primary language. No separate substantial developer utility was found. There are no invented certifications, CVEs, employers, benchmarks, project usage figures, or maturity claims. Planned runtime validation and agent evaluation remain learning and development interests.

## Contribution workflow

The existing `output` branch and both SVG paths were verified. The latest three accessible existing workflow runs had completed successfully. [Most recent observed run](https://github.com/kcprajeesh/Kcprajeesh/actions/runs/40370468913).

The updated workflow keeps daily generation at 00:00 UTC and manual dispatch. A push triggers it only when the workflow itself changes. The generator remains Platane/snk `svg-only` v3; publication remains crazy-max/ghaction-github-pages v4. Their tag revisions were resolved through GitHub and pinned to complete commit hashes. Update those hashes deliberately when upgrading.

Workflow permissions default to none. The single generation/publication job has only `contents: write`, needed for publishing to `output`; it uses the automatic `GITHUB_TOKEN`. Runs publish serially, have a ten-minute limit, preserve branch history, skip empty commits, and disable Jekyll output. No personal token or GitHub Pages hosting is needed. The existing `gh-pages` branch is unrelated to the profile and is untouched.

No setup is normally required: existing successful runs show that Actions is already enabled. After publishing, an optional manual run is available at **Actions → Generate Contribution Snake → Run workflow**. If repository or organization policy blocks it, allow the two pinned actions and ensure the generated-assets branch permits pushes by the workflow token. The workflow requests the required contents permission explicitly. Do not add a personal access token or weaken protection on `main`. Scheduled runs in inactive public repositories can be disabled by GitHub; if that happens, re-enable the workflow in Actions. The main profile does not depend on this animation to communicate any project information.

## Validation

- The starting working tree was clean. The checkout, `main`, remote URLs, tracked files, recent history, workflows, and remote branch heads were inspected before editing. The README backup matches `HEAD:README.md` byte for byte.
- GitHub’s actual Markdown rendering API returned HTTP 200. Its sanitized HTML retained the headings, links, code block, both `picture` elements, responsive/reduced-motion media sources, and `details`/`summary`. Local image references exist and have nonempty alt text.
- All featured repository links, linked source files/package directory, GitHub profile/activity URLs, CYVANTAS, X, Instagram, and both remote snake images returned HTTP 200 during checks. CYVANTAS redirects to `www.cyvantas.in`; Instagram redirects to `www.instagram.com`. Social ownership is supplied by the user; an HTTP response only establishes URL reachability. Intermittent DNS failures were retried; final reachability checks succeeded. The roadmap anchor was checked against the repository README heading.
- All local SVGs parse as XML, have titles/descriptions, contain no embedded scripts or external imagery, and were rasterized with resvg for visual review. Desktop artwork was inspected at 840px wide; mobile artwork and the motion-free fallback at 344px. Serif type and mobile line fit were reviewed. These are asset reviews, not full-page browser screenshots.
- Workflow YAML parsed with the `yaml` library using unique-key checks. Fifteen semantic assertions passed for triggers, branch/paths, permissions, concurrency, timeout, full action pins, owner-derived username, output branch, token reference, and publication settings. No changed workflow was dispatched or run remotely.
- The design-taste source linter reported **0 failures, 0 warnings** on GitHub’s rendered HTML. It does not support raw `.md`/`.svg` inputs. Its browser inspector could not run because no Chromium/Chrome is installed. The downloaded, checksum-verified Linux ARM64 actionlint binary could not execute on Android (`unexpected e_type: 2`); YAML parsing and the semantic checks above are the available workflow validation, not a claimed actionlint pass.
- Manual reading covered heading order, short mobile lines, a three-line CLI example, link labels, optional animation, and clear separation of implemented features from roadmap work. Full GitHub page screenshots, keyboard behavior, and real-device rendering still need visual confirmation after publication. No browser audit score is claimed.
- The complete tracked diff and every new file were reviewed; `git diff --check` passed. Nothing was staged, committed, pushed, or changed in credentials/remotes. Temporary downloads, validation packages, and renderings were kept outside the repository.

## Review and publish

Run from this checkout. The commands deliberately list the seven intended files; inspect them before committing.

```sh
cd /data/data/com.termux/files/home/GitHub/kcprajeesh-profile
git status --short --branch
git diff --check
git diff -- README.md .github/workflows/snake.yml
git ls-files --others --exclude-standard
cat docs/PROFILE.md
cat assets/hero.svg assets/hero-mobile.svg assets/activity-static.svg
git diff --no-index /dev/null docs/backups/README.before-redesign.md
```

The final command exits 1 when it shows a new file; that is expected. To verify the archived README matches the original commit:

```sh
git show 2afb8c3:README.md | sha256sum
sha256sum docs/backups/README.before-redesign.md
```

Before publishing, inspect any new remote commits:

```sh
git fetch origin
git log --oneline --left-right HEAD...origin/main
git diff HEAD..origin/main -- README.md .github/workflows/snake.yml
```

Continue only if there are no incoming commits. If the remote advanced, preserve the local work and reconcile those changes first. For a clean comparison:

```sh
git add README.md .github/workflows/snake.yml assets/hero.svg assets/hero-mobile.svg assets/activity-static.svg docs/PROFILE.md docs/backups/README.before-redesign.md
git diff --cached --check
git diff --cached --stat
git diff --cached
git commit -m "Design CYVANTAS GitHub profile around verified security projects"
git push origin HEAD:main
```

Use a normal push; a concurrent remote update will be rejected safely. If branch protection requires review, publish a topic branch and open a pull request instead. After publication, inspect the [GitHub profile](https://github.com/kcprajeesh) in light/dark modes and on a phone; check the activity disclosure with reduced motion enabled. Workflow-only changes trigger generation; a manual dispatch is optional.
