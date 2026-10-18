# apple-top-music

Apple Music top charts data for [Apple Top](https://github.com/rss2401/apple-top).

This repository only stores data. The website, downloader, and shared workflow live in
[rss2401/apple-top](https://github.com/rss2401/apple-top), which reads this repository's
GitHub Pages site through the relative path `../apple-top-music/`.

## Contents

| Path | Description |
| --- | --- |
| `rankings/YYYYMM/` | Ranking RSS JSON per month: `<country>_music_<feed>.json` |
| `details/<id>.json` | iTunes Lookup responses, one result per country |
| `archives/<id>.json` | Ranking history of each item across months |
| `logos/` | Artwork: `<id>-<url-hash>.png`, one file per artwork URL |
| `rankings.json` | Index of all ranking and list files, used by the website |

Snapshot at migration: 2192 items, 2101 detail files, 4051 artwork files, 2192 archives.

## Updates

`.github/workflows/update.yml` runs at 04:23 UTC on the first day of each month and every
Monday, and can be started manually. Every run in a month overwrites that month's
`rankings/YYYYMM/` directory, so each month keeps the latest weekly snapshot.

Data before this repository was created was migrated from
[xy2401/appstore](https://github.com/xy2401/appstore), where the full Git history remains.
