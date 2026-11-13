# Install your profile

1. Extract this ZIP. Copy README.md, assets, scripts, and .github into the root of your Dawud-Muhammed/Dawud-Muhammed repository. Include the hidden .github folder. Replace your existing readme.md with README.md; keep only one README.
2. Commit and push to your default branch. The workflow also starts on relevant pushes to main or master.
3. On GitHub, open the repository → Actions → Update profile ring → Run workflow. Select your default branch and run it. Enable Actions if GitHub asks.
4. Once the run succeeds, the placeholder becomes your contribution count. The workflow is scheduled daily at 06:23 UTC. GitHub scheduling and image caching can delay updates.

No personal access token, paid service, JavaScript embed, or third-party statistics server is required. The workflow uses GitHub's temporary built-in token and requests contents: write to save the SVG. Repository or organization rules may block direct bot pushes; review the failed run if this happens. Do not disable branch protections blindly.

## What the number means

The ring displays GitHub GraphQL's contributionCalendar.totalContributions for the default last-year window, not lifetime commits and not a percentage goal. GitHub defines which activity qualifies. The number reflects activity visible to the workflow token; hidden private activity may differ from your signed-in profile. No private repository names or details are requested.

The included SVG intentionally says Awaiting first sync. It does not contain a fabricated total. API errors fail the workflow and preserve the last successfully generated artwork.

## Design

Graphite, brushed-silver gradients, electric blue, a layered 3D-style ring, and a slow orbit animation. This is SVG artwork rather than an interactive 3D scene. Animation can depend on the viewer; the static design remains complete. Reduced-motion preferences disable the orbit in supporting renderers. There is no fox, project list, or contribution heatmap.

The portfolio link is regular README HTML so it remains clickable on GitHub. All illustrations are local SVGs. Change the brand copy or colors in assets/intro.svg and scripts/update_profile.py. Regenerate the initial artwork locally with:

```sh
python3 scripts/update_profile.py --placeholder
```

Normal live regeneration requires GH_TOKEN in the environment. Never put a token into source code. The automated workflow supplies its own token.

GitHub can disable scheduled workflows in inactive public repositories after 60 days without activity; re-enable the workflow in Actions if needed. This package has been checked locally; the authenticated API request and repository push must be verified by your first workflow run.

Official references:
- https://docs.github.com/en/graphql/reference/users
- https://docs.github.com/en/actions/concepts/security/github_token
- https://docs.github.com/en/actions/reference/workflows-and-actions/workflow-syntax
