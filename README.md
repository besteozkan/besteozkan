
# 💻 Tech Stack:
<div style="display: flex; align-items: flex-start;"><img src="https://techstack-generator.vercel.app/python-icon.svg" alt="icon" width="52" height="52" /><img src="https://techstack-generator.vercel.app/java-icon.svg" alt="icon" width="52" height="52" /><img src="https://techstack-generator.vercel.app/mysql-icon.svg" alt="icon" width="52" height="52" /><img src="https://techstack-generator.vercel.app/cpp-icon.svg" alt="icon" width="52" height="52" /></div>

---

[![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)]()
![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)

---

## I’m currently learning
<div style="display: flex; align-items: flex-start;"> <img src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/numpy.png" alt="icon" width="52" height="52" />
<img src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/pandas.png" alt="icon" width="52" height="52" /></div>

name: generate animation

on:
  schedule:
    - cron: "0 */12 * * *"
  workflow_dispatch:

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      - uses: crazy-max/ghaction-github-pages@v3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
