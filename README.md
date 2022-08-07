### Hi there 👋

<!--
**saxenashivang20/saxenashivang20** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
<!-- <p align="center"><img src="https://github-hero-readme.vercel.app/api?username=arpanaditya&linkedin=arpan-aditya&twitter=adityaa_sahoo" href="https://linktr.ee/arpanaditya"/> 
-->


<p align="center"> <img src="https://komarev.com/ghpvc/?username=saxenashivang20&label=Profile%20views&color=0e75b6&style=flat" alt="saxenashivang20" /> </p>

---

<h2 align="center">My Socials :handshake: </h2>
<p align="center">
<a href="https://twitter.com/Shivang_sxn">
<img src="https://raw.githubusercontent.com/klaasnicolaas/ColoredBadges/master/svg/social/twitter.svg" alt="Twitter" style="vertical-align:top; margin:4px">
</a>
<a href="https://www.linkedin.com/in/shivang-saxena-2059601ba/">
<img src="https://raw.githubusercontent.com/klaasnicolaas/ColoredBadges/master/svg/social/linkedin.svg" alt="Linkedin" style="vertical-align:top; margin:4px">
</a>
<a href="https://www.instagram.com/shivang_sxn/">
<img src="https://raw.githubusercontent.com/klaasnicolaas/ColoredBadges/prod/svg/social/instagram.svg" alt="Instagram" style="vertical-align:top; margin:4px">
</a>
<a href="mailto:saxenashivang20@gmail.com">
<img src="https://raw.githubusercontent.com/klaasnicolaas/ColoredBadges/prod/svg/social/gmail.svg" alt="GMail" style="vertical-align:top; margin:4px">
</a>
</p>



---
<!-- Badges used from https://github.com/klaasnicolaas/ColoredBadges -->
<h2 align="center">My Tech Stack 🧰</h2>
<p align="center">
<a href="#">
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus.svg">
</a>
<a href="#">
<img src="https://raw.githubusercontent.com/klaasnicolaas/ColoredBadges/master/svg/dev/languages/python.svg">
</a>
<a href="#">
    <img src="https://raw.githubusercontent.com/klaasnicolaas/ColoredBadges/master/svg/dev/languages/html.svg">
</a>
  <a href="#">
    <img src="https://raw.githubusercontent.com/klaasnicolaas/ColoredBadges/master/svg/dev/languages/css3.svg">
</a>
</a>
</p>

---

<h2 align="center">My Tools :gear: </h2>
<p align="center">
<a href="https://git-scm.com">
<img src="https://raw.githubusercontent.com/klaasnicolaas/ColoredBadges/prod/svg/dev/tools/git.svg" alt="git" style="vertical-align:top; margin:4px">
</a>
<a href="https://github.com/saxenashivang20">
<img src="https://raw.githubusercontent.com/klaasnicolaas/ColoredBadges/prod/svg/dev/services/github.svg" alt="github" style="vertical-align:top; margin:4px">
</a>
<a href="https://code.visualstudio.com/">
<img src="https://raw.githubusercontent.com/klaasnicolaas/ColoredBadges/master/svg/dev/tools/visualstudio_code.svg" alt="vscode" style="vertical-align:top; margin:4px">
</a>
 <a href="#">
<img src="https://raw.githubusercontent.com/klaasnicolaas/ColoredBadges/master/svg/dev/services/google_cloud_platform.svg" alt="google_cloud_platform" style="vertical-align:top; margin:4px">
</a>
 <a href="#">
</p>

---

[![Shivang's GitHub stats](https://github-readme-stats.vercel.app/api?username=saxenashivang20&hide=prs,issues&theme=gruvbox)](https://github.com/saxenashivang20/github-readme-stats)
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=saxenashivang20&layout=compact&theme=gruvbox)](https://github.com/saxenashivang20/github-readme-stats)


<p align="center"> <img src="https://github.com/saxenashivang20/saxenashivang20/blob/output/github-contribution-grid-snake.gif" width="700" /> </p>


# This is a basic workflow to help you get started with Actions


# GitHub Action for generating a contribution graph with a snake eating your contributions.

name: Generate Snake

# Controls when the action will run. This action runs every 6 hours.

on:
  schedule:
      # every 6 hours
    - cron: "0 */6 * * *"

# This command allows us to run the Action automatically from the Actions tab.
  workflow_dispatch:

# The sequence of runs in this workflow:
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Generates the snake  
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: shrankhla20
          # these next 2 lines generate the files on a branch called "output". This keeps the main branch from cluttering up.
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

     # show the status of the build. Makes it easier for debugging (if there's any issues).
      - run: git status

      # Push the changes
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
