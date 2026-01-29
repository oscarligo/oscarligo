name: WakaTime Stats

on:
  schedule:
    # Se ejecuta cada día a las 12:00 AM UTC
    - cron: '0 0 * * *'
  # Permite ejecutarlo manualmente desde la pestaña Actions para probar
  workflow_dispatch:

jobs:
  update-readme:
    name: Update Readme with Metrics
    runs-on: ubuntu-latest
    steps:
      - uses: anmol098/waka-readme-stats@master
        with:
          WAKATIME_API_KEY: ${{ secrets.WAKATIME_API_KEY }}
          GH_TOKEN: ${{ secrets.GH_TOKEN }} # O usa secrets.GITHUB_TOKEN si no creaste uno personal
          # Opciones de personalización:
          SHOW_OS: "False"
          SHOW_PROJECTS: "True"
          SHOW_EDITORS: "True"
          SHOW_TIMEZONE: "True"
          SHOW_COMMIT: "True"
          SHOW_LANGUAGE_PER_REPO: "True"
          SHOW_LOC_CHART: "False"
