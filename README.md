# Movies Recommendation System
Recommend movies based on inputs provided by user, such as :

1. Number of movies for recommendations
2. From_year
3. To_year
4. Genre (for content-based)/Movie title with release year (for collaborative filtering)

## Introduction

With the rapid explosion of video streaming platforms on the Internet, the catalog of movies is rising exponentially, leaving viewers overwhelmed with a huge database of movies to choose from. Movie Recommendation Systems come into play, which consider users' preferences and recommend movies to them. This saves users a lot of time and effort that would otherwise be wasted while searching for a movie manually. This motivated me to start research on the topic ‘Movies Recommendation’.

## Background

[![forthebadge](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMjQuNDQiIGhlaWdodD0iMzUiIHZpZXdCb3g9IjAgMCAyMjQuNDQgMzUiPjxyZWN0IGNsYXNzPSJzdmdfX3JlY3QiIHg9IjAiIHk9IjAiIHdpZHRoPSIxMjcuMDUiIGhlaWdodD0iMzUiIGZpbGw9IiNFNTA5MTQiLz48cmVjdCBjbGFzcz0ic3ZnX19yZWN0IiB4PSIxMjUuMDUiIHk9IjAiIHdpZHRoPSI5OS4zODk5OTk5OTk5OTk5OSIgaGVpZ2h0PSIzNSIgZmlsbD0iIzAwMDAwMCIvPjxwYXRoIGNsYXNzPSJzdmdfX3RleHQiIGQ9Ik0xNS43OCAyMkwxNC4zMSAyMkwxNC4zMSAxMy40N0wxNS43OCAxMy40N0wxNS43OCAyMlpNMjIuMDcgMjJMMjAuNTkgMjJMMjAuNTkgMTMuNDdMMjIuMDcgMTMuNDdMMjUuODkgMTkuNTRMMjUuODkgMTMuNDdMMjcuMzYgMTMuNDdMMjcuMzYgMjJMMjUuODggMjJMMjIuMDcgMTUuOTVMMjIuMDcgMjJaTTMxLjY3IDE5LjQyTDMxLjY3IDE5LjQyTDMzLjE1IDE5LjQyUTMzLjE1IDIwLjE1IDMzLjYzIDIwLjU1UTM0LjExIDIwLjk1IDM1LjAxIDIwLjk1TDM1LjAxIDIwLjk1UTM1Ljc4IDIwLjk1IDM2LjE3IDIwLjYzUTM2LjU2IDIwLjMyIDM2LjU2IDE5LjgwTDM2LjU2IDE5LjgwUTM2LjU2IDE5LjI0IDM2LjE2IDE4Ljk0UTM1Ljc3IDE4LjYzIDM0Ljc0IDE4LjMyUTMzLjcxIDE4LjAxIDMzLjEwIDE3LjYzTDMzLjEwIDE3LjYzUTMxLjkzIDE2LjkwIDMxLjkzIDE1LjcyTDMxLjkzIDE1LjcyUTMxLjkzIDE0LjY5IDMyLjc3IDE0LjAyUTMzLjYxIDEzLjM1IDM0Ljk1IDEzLjM1TDM0Ljk1IDEzLjM1UTM1Ljg0IDEzLjM1IDM2LjU0IDEzLjY4UTM3LjI0IDE0LjAxIDM3LjY0IDE0LjYxUTM4LjA0IDE1LjIyIDM4LjA0IDE1Ljk2TDM4LjA0IDE1Ljk2TDM2LjU2IDE1Ljk2UTM2LjU2IDE1LjI5IDM2LjE0IDE0LjkxUTM1LjcyIDE0LjU0IDM0Ljk0IDE0LjU0TDM0Ljk0IDE0LjU0UTM0LjIyIDE0LjU0IDMzLjgxIDE0Ljg1UTMzLjQxIDE1LjE2IDMzLjQxIDE1LjcxTDMzLjQxIDE1LjcxUTMzLjQxIDE2LjE4IDMzLjg1IDE2LjUwUTM0LjI4IDE2LjgxIDM1LjI4IDE3LjEwUTM2LjI3IDE3LjQwIDM2Ljg4IDE3Ljc4UTM3LjQ4IDE4LjE2IDM3Ljc2IDE4LjY1UTM4LjA0IDE5LjEzIDM4LjA0IDE5Ljc5TDM4LjA0IDE5Ljc5UTM4LjA0IDIwLjg2IDM3LjIyIDIxLjQ5UTM2LjQxIDIyLjEyIDM1LjAxIDIyLjEyTDM1LjAxIDIyLjEyUTM0LjA4IDIyLjEyIDMzLjMwIDIxLjc3UTMyLjUzIDIxLjQzIDMyLjEwIDIwLjgzUTMxLjY3IDIwLjIyIDMxLjY3IDE5LjQyWk00My44MSAyMkw0Mi4zMyAyMkw0Mi4zMyAxMy40N0w0NS41OSAxMy40N1E0Ny4wMiAxMy40NyA0Ny44NiAxNC4yMVE0OC43MSAxNC45NiA0OC43MSAxNi4xOEw0OC43MSAxNi4xOFE0OC43MSAxNy40NCA0Ny44OCAxOC4xM1E0Ny4wNiAxOC44MyA0NS41OCAxOC44M0w0NS41OCAxOC44M0w0My44MSAxOC44M0w0My44MSAyMlpNNDMuODEgMTQuNjZMNDMuODEgMTcuNjRMNDUuNTkgMTcuNjRRNDYuMzkgMTcuNjQgNDYuODAgMTcuMjdRNDcuMjIgMTYuOTAgNDcuMjIgMTYuMTlMNDcuMjIgMTYuMTlRNDcuMjIgMTUuNTAgNDYuODAgMTUuMDlRNDYuMzcgMTQuNjggNDUuNjQgMTQuNjZMNDUuNjQgMTQuNjZMNDMuODEgMTQuNjZaTTU0LjU1IDIyTDUzLjA4IDIyTDUzLjA4IDEzLjQ3TDU0LjU1IDEzLjQ3TDU0LjU1IDIyWk02MC44NSAyMkw1OS4zNiAyMkw1OS4zNiAxMy40N0w2Mi4zNiAxMy40N1E2My44NCAxMy40NyA2NC42NCAxNC4xM1E2NS40NSAxNC43OSA2NS40NSAxNi4wNUw2NS40NSAxNi4wNVE2NS40NSAxNi45MCA2NS4wMyAxNy40OFE2NC42MiAxOC4wNiA2My44OCAxOC4zN0w2My44OCAxOC4zN0w2NS44MCAyMS45Mkw2NS44MCAyMkw2NC4yMSAyMkw2Mi41MCAxOC43MUw2MC44NSAxOC43MUw2MC44NSAyMlpNNjAuODUgMTQuNjZMNjAuODUgMTcuNTJMNjIuMzcgMTcuNTJRNjMuMTIgMTcuNTIgNjMuNTQgMTcuMTVRNjMuOTYgMTYuNzcgNjMuOTYgMTYuMTFMNjMuOTYgMTYuMTFRNjMuOTYgMTUuNDMgNjMuNTcgMTUuMDVRNjMuMTggMTQuNjggNjIuNDEgMTQuNjZMNjIuNDEgMTQuNjZMNjAuODUgMTQuNjZaTTc1LjQyIDIyTDY5Ljg0IDIyTDY5Ljg0IDEzLjQ3TDc1LjM4IDEzLjQ3TDc1LjM4IDE0LjY2TDcxLjMyIDE0LjY2TDcxLjMyIDE3LjAyTDc0LjgzIDE3LjAyTDc0LjgzIDE4LjE5TDcxLjMyIDE4LjE5TDcxLjMyIDIwLjgyTDc1LjQyIDIwLjgyTDc1LjQyIDIyWk04Mi4wNyAyMkw3OS42MSAyMkw3OS42MSAxMy40N0w4Mi4xMyAxMy40N1E4My4yNiAxMy40NyA4NC4xNCAxMy45N1E4NS4wMiAxNC40OCA4NS41MCAxNS40MFE4NS45OCAxNi4zMyA4NS45OCAxNy41Mkw4NS45OCAxNy41Mkw4NS45OCAxNy45NVE4NS45OCAxOS4xNiA4NS40OSAyMC4wOFE4NS4wMSAyMS4wMCA4NC4xMiAyMS41MFE4My4yMiAyMiA4Mi4wNyAyMkw4Mi4wNyAyMlpNODEuMTAgMTQuNjZMODEuMTAgMjAuODJMODIuMDYgMjAuODJRODMuMjMgMjAuODIgODMuODUgMjAuMDlRODQuNDggMTkuMzYgODQuNDkgMTcuOTlMODQuNDkgMTcuOTlMODQuNDkgMTcuNTJRODQuNDkgMTYuMTMgODMuODkgMTUuNDBRODMuMjggMTQuNjYgODIuMTMgMTQuNjZMODIuMTMgMTQuNjZMODEuMTAgMTQuNjZaTTk5LjUzIDIyTDk2LjQyIDIyTDk2LjQyIDEzLjQ3TDk5LjM0IDEzLjQ3UTEwMC43OSAxMy40NyAxMDEuNTUgMTQuMDVRMTAyLjMwIDE0LjYzIDEwMi4zMCAxNS43OEwxMDIuMzAgMTUuNzhRMTAyLjMwIDE2LjM2IDEwMS45OCAxNi44M1ExMDEuNjcgMTcuMzAgMTAxLjA2IDE3LjU2TDEwMS4wNiAxNy41NlExMDEuNzUgMTcuNzUgMTAyLjEzIDE4LjI2UTEwMi41MSAxOC43OCAxMDIuNTEgMTkuNTFMMTAyLjUxIDE5LjUxUTEwMi41MSAyMC43MSAxMDEuNzQgMjEuMzZRMTAwLjk3IDIyIDk5LjUzIDIyTDk5LjUzIDIyWk05Ny45MCAxOC4xNUw5Ny45MCAyMC44Mkw5OS41NSAyMC44MlExMDAuMjQgMjAuODIgMTAwLjY0IDIwLjQ3UTEwMS4wMyAyMC4xMyAxMDEuMDMgMTkuNTFMMTAxLjAzIDE5LjUxUTEwMS4wMyAxOC4xOCA5OS42NyAxOC4xNUw5OS42NyAxOC4xNUw5Ny45MCAxOC4xNVpNOTcuOTAgMTQuNjZMOTcuOTAgMTcuMDZMOTkuMzUgMTcuMDZRMTAwLjA1IDE3LjA2IDEwMC40MyAxNi43NVExMDAuODIgMTYuNDMgMTAwLjgyIDE1Ljg2TDEwMC44MiAxNS44NlExMDAuODIgMTUuMjMgMTAwLjQ2IDE0Ljk1UTEwMC4xMCAxNC42NiA5OS4zNCAxNC42Nkw5OS4zNCAxNC42Nkw5Ny45MCAxNC42NlpNMTA5LjAyIDE4Ljg2TDEwNi4xNSAxMy40N0wxMDcuODAgMTMuNDdMMTA5Ljc2IDE3LjUxTDExMS43MiAxMy40N0wxMTMuMzYgMTMuNDdMMTEwLjUwIDE4Ljg2TDExMC41MCAyMkwxMDkuMDIgMjJMMTA5LjAyIDE4Ljg2WiIgZmlsbD0iIzAwMDAwMCIvPjxwYXRoIGNsYXNzPSJzdmdfX3RleHQiIGQ9Ik0xNDEuNTcgMjJMMTM5LjI0IDIyTDEzOS4yNCAxMy42MEwxNDEuMTkgMTMuNjBMMTQ0LjkwIDE4LjA3TDE0NC45MCAxMy42MEwxNDcuMjMgMTMuNjBMMTQ3LjIzIDIyTDE0NS4yOCAyMkwxNDEuNTcgMTcuNTJMMTQxLjU3IDIyWk0xNTkuMTQgMjJMMTUyLjM5IDIyTDE1Mi4zOSAxMy42MEwxNTguOTggMTMuNjBMMTU4Ljk4IDE1LjQ0TDE1NC43NSAxNS40NEwxNTQuNzUgMTYuODVMMTU4LjQ4IDE2Ljg1TDE1OC40OCAxOC42M0wxNTQuNzUgMTguNjNMMTU0Ljc1IDIwLjE3TDE1OS4xNCAyMC4xN0wxNTkuMTQgMjJaTTE2NS43MyAxNS40OEwxNjMuMTUgMTUuNDhMMTYzLjE1IDEzLjYwTDE3MC42NyAxMy42MEwxNzAuNjcgMTUuNDhMMTY4LjExIDE1LjQ4TDE2OC4xMSAyMkwxNjUuNzMgMjJMMTY1LjczIDE1LjQ4Wk0xNzcuNDIgMjJMMTc1LjA0IDIyTDE3NS4wNCAxMy42MEwxODEuNjQgMTMuNjBMMTgxLjY0IDE1LjQ0TDE3Ny40MiAxNS40NEwxNzcuNDIgMTcuMjhMMTgxLjEzIDE3LjI4TDE4MS4xMyAxOS4xMkwxNzcuNDIgMTkuMTJMMTc3LjQyIDIyWk0xOTIuNjIgMjJMMTg2LjIzIDIyTDE4Ni4yMyAxMy42MEwxODguNjEgMTMuNjBMMTg4LjYxIDIwLjExTDE5Mi42MiAyMC4xMUwxOTIuNjIgMjJaTTE5OS40MSAyMkwxOTcuMDMgMjJMMTk3LjAzIDEzLjYwTDE5OS40MSAxMy42MEwxOTkuNDEgMjJaTTIwNi40NCAyMkwyMDMuNzMgMjJMMjA2Ljc4IDE3Ljc1TDIwMy44NiAxMy42MEwyMDYuNTMgMTMuNjBMMjA4LjIxIDE2LjAyTDIwOS44NyAxMy42MEwyMTIuNDQgMTMuNjBMMjA5LjUxIDE3LjY2TDIxMi42MyAyMkwyMDkuOTAgMjJMMjA4LjE2IDE5LjQwTDIwNi40NCAyMloiIGZpbGw9IiNFNTA5MTQiIHg9IjEzOC4wNSIvPjwvc3ZnPg==)](https://forthebadge.com)
