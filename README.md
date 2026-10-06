[![Anurag's GitHub stats](https://github-stats-extended.vercel.app/api?username=ryan2414)](https://github.com/stats-organization/github-stats-extended)

### Hi there 👋

<h1>I'm CapyCody.</h1>

<h2>🌱 My Skill is C#, Winform, Unity, Swift, iOS</h2>
<h2>📫 How to reach me js6270@naver.com</h2>

<h2>🔭 I'm working in Viet Nam as FA Developer Since 2025 </h2>
<h2>🔭 I'm studying Vietnamese, C#, Swift. </h2>

name: Update README cards

on:
  schedule:
    - cron: "0 0 * * *" # Runs once daily at midnight
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    permissions:
      contents: write

    steps:
      - uses: actions/checkout@v6

      - name: Generate stats card
        uses: stats-organization/github-readme-stats-action@v2
        with:
          card: stats
          options: username=${{ github.repository_owner }}&show_icons=true
          path: profile/stats.svg
          token: ${{ secrets.GITHUB_TOKEN }}

      - name: Generate top languages card
        uses: stats-organization/github-readme-stats-action@v2
        with:
          card: top-langs
          options: username=${{ github.repository_owner }}&layout=compact&langs_count=6
          path: profile/top-langs.svg
          token: ${{ secrets.GITHUB_TOKEN }}

      - name: Generate pin card
        uses: stats-organization/github-readme-stats-action@v2
        with:
          card: pin
          options: username=stats-organization&repo=github-readme-stats
          path: profile/pin-stats-organization-github-readme-stats.svg
          token: ${{ secrets.GITHUB_TOKEN }}

      - name: Commit cards
        run: |
          git config user.name "github-actions[bot]"
          git config user.email "41898282+github-actions[bot]@users.noreply.github.com"
          git add profile/*.svg
          git commit -m "Update README cards" || exit 0
          git push

![Stats](./profile/stats.svg)
![Top Languages](./profile/top-langs.svg)
![Pinned](./profile/pin-stats-organization-github-readme-stats.svg)
