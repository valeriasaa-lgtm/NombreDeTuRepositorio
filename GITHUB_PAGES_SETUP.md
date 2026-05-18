# GitHub Pages setup

SERENA is deployed from the `serena` branch with GitHub Actions.

The deploy workflow is intentionally simple:

1. Check out the repository.
2. Upload the static site artifact from the repository root.
3. Deploy that artifact to GitHub Pages.

If a Pages deploy fails with an access error such as:

```text
HttpError: Resource not accessible by integration
Create Pages site failed
```

open the repository settings and enable Pages manually once:

1. Go to `Settings -> Pages`.
2. Under `Build and deployment`, set `Source` to `GitHub Actions`.
3. Save the setting.
4. Re-run `Deploy SERENA website to GitHub Pages`.

The workflow should not try to create or enable the Pages site by itself. That
requires repository settings access and can fail with the automatic GitHub
Actions token.
