# AniList Anime List Filter

Filter your AniList anime list by status and year range — e.g. completed anime from 2024 onwards, something the AniList UI doesn't let you do.

Live demo: `https://haijo2.github.io/anilist-filter/`

## Features

- Load any public AniList user's anime list by username (no login/OAuth needed)
- Filter by list status: Completed, Watching, Planning, Paused, Dropped, Repeating, or All
- Filter by release year range (e.g. 2024+)
- Sort by your score, average score, title, release year, or recently completed
- Gallery and list views (3-column gallery on phones)
- Shows your score plus the show's average score in brackets, e.g. `★ 8 [84]`
- Username and filter selections are remembered per device (`localStorage`)

## Usage

Just open `index.html` in a browser — or the hosted URL on your phone and Add to Home Screen.
Enter your AniList username and the list loads automatically.

No build step, no dependencies, no backend. Single static file.

## How it works

- Uses the public AniList GraphQL API (`https://graphql.anilist.co`)
- Fetches the full list via `MediaListCollection` for the given username
- Entry-level `status` filtering keeps only the selected status (the API returns
  Planning, Dropped, etc. groups too), and entries are deduped across custom lists
- Year filtering/sorting is done client-side on the anime's `startDate`

## Hosting

Any static host works. This repo is published with GitHub Pages
(Settings > Pages > Deploy from branch > `main`).
